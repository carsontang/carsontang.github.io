---
layout: page
title: Notes
permalink: /notes/
mathjax: true
---

## Business
* Lean startups focus on user growth.
* A startup searches for repeatable and scalable sales.
* Test your ideas by using [hypothesis testing](https://www.entrepreneur.com/article/243528).
* Build prototypes like [Bret
	Taylor](https://www.quora.com/What-is-the-backstory-of-FriendFeed/answer/Bret-Taylor)
* Utilize your personal connections, hobbies, interests
* Honesty and integrity enable word of mouth advertising. Word of mouth
	advertising is the best advertising.
* Generate many ideas to come up with a hit idea.
* History judges people by their peak accomplishments, not by their averages.
* Intuition helps make better decisions when you have experience in the field
	you're making a decision for.
* To generate ideas, listen to other people's inconveniences and note them.
* After he was rejected by YCombinator, Apoorva Mehta, the founder of Instacart,
  convinced a YC partner to grant him an interview by ordering him a six-pack of
	beers of Instacart.
* Mehta quit working on his first idea, a social network for lawyers, because
	his heart wasn't in it.
* Brian Scudamore, the founder of 1-800-GOT-JUNK, parked his truck near a busy
	intersection. His truck gave him free advertising.
* Brian's girlfriend suggested that he call the local newspaper. After the
	reporter and photographer had arrived, the next day, the company had a
	front-page advertisement of his junk pickup business, and the phones were
	ringing.
* Brian fired 9 out of the 11 employees after he realized that he hated working
	with people who weren't of high integrity.
* Brian got the number 1-800-GOT-JUNK after making 62 calls, 3 of which were to the same state official who owned the number. He made his own luck by persisting.
* According to Brian, "your life will have storms, but storms don't last forever."
* 1-800-GOT-JUNK's new CEO lowered goals to increase the team's confidence and morale.
* Amazon likes to set high standards. [Jeff Bezos told the Echo developers that the device had to respond to any query in 1 second, even though the state of the art at the time was 2.5 seconds.](http://www.businessinsider.com/the-inside-story-of-how-amazon-created-echo-2016-4)

## Career
* Ask your peers for judgment since they are also actively working on the
	problems you're working on.
* You can't claim a status, you have to earn it. Status claimers are status quo
	challenging rebels, whereas status earners are leaders with original thought.
* You either have a choice to voice your opinions or exit an unhealthy
	situation. In the long run, speaking up will result in fewer regrets.
* Middle management is less receiptive to new ideas. Lower management have
	little to lose by accepting a new idea. Leaders at the top have already earned
	their statuses and are looking for original ideas.
* Disagreeable managers (bad UI but solid OS) are more receptive to new ideas
	since they have a track record of challenging the status quo. They are more
	likely to stand up for you than people pleasers.
* Expose people to ideas so that they're more receptive to it. This is the mere
	expose fact.
* Look at a task, deliberately procrastinate, and let the idea develop in the
	back of your mind.
* To sustain originality, make fewer plans in advance.
* Sever ties with frenemies - people who are highly supportive **and** highly
	negative toward you.
* Formal training isn't necessary for breakthroughs. Howard Rogers toiled for 15
	years to develop instant color photography. He had no formal training.
* Dissenting for the sake of dissenting isn't useful.
* To innovate, rather than thinking of things to gain with an invention, think
	of what a company would lose out on when the new invention arises.
* Regina Dugan recommends allocating two years on a project so that every week
	is 1% of the time.
* Learning begins not when you ask "how does this work?", but when you ask, "I wonder if..."
* [Elon Musk's secrets to success](http://imgur.com/gallery/9LXLz)
* [Quora answer on how to become part of the 1 percent](https://www.quora.com/How-can-one-become-part-of-the-1/answers/8734078)

## Ideas
* Java huge garbage collector analyzer (10G+)
* [Alibaba infra projects](https://drive.google.com/file/d/0B0Mge0XRpms4VzlyYXJzcTVhcFU/view)
* Steve Scott's tips on how to start a successful blog [1](http://www.stevescottsite.com/startablog.pdf) [2](http://www.stevescottsite.com/begin)
* "How to Build a Great Bot" was the number one session at F8 2017. Companies want to make great bots!

## Software Development
* Don't be afraid to read code, extract essentials, and never limit yourself! Be
	nimble in your thinking.
* Hire people who are willing to challenge your ideas.
* Engineers don't always have good user interfaces, but they might have a solid
	operating system.

## Technical Knowledge
* A pixel is a **pic**ture **el**ement. It is 1 byte, which allows for 256
	possible values. The values of a pixel represent the **intensity**. In a
	grayscale image, the insensity values represent how **black** a pixel is. For
	example, 0 means the pixel is black, and 255 means the pixel is white. Read
	[Digital Image Basics](http://www.whydomath.org/node/wavlets/imagebasics.html)
	to learn more.
* Colored digital images are just combinations of red, green, and blue. Whereas
	a grayscale image is just one channel, a colored image is three channels. Each
	channel is the image's red, green, and blue intensities.
* In an image, **edges** are areas of **strong intensity contrasts**, a jump in intensity from one pixel
  to the next. The [Canny edge detection algorithm](http://masters.donntu.org/2010/fknt/chudovskaja/library/article5.htm)
	looks for these jumps.
* [Why are GPUs better than CPUs for deep learning?]( https://www.quora.com/Why-are-GPUs-well-suited-to-deep-learning/answer/Tim-Dettmers-1)
  Deep learning requires lots of parallel mathematical computations. A GPU can
	perform multiple orders of magnitudes more calculations than a CPU.
* [Description of the Thrift protocol and transport layers](https://gist.github.com/carsontang/8d7c7680e84a509545a6b259de8098ff)
* **Why inheritance sucks** - In Java, implementing an interface should be preferred over inheritance. Inheritance often results in difficult maintenance of code. If a class is inheritable, then you must ensure all future subclasses should implement the interface specified by the class. That is hard to predict unless you know the class is providing base fundamental functionality. Inheritance might result in code reuse and **less time** writing code before it ships, but it also results in **more time** maintaining code after it ships.
* [Why the gradient is the direction of steepest ascent](http://www.math.usm.edu/lambers/mat280/spr10/lecture7.pdf)
* [SSTable](https://www.igvita.com/2012/02/06/sstable-and-log-structured-storage-leveldb/) stands for Sorted String Table. It's a a simple abstraction to efficiently store large numbers of key-value pairs while optimizing for high throughput, sequential read/write workloads.
* [RocksDB is a fork of LevelDB that can handle server side workloads](http://rocksdb.blogspot.com/2013/11/the-history-of-rocksdb.html). RocksDB allows fast read/writes atop SSD, whereas [HBase/HDFS cannot take advantage of SSD](http://hadoopblog.blogspot.com/2012/05/hadoop-and-solid-state-drives.html) (since it was built for disk drives).
* [Simplify your life with an SSH config file](http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/)
* The **Kullback-Leibler divergence** is essentialy the **distance between two probability distributions**. Let's say Carson and Mark's vocabulary consists of "Java", "Macbook", "RegionServer", and "Zeus". Carson says the words with probabilities 0.25, 0.25, 0.35, and 0.15. Mark says the words with probabilities 0.15, 0.55, 0.15, and 0.15. The KL divergence between the two probability distributions measures how different they are. In machine learning, the softmax classifier minimizes the KL divergence between the estimated probabilities of each feature and the "true" distribution, which is known because of supervised learning.
* set up a relatively secure SSH server on your home PC with either `ngrok tcp 22` or ZeroTier. To use ZeroTier, both the client and the server need to be on the virtual ZeroTier network. If a ZT network can't be joined, check for PORT_ERROR and check /var/log/syslog for zt0/zt1 related issues.
* Python searches for modules in 1) the directory containing the input script (or current directory) 2) PYTHONPATH and 3) installation-dependent default. [Source](https://docs.python.org/2/tutorial/modules.html#the-module-search-path)


## Miscellaneous
### Why Android isn't as smooth as iPhone

Android UI will never be completely smooth because of the following design constraints:

* UI rendering occurs on the main thread of an app
* UI rendering has normal priority

Even with a Galaxy Nexus, or the quadcore EeePad Transformer Prime, there is no
way to guarantee a smooth frame rate if these two design constraints remain
true. It’s telling that it takes the power of a Galaxy Nexus to approach the
smoothness of a three year old iPhone. So why did the Android team design the
rendering framework like this?

Work on Android started before the release of the iPhone, and at the time
Android was designed to be a competitor to the Blackberry. The original Android
prototype wasn’t a touch screen device. Android’s rendering trade-offs make
sense for a keyboard and trackball device. When the iPhone came out, the Android
team rushed to release a competitor product, but unfortunately it was too late
to rewrite the UI framework.

### Interesting datasets
* [Instacart Online Grocery Shopping Dataset 2017, 3 million grocery orders from 200,000+ Instacart users.](https://tech.instacart.com/3-million-instacart-orders-open-sourced-d40d29ead6f2)
* [Mapillary Vistas Dataset—the world’s largest and most diverse publicly available, pixel-accurately and instance-specifically annotated street-level imagery dataset](http://blog.mapillary.com/product/2017/05/03/mapillary-vistas-dataset.html)
* [List of medical datasets](https://github.com/beamandrew/medical-data)
