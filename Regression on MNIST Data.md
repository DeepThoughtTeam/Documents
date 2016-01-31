#### Download data set

first, download [python file](https://tensorflow.googlesource.com/tensorflow/+/master/tensorflow/examples/tutorials/mnist/input_data.py), the name of downloaded file should be input_data.py.

second, change to directory where saving input_data.py, run:
```bash
sudo python -m compileall .
```

then, open python in command line, and run following code

```python
import tensorflow.examples.tutorials.mnist.input_data
mnist = input_data.read_data_sets("MNIST_data/", one_hot=True)
```
