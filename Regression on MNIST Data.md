#### Download data set

first, download [python file](https://tensorflow.googlesource.com/tensorflow/+/master/tensorflow/examples/tutorials/mnist/input_data.py), the name of downloaded file should be input_data.py.

second, change to directory where saving input_data.py, run:
```bash
sudo python -m compileall .
```

then, open python in command line, and run following code

```python
import input_data
input_data.read_data_sets("MNIST_data/", one_hot=True)
```



#### Build regression model on MNIST dataset (make sure change to input_data directory)

```python
import tensorflow as tf
import input_data

# Open MNIST datasset 
minist = input_data.read_data_sets("MNIST_data/", one_hot=True)

# Create a placeholder. A placeholder is a value that we'll input when we ask TensorFlow to run a computation. 
x = tf.placeholder(tf.float32, [None, 784])


# Since here using linear regression.
# Set parameters W
W = tf.Variable(tf.zeros([784, 10]))

# Set error/basis b
b = tf.Variable(tf.zeros([10]))

# Initialize the regression here.
y = tf.nn.softmax(tf.matmul(x, W) + b)


# Trainning phrase
y_ = tf.placeholder(tf.float32, [None, 10])
cross_entropy = -tf.reduce_sum(y_*tf.log(y))
train_step = tf.train.GradientDescentOptimizer(0.01).minimize(cross_entropy)
init = tf.initialize_all_variables()
sess = tf.Session()
sess.run(init)


for i in range(1000):
  batch_xs, batch_ys = mnist.train.next_batch(100)
  sess.run(train_step, feed_dict={x: batch_xs, y_: batch_ys})
  
  
# Testing phrase
correct_prediction = tf.equal(tf.argmax(y,1), tf.argmax(y_,1))
accuracy = tf.reduce_mean(tf.cast(correct_prediction, "float"))
print sess.run(accuracy, feed_dict={x: mnist.test.images, y_: mnist.test.labels})

# Accuracy should be about 91%
```
