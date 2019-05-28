# skin_cancer_detection_cnn

### Questions: 

What is the 5-year survival rate for stage 4 melanoma?

15-20%

What is the 5-year survival rate for stage 0 melanoma?

99-100%

### Ilustrations of the stages:

![Diagram](/img/diagram.png) ![Ilustration](/img/ilustration.png)

### Classifying Melanomas is a very hard problem.
1.- Some people have lot of moles.

2.- Find one malignant mole is really hard.

3.- Dermatologist are extremely highly trained to find melanomas and carcinomas.


## International Dataset.
Students in collaboration with the School of Medicine collected roughly 130000 images of skin conditions. However, it is not already classified as cancer o not cancer. So, they had to create a manual classification tree with all the diseases in order to clean up the data. 

![Diagram](/img/tree_diseases.png)

Based on the enormous amount of data that needs to be processed, CNN is a good candidate because the neural network can process hundreds of thousands of images as many human doctors can never study as many as you can feed into a neural network. 


## The Students had to clean up the data and they faced the following challenges:

1.- Duplicates

2.- Variable resolution

3.- Variable lighting 

4.- Big yellow markers


## Architecture:

The architecture is taken from google: Recurrent Convolutional Neural Network (Inception-v3)

![RCNN](/img/recurrent_cnn.png)

## Question:

Do you think that pretraining the network with completely different images like cats, dogs, horses, and cars, made cancer classification better, the same, or worse?

Better... (Interesting, huum?)








