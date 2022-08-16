---
timeToRead: 0
authors: []
title: Obj
excerpt: ''
date: 
hero: ''
draft: true

---
# Pi setup

##### Show your Raspberry Pi OS version.

cat /etc/os-release

##### Update packages on your Raspberry Pi OS.

sudo apt-get update

##### Check your Python version. You should have Python 3.7 or later.

python3 --version

##### Install virtualenv and upgrade pip.

python3 -m pip install --user --upgrade pip
python3 -m pip install --user virtualenv

##### Create a Python virtual environment for the TFLite samples (optional but strongly recommended)

python3 -m venv \~/tflite

##### Run this command whenever you open a new Terminal window/tab to activate the environment.

source \~/tflite/bin/activate

##### Clone the TensorFlow example repository with the TFLite Raspberry Pi samples.

git clone https://github.com/tensorflow/examples.git
cd examples/lite/examples/object_detection/raspberry_pi

##### Install dependencies required by the sample

sh setup.sh

##### Run the object detection sample

##### **IMPORTANT**: If you SSH to the Pi, make sure that:

##### 1. There is a display connected to the Pi.

##### 2. Run `export DISPLAY=:0` before proceeding to make the object_detection window appear on the display.

python detect.py

##### If you see an error running the sample:

# Windows setup

sudo apt-get install libatlas-base-dev

C:\\Users\\Owner\\AppData\\Local\\Temp\\CUDA

[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-downloads "https://developer.nvidia.com/cuda-downloads")

[https://www.tensorflow.org/install/source#gpu](https://www.tensorflow.org/install/source#gpu "https://www.tensorflow.org/install/source#gpu")

[https://developer.nvidia.com/cudnn-download-survey](https://developer.nvidia.com/cudnn-download-survey "https://developer.nvidia.com/cudnn-download-survey") extract