#### Install TensorFlow (assume on mac os)

	if not install pip:
	    sudo easy_install pip
	if installed pip, try upgrade first:
	    sudo pip install --upgrade pip

	install tensorflow:
	    sudo easy_install --upgrade six
	    sudo pip install --upgrade https://storage.googleapis.com/tensorflow/mac/tensorflow-0.5.0-py2-none-any.whl
	    
	    
#### Test TensorFlow Installation 

run this python script:

``` Python
import tensorflow as tf	
	  
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print sess.run(hello)	

```

if encounter error: 

```python
ImportError: numpy.core.multiarray failed to import
```

try: 
```bash
sudo easy_install -U numpy
```
	
	
if encouter error:

```python
>>> import tensorflow as tf
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/usr/local/lib/python2.7/site-packages/tensorflow/__init__.py", line 4, in <module>
    from tensorflow.python import *
  File "/usr/local/lib/python2.7/site-packages/tensorflow/python/__init__.py", line 13, in <module>
    from tensorflow.core.framework.graph_pb2 import *
...
  File "/usr/local/lib/python2.7/site-packages/tensorflow/core/framework/tensor_shape_pb2.py", line 22, in <module>
    serialized_pb=_b('\n,tensorflow/core/framework/tensor_shape.proto\x12\ntensorflow\"d\n\x10TensorShapeProto\x12-\n\x03\x64im\x18\x02 \x03(\x0b\x32 .tensorflow.TensorShapeProto.Dim\x1a!\n\x03\x44im\x12\x0c\n\x04size\x18\x01 \x01(\x03\x12\x0c\n\x04name\x18\x02 \x01(\tb\x06proto3')
TypeError: __init__() got an unexpected keyword argument 'syntax'
```

try:

```bash
sudo pip install --upgrade protobuf
```



	

