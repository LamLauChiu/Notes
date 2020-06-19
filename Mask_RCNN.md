Reading and Writing XML Files in Python
https://stackabuse.com/reading-and-writing-xml-files-in-python/
https://pymotw.com/2/xml/etree/ElementTree/create.html

https://stackoverflow.com/questions/48915003/get-the-bounding-box-coordinates-in-the-tensorflow-object-detection-api-tutorial


https://www.geeksforgeeks.org/python-schedule-library/




https://www.codespeedy.com/convert-image-to-base64-string-in-python/

Convert Image to Base64 string in Python


How to post a very long URL using Python - Requests module
requests doesn't really impose a length limit on the query string, but your server might. Certain browsers also limit URL lengths to about 2000 characters.
Making a POST request with the same data with requests is trivial; pass a dictionary of the fields to the data keyword argument and use the requests.post() function:
url = 'http://example.com:8080/testAPI/testAPIServlet'
params = {'id': '123|345.....................................|789',
          'rows': 200}
response = requests.post(url, data=params)
This echoes the GET request variant, where you'd have used the params keyword argument instead.

How to post a very long URL using Python - Requests module


Faster R-CNN: Down the rabbit hole of modern object detection:
https://tryolabs.com/blog/2018/01/18/faster-r-cnn-down-the-rabbit-hole-of-modern-object-detection/

Mask_RCNN/releases

https://github.com/matterport/Mask_RCNN/releases

http://cocodataset.org/#home

https://gluon-cv.mxnet.io/contents.html

Mask R-CNN with OpenCV
Instance segmentation vs. Semantic segmentation

https://www.pyimagesearch.com/2018/11/19/mask-r-cnn-with-opencv/	



https://machinelearningmastery.com/how-to-train-an-object-detection-model-with-keras/

目标检测——目标检测方法的综述

https://blog.csdn.net/gaoyu1253401563/article/details/86477942

It's likely you have Tensorflow 2.0 installed and the code on machine learning mastery has been written on top of tf < 2.0.
You can do either of two things:
* Downgrade your tf to v1.x
* Change tf.random_shuffle to tf.random.shuffle
Also, consider downgrading Keras from v2.3.1 to v2.1.1 (not a must though)
https://stackoverflow.com/questions/59017361/attributeerror-module-tensorflow-has-no-attribute-random-shuffle


AttributeError: module 'tensorflow' has no attribute 'log'

If you can find the exact line where tf.log is used, try tf.math.log instead.

https://github.com/matterport/Mask_RCNN/issues/1797

deep-learning-models

https://github.com/fchollet/deep-learning-models/releases


Deep Learning Framework:
TensorFlow
Keras
PyTorch
Theano
MAXET
CNTK
DeepLearning4J
FastAI

