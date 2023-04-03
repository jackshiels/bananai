
![alt text](https://github.com/jackshiels/bananai/blob/main/GitImages/bananai_header_git_small.jpg?raw=true)

# Bananai 🍌
🤖 A deep learning project to detect the ripeness of bananas using an Arduino 🤖

# Why apply Artificial Intelligence (AI) to bananas?
Artifical Intelligence (AI) is everywhere. From search bots, to cars, to marketing services, AI is experiencing a profound and significant moment in the Zeitgeist. The unregulated and unknown power of tools such as ChatGPT has led to many industry figures calling for a halt to further innovation to prevent catastrophic consequences (Narayan, Hu, &, Mukherjee, 2023). While such tools are immensely complex and almost impossible to reproduce in civilian hands, specific and targeted domain-level AI solutions can be trained and deployed by novice. Hence, this student project chose a unique domain to attach AI to: that of the banana 🍌.

Bananas are an instantly recognisable fruit. Undeniably unique, bananas are easy-to-hold, hangable, and coming with their own protective wrapper. Bananas, like many other fruit, provide value from their ripeness and availability to eat, which diminishes over time (Rizzo et al., 2023). As such, it becomes important for both supply chain efficiency and personal consumption to know when a banana is at the ideal point to eat.

Bananai is the application of deep learning to banana ripeness, using image recognition to determine when a banana is best to eat. In combination with an Arduino BLE 33 Sense, Bananai is deployed on a banana stand to provide an immediate indication of when to consume. The following readme describes how Bananai came to be, and outlines the steps taken in its development. Instructions on how to deploy are also provided.

# Research question
Given the need for a way to detect banana ripeness, the following research question was determined:

*Can we use an onboard, transfer learning model on an Arduino to understand when bananas become overripe, and how much training data do we need for an acceptable accuracy level (> 90%)?*

A project outline is provided below.

# Project outline
Several steps were taken to design Bananai. These steps included:

* Deciding on the physical and software/AI architecture.
* Gathering images.
* Processing and transforming images.
* Iterative model training and data gathering.
* Design of the software to deploy on Arduino.
* Construction of the physical device.
* Deployment and testing.

# Deciding on the physical and software/AI architecture
BananAI was split into two architectures: software (AI) and hardware.

## Software
Transfer learning is an AI model architecture that uses large, existing models to act as a basis for the training of smaller collections of domain-specific data (Tensorflow, 2022). Transfer learning was a good choice for BananAI, as it doesn't necessitate the gathering of thousands of images of bananas.

This AI model would be trained on Edge Impulse. Edge Impulse is a Platform-as-a-Service (PaaS) for training and deploying AI models on a variety of hardware (including Arduinos). Edge Impulse is streamlined and easier to use for fast iteration of Arduino-focused AI models, as it can deploy to these devices easily.

# Findings
* Increasing the number of images with transfer learning didn't appear to help accuracy.
* Moving into the 160x160 models caused a loss of accuracy.

# References
Arduino.cc (n.d.). Nano 33 BLE Sense. Available at: https://docs.arduino.cc/hardware/nano-33-ble-sense (accessed 13 March 2023).

Narayan, J., Hu, K. and Mukherjee, S. (2023). Elon Musk and others urge AI pause, citing 'risks to society'. Available at: https://www.reuters.com/technology/musk-experts-urge-pause-training-ai-systems-that-can-outperform-gpt-4-2023-03-29/ (accessed 3 April, 2023).

Rizzo, M., Marcuzzo, M., Zangari, A., Gasparetto, A. and Albarelli, A. (2023). ‘Fruit ripeness classification: A survey’, Artificial Intelligence in Nature, 7, pp. 44-57. doi: 10.1016/j.aiia.2023.02.004

Tensorflow (2022). Transfer learning and fine-tuning. Available at: 
https://www.tensorflow.org/tutorials/images/transfer_learning (accessed 20 March 2023).
