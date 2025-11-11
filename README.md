# Hybrid Traditional + AI Pipeline

This README explains each section of the MATLAB script that combines a traditional segmentation step with a CNN classifier. 

## Section 1: Load Image and AI Network

Loads the sample image `peppers.png`, initializes the pre trained SqueezeNet model, and opens a figure that shows the original image in the first subplot. This sets up both inputs: the raw image and the classifier that will later receive a focused crop. 

## Section 2: Traditional Method (Color Segmentation with K-Means)

Converts the image to Lab color space, clusters the a and b channels into two groups using `imsegkmeans`, and builds a binary mask from one cluster. The mask is applied to the original image to isolate the main object, which is then displayed. This is the classical preprocessing step that reduces background clutter. 

## Section 3: AI Method (Image Classification)

Resizes the isolated object to SqueezeNet’s required input size and runs `classify` to obtain the predicted label and class probabilities. This uses the learned features of a CNN to recognize the object. 

## Section 4: Results Analysis

Shows the resized input in the final subplot and prints the top prediction and its confidence. The script’s rationale is that focusing on the segmented region helps the classifier attend to the object of interest. 

<img width="1560" height="920" alt="Hybrid Pipeline Images" src="https://github.com/user-attachments/assets/ad3312c1-cc22-44f6-9dbb-d395dac224ee" />
