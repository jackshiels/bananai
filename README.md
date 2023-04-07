
![BananAI Header](https://github.com/jackshiels/bananai/blob/main/GitImages/bananai_header_git_small.jpg?raw=true)

# BananAI 🍌
🤖 A deep learning project to detect the ripeness of bananas using an Arduino 🤖

# Why apply Artificial Intelligence (AI) to bananas?
Artifical Intelligence (AI) is everywhere. From search bots, to cars, to marketing services, AI is experiencing a profound and significant moment in the Zeitgeist. The unregulated and unknown power of tools such as ChatGPT has led to many industry figures calling for a halt to further innovation to prevent catastrophic consequences (Narayan, Hu, &, Mukherjee, 2023). While such tools are immensely complex and almost impossible to reproduce in civilian hands, specific and targeted domain-level AI solutions can be trained and deployed by novice. Hence, this student project chose a unique domain to attach AI to: that of the banana 🍌.

Bananas are an instantly recognisable fruit. Undeniably unique, bananas are easy-to-hold, hangable, and coming with their own protective wrapper. Bananas, like many other fruit, provide value from their ripeness and availability to eat, which diminishes over time (Rizzo et al., 2023). As such, it becomes important for both supply chain efficiency and personal consumption to know when a banana is at the ideal point to eat.

BananAI is the application of deep learning to banana ripeness, using image recognition to determine when a banana is best to eat. In combination with an Arduino BLE 33 Sense, BananAI is deployed on a banana stand to provide an immediate indication of when to consume. The following readme describes how BananAI came to be, and outlines the steps taken in its development. Instructions on how to deploy are also provided.

# Research question
Given the need for a way to detect banana ripeness, the following research question was determined:

*Can we use an onboard, transfer learning model on an Arduino to understand when bananas become overripe, and how much training data do we need for an acceptable accuracy level (> 90%)?*

A project outline is provided below.

# Project outline
Ordered steps were taken to design BananAI. These steps included:

* Deciding on the physical and software/AI architecture.
* Gathering images.
* Processing and transforming images.
* Iterative model training and data gathering.
* Design of the software to deploy on Arduino.
* Construction of the physical device.
* Deployment and testing.

# Deciding on the physical and software/AI architecture
BananAI was split into two architectures: software (including AI) and hardware.

## Software
BananAI utilises Transfer Learning. Transfer learning is an AI model architecture that uses large, existing models to act as a basis for the training of smaller collections of domain-specific data, which can save time (Tensorflow, 2022). Transfer learning was a good choice for BananAI, as it doesn't necessitate the gathering of thousands of images of bananas.

The AI model would be trained on Edge Impulse. Edge Impulse is a Platform-as-a-Service (PaaS) for training and deploying AI models on a variety of hardware (including Arduinos) (Edge Impulse, 2022). Edge Impulse is streamlined and easier to use for fast iteration of Arduino-focused AI models, as it can deploy to these devices easily and utilises compression to make models compatible with low-memory devices.

## Hardware
![Arduino Nano 33 BLE Sense](https://github.com/jackshiels/bananai/blob/main/GitImages/nano.jpg?raw=true)

The device selected for this AI is the Arduino Nano 33 BLE Sense (Arduino.cc, n.d.). The Nano 33 BLE Sense is capable of running machine learning models with inputs from a camera shield, which would suit a live-classification of bananas. The device is also small and easy to deploy into an enclosure. However, it has several limitations in its specifications, which are:

* 256KB of SRAM.
* 1MB of storage.
* A 64Mhz processor.

These limitations constrained the complexity of the AI model, as will be described later in the readme.

# Data gathering
Banana ripeness is a sliding scale, and past research into this topic shows varying opinions on how to classify bananas. For example, Mazen and Nashat define four categories of classification for an Artificial Neural Network (ANN), based on the percentage value of brown spots and other features (2018). Marimuthu and Roomi used seven for a fuzzy model (2017). However, several studies settle on four categories (Rizzo et al., 2023): unripe, yellowish-green, mid-ripen, and overripe (Saragih & Emanuel, 2021).

A factor in classification is the limitations of the Arduino's memory, which is 256KB. Models with more categories proved too large for this device.

Images of bananas were initially split into three categories, being:

* Underripe.
* Ripe.
* Overripe.

Photos of bananas were captured on an iPhone 13 Pro in various positions, bunches of bananas, lighting circumstances, and with varying backgrounds. The data set can be obtained here. A selection of images is displayed below to illustrate the data set's diversity. 

![Arduino Nano 33 BLE Sense](https://github.com/jackshiels/bananai/blob/main/GitImages/banana_images_sample.jpg?raw=true)

Images were then transferred to a personal computer and converted from HEIC to JPG format. Following conversion, a batch image processing tool was used to transform images to 288x384 resolution. Images were then stored in ordered folders for ease of access. After some training, it was discovered that some images were classified incorrectly during the batch conversion process. These errors were remedied and the images were subsequently reorganised.

# Findings
* Increasing the number of images with transfer learning didn't appear to help accuracy.
* Moving into the 160x160 models caused a loss of accuracy.
* Adding final neurons and increasing the learning rate helped with accuracy at cost of overfitting.
* Banana features may be better represented in certain statistical models (Mazen & Nashat, 2018).
* Other models also have a hard time distinguishing between categories (Mazen & Nashat, 2018).

# References
Amazon (2023). *Model Fit: Underfitting vs. Overfitting*. Available at: https://docs.aws.amazon.com/machine-learning/latest/dg/model-fit-underfitting-vs-overfitting.html (accessed 1 April 2023).

Arduino.cc (n.d.). *Nano 33 BLE Sense*. Available at: https://docs.arduino.cc/hardware/nano-33-ble-sense (accessed 13 March 2023).

Edge Impulse (2022). *Getting Started*. Available at: https://docs.edgeimpulse.com/docs (accessed 7 April 2023).

Narayan, J., Hu, K. and Mukherjee, S. (2023). *Elon Musk and others urge AI pause, citing 'risks to society'*. Available at: https://www.reuters.com/technology/musk-experts-urge-pause-training-ai-systems-that-can-outperform-gpt-4-2023-03-29/ (accessed 3 April, 2023).

Rizzo, M., Marcuzzo, M., Zangari, A., Gasparetto, A. and Albarelli, A. (2023). ‘Fruit ripeness classification: A survey’, Artificial Intelligence in Nature, 7, pp. 44-57. doi: 10.1016/j.aiia.2023.02.004

Tensorflow (2022). *Transfer learning and fine-tuning*. Available at: 
https://www.tensorflow.org/tutorials/images/transfer_learning (accessed 20 March 2023).
