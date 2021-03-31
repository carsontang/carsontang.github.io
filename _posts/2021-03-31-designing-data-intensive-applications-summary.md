---
layout: post
title: Summary of Designing Data-Intensive Applications
excerpt: notes taken from reading Martin Kleppmann's book
category: distributed-systems
tags: [distributed-systems]
---

## Overview
* 3 main approaches: single-leader, multi-leader, leaderless

## Synchronous Replication
* **definition** - leader replica waits until all follower replicas have confirmed write success before reporting success to the user
* **advantage** - follower is guaranteed to have up-to-date copy of data that is consistent with leader
* **disadvantage** - if follower doesn't respond (because it has crashed or there is a network fault or for any other reason), the write cannot be processed. The leader must block all writes and wait until the synchronous replica is available again.
* in practice, impractical for all followers to be synchronous. Usually one follower is synchronous so that you have an up-to-date copy of data on at least two nodes: leader and synchronous follower. This is called **semi-synchronous**.
* Facebook [uses semisync](http://yoshinorimatsunobu.blogspot.com/2014/04/semi-synchronous-replication-at-facebook.html) to prevent data loss.

## Asynchronous Replication
* **definition** - leader processes write and reports success to user without waiting for follower replica's confirmation of write success
* leader-based replication often configured as completely asynchronous
* **advantage** - leader can continue processing writes even if all of its followers have fallen behind
* **disadvantage** - the write isn't **durable**; if leader fails and is not recoverable, any writes that haven't been replicated to followers are lost.
* **weak durability** - if system is 100% async, once leader fails, all writes are lost
* Microsoft Azsure uses [chain replication](https://pdos.csail.mit.edu/6.824/notes/l-cr.txt), a variant of synchronous replication, to combat the disadvantages of data loss with async replication

## How to Replicate
* copying files - **This is not sufficient!** Clients are constantly writing to the database so a standard file copy would see different parts of the database at **different points in time**.
* snapshot + replication logs - take a consistent snapshot of the leader's database at some point in time. Copy snapshot to follower node. Follower requests all changes from leader since snapshot was taken. Once follower has processed backlog of changes, it has **caught up**.

## Handling Node Outages
* any node in a system can go down. What if leader goes down?
* **failover** - one of the followers needs to be promoted to the new leader. Clients send writes to new leader, other followers start consuming data changes from new leader
* causes of undetected leader: crashes, power outage, network issues, etc.
* no foolproof way of detecting what has gone wrong, so most systems use a **timeout**. Nodes bounce messages between each other, and if node doesn't respond within say 30 seconds, it is assumed dead.