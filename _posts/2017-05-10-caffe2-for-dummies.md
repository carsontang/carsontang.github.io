---
layout: post
title: Caffe2 for Dummies
excerpt: Notes on installing Caffe2 on Ubuntu 16.04, Caffe2's code structure, and its usage.
category: machine learning
tags: [machine learning]
---

## Troubleshooting Installation on Ubuntu 16.04

Visit the [official Caffe2 installation site](https://caffe2.ai/docs/getting-started.html?platform=ubuntu&configuration=compile) for the latest instructions.

Run `python -c 'from caffe2.python import core' 2>/dev/null && echo "Success" || echo "Failure"` to see if Caffe2 was installed properly. If `"Failure"` is outputted, check the following:

**Caffe2 missing in Python module search path** - Did you run the command within `caffe2/build`? If not, `cd` into `caffe2/build` or `export PYTHONPATH=$PYTHONPATH:/path/to/caffe2/build` so that the Python module search path will include `caffe2.python`.

**Anaconda using outdated libgcc** - Open up the python shell and type `from caffe2.python import core`.

```
>>> from caffe2.python import core
WARNING:root:This caffe2 python run does not have GPU support. Will run in CPU only mode.
WARNING:root:Debug message: /home/$USER/anaconda2/bin/../lib/libstdc++.so.6: version `CXXABI_1.3.8' not found (required by caffe2/python/caffe
2_pybind11_state_gpu.so)
CRITICAL:root:Cannot load caffe2.python. Error: /home/$USER/anaconda2/bin/../lib/libstdc++.so.6: version `GLIBCXX_3.4.20' not found (required
by caffe2/python/caffe2_pybind11_state.so)
```

This means Anaconda has an outdated `libstdc++.so`. To double check this, run `strings ~/anaconda2/lib/libstdc++.so | grep GLIBCXX_3.4`. This should be missing GLIBCXX_3.4.20. To fix this issue, run `conda install libgcc`. Running `strings ~/anaconda2/lib/libstdc++.so | grep GLIBCXX_3.4` should now show `GLIBCXX_3.4.20`.

## Hosting Jupyter Notebook on Server

* (on server) `jupyter notebook --no-browser --port=8889`
* (on laptop) `ssh -N -f -L localhost:8885:localhost:8889 user@remotehost`
* Copy the URL printed by Jupyter on the server, and replace the `8889` with `8885`. Visit this URL on your laptop.