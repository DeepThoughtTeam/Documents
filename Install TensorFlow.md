Install TensorFlow (assume on mac os)

	if not install pip:
	    sudo easy_install pip
	if installed pip, try upgrade first:
	    sudo pip install --upgrade pip

	install tensorflow:
	    sudo easy_install --upgrade six
	    sudo pip install --upgrade https://storage.googleapis.com/tensorflow/mac/tensorflow-0.5.0-py2-none-any.whl
	    
	    
Test TensorFlow Installation 

	run this python script:
	
	```python
	  import tensorflow as tf	
    hello = tf.constant('Hello, TensorFlow!')
	  sess = tf.Session()
	  print sess.run(hello)	
	```