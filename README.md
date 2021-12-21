# Detect faces in video and images with OpenCV
## Table of Contents
* [Introduction](#introduction)
* [Technologies](#technologies)
* [Usage](#usage)
  * [Adjusting Model Sensitivity](#adjusting-model-sensitivity)
* [How it works](#how-it-works) 
* [Author](#author-/--zachary-seitz)

## Introduction
The goal was to utilize some common data science tools and explore a few different deployment methods for ML models. I utimately settled on a Jupyter Notebook deployed using Binder.

## Technologies
* Python
* Binder
* Jupyter notebooks
* Ipywidgets
* Numpy
* PIL/pillow

## Usage

## How it works

# A bit about image modes and pixels
  An image's *mode* determines how the image pixels are represented to the computer.

  Very generally speaking, a typical color image will be in the red-green-blue mode, or RGB for short. This means that each pixel is composed of three numbers, called *channels* (in this case, one channel for each color). These channel values range from 0 to 255. So a pixel with values (255, 0, 0) is a red pixel. A pixel with (255, 0, 255) has maxed red and blue channel values, so it would be a purple pixel.

# The Haar cascasde
  To understand how the Haar cascade actually operates on the image, imagine using a magnifying glass to read a newspaper. At first, you can't read any words, but you can faintly make out shapes of words, so you bring the magnifying glass closer. Now you can read just the big words—the headings and so on. Finally, you move closer and can read all the words becuase you've 'resized' the image within the magnifying glass. The Haar cascade kind of works like this; it uses what's called a sliding window approach. This means it checks for faces within the reading window (i.e. inside the magnifying glass) as it slides the reading window across the image, marking any faces it finds along the way. It then resizes the image (i.e. moves the magnifying glass) and scans through the image again.

  The accuracy and speed of the sliding window is affected by some important parameters: scale factor and minimum neighbors. Scale factor determines how much the image is resized at each step of the cascasde. Practically, this allows the cascade to detect faces of different sizes if say, one person is really close to camera while everyone else is far away. Higher scale factors allow for faster detection, but make for less sensitive classifiers.

  As you can imagine, the cascade can also detect all sorts of stuff that isn't a face, so this minimum neighbors parameter helps filter out the noise. If the cascade counts the same object as a face each time it passes, there's a better chance it's an actual face rather than a false positive. We call these detections *neighbors* if the detections include the same pixels. The more neighbors a hit has, the more likely it is to be a face. Practically, a higher minNeighbors value means fewer faces are likely to be detected, but it also typically results in fewer false positives.

# Further reading
- OpenCV Haar cascade: https://docs.opencv.org/3.4/db/d28/tutorial_cascade_classifier.html

## Author
### Zachary Seitz
#### Let's connect!
* Find me on [Linkedin](https://linkedin.com/in/zachmichael14).
* Email me at zachmichael14@gmail.com.
* Visit my [website](https://zachmichael14.github.io/gh_page/).
