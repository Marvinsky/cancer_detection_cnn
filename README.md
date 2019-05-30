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

## Validation set:

![Ilustration](/img/validation_set.png)


## Evaluation Metrics:

We already use precision and recall. However, in Medicine, doctors use sensitivity/specificity.

## Question:

What's the relation between sensitivity/specificity and recall/precision? ([Precision and recall](https://en.wikipedia.org/wiki/Precision_and_recall))


Let's define:

# Sensitivity:
Of all the sick people, how many did we diagnose as sick?

# Specificity:
Of all the healthy people, how many did we diagnose as healthy?

## Sensitivity and Specificity

Sensitivity and Specificity are not the same as Precision and Recall.

# In the case of cancer:

  . Sensitivity: Of all the people with cancer, how many were correctly diagnose?
  
  . Specificity: Of all the people without cancer, how many were correctly diagnose?
  
# Precision and recall are the following:

  . Recall: Of all the people who have cancer, how many did we diagnose as having cancer?
  
  . Precision: Of all the people we diagnose with cancer, how many actually had cancer?
  
Sensitivity and Recall are the same and Specificity and Precision are not the same thing.

![confusion matriz](/img/confusion_matriz.png)

Sensitivity and specificity are rows of this matrix. More specifically, if we label:

  . TP: (True Positives) Sick people that we correctly diagnose as sick.
  
  . TN: (True Negatives) Healthy people that we correctly dianosed as healthy
  
  . FN: (False Positives) Healthy people that we incorrectly diagnosed as sick.
  
  . FN: (False Negatives) Sick people that we incorrectly diagnosed as healthy
  
Sensitivity = TP/(TP + FN)

Specificity = TN/(TN + FP)

![confusion matriz](/img/confusion_matriz_s_s.png)

Precision and recall are the top row and left column of the matrix.

Recall = TP/(TP + FN)

Precision = TP/(TP + FP)

![confusion matriz](/img/confusion_matriz_p_r.png)

## Question:

Say we have a neural network that outputs the probability of a melanoma. What value would you choose as a threshold to classify this as melanoma or no melanoma?

  . 0.2%
  . 0.5%
  . 0.8%
  
If we have chosen 0.5% then your chances of accidentally missing a cancer are exactly the same as your chances of calling something a cancer that isn't.

If we use 0.8% we will be great reducing the cost of dianostics, but bad in helping people survive when they actually have skin cancer. 

0.2% is the number we would choose from these numbers, because of the asymmetry of cost of the regret. If you find that a person has been sent to the lab but the tissue was not cancerous, you have a regret, discomfort in getting skin extracted and there's a cost to the lab test, but the regret is small. If you conversely you overlook a cancer because you've been just too cheap to send the person to the lab, then this person might die. And that's a much, much bigger cost.

So, 

  . At 0.2, we classify every malignant lesion correctly, yet we also send a lot of benign lesions for more testing.

  . At 0.5, we miss some malignant lesions (bad), and we send a few benign lesions for more testing.

  . At 0.8, we correctly classify most of the benign lesions, but we miss many malignant lesions (very bad).
 
![threshold](/img/threshold.png)
