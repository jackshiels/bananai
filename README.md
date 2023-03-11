# Bananai 🍌
🤖 A deep learning project to detect the ripeness of bananas using an Arduino 🤖

# Why apply Artificial Intelligence (AI) to bananas?
AI is everywhere. From search bots, to cars, to marketing services - the age of AI is upon us. However, one final frontier; one last bastion of the unknown; one uncharted territory remains untested by the capabilities of deep learning. This untouched subject matter: the humble banana 🍌

Bananas are a classic fruit. Undeniably unique, these yellow friends have blessed humankind with what could be the most user-friendly fruit experience. Easy-to-hold, hangable, and coming with their own wrapper, bananas invite our attention. They deserve it, too.

However, beneath this friendly veneer is a much darker secret: bananas don't like to be ripe. They fight our attempts to consume by sneakily overripening when we least expect it. Who among us hasn't rushed to the train station, giant yellow banana in hand, only to feel the deep, dark, hollow pain of biting into a mushy abomination of the natural world. No more.

Bananai is the application of deep learning to banana ripeness, using image recognition to determine when a banana is best to eat. In combination with an Arduino BLE 33 Sense, Bananai is deployed on a banana stand to provide an immediate indication of when to consume. No more embarassment. No more pain.

The following readme describes how Bananai came to be, and outlines the steps taken in its development. Instructions on how to deploy are also provided.

# Project Process

Several steps were taken to design Bananai. These steps included:

* Decide on a model architecture
* Decide on a data architecture
* Gather images of bananas
* Clean and format images of bananas
* Construct a model on Edge Impulse
* Deploy the model to an Arduino BLE 33 Sense
* Build an enclosure
* Construct the final device on a banana holder

# Findings

* Increasing the number of images with transfer learning didn't appear to help accuracy.
* Moving into the 160x160 models caused a loss of accuracy.
