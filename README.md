# tensorflow-gpu-osx
built within a virtual environment with this configuration:

 - OSX 10.11.6
 - CUDA 8.0.61
 - CuDNN 5.1.10
 - Python 2.7

Note that CUDA/Cudnn is installed in `/usr/local/cuda` but it has `lib` and `include` symlinks to `/usr/local`

# installation

1. Open Terminal
2. navigate to this folder
3. run `pip install tensorflow-1.6.0rc0-cp27-cp27m-macosx_10_11_x86_64.whl`

# testing

run the TensorFlow Hello World:

```python
'''
HelloWorld example using TensorFlow library.
Author: Aymeric Damien
Project: https://github.com/aymericdamien/TensorFlow-Examples/
'''

from __future__ import print_function

import tensorflow as tf

# Simple hello world using TensorFlow

# Create a Constant op
# The op is added as a node to the default graph.
#
# The value returned by the constructor represents the output
# of the Constant op.
hello = tf.constant('Hello, TensorFlow!')

# Start tf session
sess = tf.Session()

# Run the op
print(sess.run(hello))
``` 

On this configuration it prints the GPU info as expected:
```
019-02-09 02:08:02.088035: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:859] OS X does not support NUMA - returning NUMA node zero
2019-02-09 02:08:02.088162: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1331] Found device 0 with properties: 
name: GeForce GT 750M major: 3 minor: 0 memoryClockRate(GHz): 0.9255
pciBusID: 0000:01:00.0
totalMemory: 2.00GiB freeMemory: 480.28MiB
2019-02-09 02:08:02.088178: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1410] Adding visible gpu devices: 0
2019-02-09 02:08:02.477133: I tensorflow/core/common_runtime/gpu/gpu_device.cc:911] Device interconnect StreamExecutor with strength 1 edge matrix:
2019-02-09 02:08:02.477153: I tensorflow/core/common_runtime/gpu/gpu_device.cc:917]      0 
2019-02-09 02:08:02.477157: I tensorflow/core/common_runtime/gpu/gpu_device.cc:930] 0:   N 
2019-02-09 02:08:02.477226: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1021] Creating TensorFlow device (/job:localhost/replica:0/task:0/device:GPU:0 with 220 MB memory) -> physical GPU (device: 0, name: GeForce GT 750M, pci bus id: 0000:01:00.0, compute capability: 3.0)
```
