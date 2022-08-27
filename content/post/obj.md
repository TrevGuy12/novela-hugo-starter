---
timeToRead: 1
authors: []
title: Obj
excerpt: ''
date: 
hero: ''
draft: true

---
![](/images/speedbase.gif)

![](/images/speedconnect.gif)

![](/images/together.gif)

![](/images/printbed.gif)

## Pi setup (if you are running ML on a remote machine)

[https://makerslabntu.wordpress.com/2015/08/22/how-to-use-raspberry-pi-to-control-a-servo-via-the-web/](https://makerslabntu.wordpress.com/2015/08/22/how-to-use-raspberry-pi-to-control-a-servo-via-the-web/ "https://makerslabntu.wordpress.com/2015/08/22/how-to-use-raspberry-pi-to-control-a-servo-via-the-web/")

```js
curl -sL https://deb.nodesource.com/setup_10.x | sudo bash 
sudo apt install nodejs
node --version
```

```js
mkdir myServo
cd myServo
```

```js
npm init
npm install express --save
npm install connect --save
```

```js
cd ..
git clone https://github.com/sarfata/pi-blaster.git
cd pi-blaster

sudo apt-get install autoconf
./autogen.sh
./configure
make
sudo make install
```

to make it stop holding on to your pin

```js
sudo make uninstall
```

setup an api so we can control the servo remotely

```js
cd ..
cd myServo
npm install pi-blaster.js --save

touch api.js
```

```js
var http = require('http');
var express = require('express');
var piblaster = require('pi-blaster.js');
 
var app = express();
// ------------------------------------------------------------------------
// configure Express to serve index.html and any other static pages stored 
// in the home directory
app.use(express.static(__dirname));
 
//try a simpler rest get call
app.get('/hello', function(req, res) { 
       console.log("hello");
 });
 
//lock rest get call
app.get('/lock', function(req, res) { 
       piblaster.setPwm(22, 0.145);
       res.end('Box is locked');
 });
 
//unlock rest get call
app.get('/unlock', function(req, res) { 
       piblaster.setPwm(22, 0.1);
       res.end('Box is unlocked');
 });
 
 
// Express route for any other unrecognised incoming requests
app.get('*', function (req, res) {
       res.status(404).send('Unrecognised API call');
});
 
// Express route to handle errors
app.use(function (err, req, res, next) {
 if (req.xhr) {
       res.status(500).send('Oops, Something went wrong!');
 } else {
       next(err);
 }
}); // apt.use()
 
 
//------------------------------------------------------------------------
//on clrl-c, put stuff here to execute before closing your server with ctrl-c
process.on('SIGINT', function() {
 var i;
 console.log("\nGracefully shutting down from SIGINT (Ctrl+C)");
 process.exit();
});
 
// ------------------------------------------------------------------------
// Start Express App Server
//
app.listen(3000);
console.log('App Server is listening on port 3000');
```

Now on the remote machine (not the pi)

http://10.0.0.188:3000/lock

http://10.0.0.188:3000/unlock

# Colab ML object detection training

This is way too much code for a blog post, please see the Google colab link for all the python code. Google colab is a virtual server that lets you rent large servers for doing machine learning without the need of installing and running computation on your local computer. Each section has comments to see what each section is doing.

[https://colab.research.google.com/drive/1Z-RLCOF84MKWxkIK48kuSJCWGhzLbf07#scrollTo=LipVYmJHYJPz](https://colab.research.google.com/drive/1Z-RLCOF84MKWxkIK48kuSJCWGhzLbf07#scrollTo=LipVYmJHYJPz "https://colab.research.google.com/drive/1Z-RLCOF84MKWxkIK48kuSJCWGhzLbf07#scrollTo=LipVYmJHYJPz")

![](/images/capture.PNG)

# Pi setup (if you are running ML on pi)

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