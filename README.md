# Finding Fish with Tensorflow Object detection API

## Step 1 
On a GPU machine/VM go through steps in instalation.ipynb notebook.
It should clone tensorflow models and does all the required setttings

## Step 2
Copy fish_detection content inside models/research/object_detection

## Step 3

Run the notebooks in the following order

1. object_detection_tutorial.ipynb
2. create_pascal_tf_record.ipynb
3. train.ipynb
4. fish_detection_tutorial.ipynb

* note
if you get validation error for traing your model with fasterrcnn
update def to_absolute_coordinates method and set check_range=False in models/research/object_detection/core/box_list_ops.py

`with tf.name_scope(scope, 'ToAbsoluteCoordinates'):
    height = tf.cast(height, tf.float32)
    width = tf.cast(width, tf.float32)

    # Ensure range of input boxes is correct.
    check_range=False`
    
you might need to rerun the following block to make sure your changes took place

`import sys,os,os.path
#manual step - hard coded issue
! cd  ../ && {sys.executable} setup.py build && {sys.executable} setup.py install && chmod 777 slim && cd slim && ! sudo {sys.executable} -m pip install -e . && ! echo 'done' && ! ls `



# Resource:

1. [Provision the Data Science Virtual Machine for Linux (Ubuntu)](https://docs.microsoft.com/en-us/azure/machine-learning/data-science-virtual-machine/dsvm-ubuntu-intro)
