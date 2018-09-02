# Age_gender
The Adience dataset [35] consists of 26,580 images of faces. 
A total of 2,284 subjects (people) were captured in this dataset. 
The dataset was then split into two gender classes (male and female) along with eight age groups; 
specifically: 0-2, 4-6, 8-13, 15-20, 25-32, 38-43, 48-53, and 60+. 
The goal of the Adience dataset is to correctly predict both the age and the gender of a given person in a photo
The dataset is imbalanced with more samples being present for people in the age brackets 25 − 32 than than any other age group by a factor of two (4,897).
Samples in the age ranges 48 − 53 and 60+ are the most unrepresented (825 and 869, respectively).
The number of male samples (8,192) is slightly lower than the number of female data points (9,411), but is still within reasonable limits of class distribution.
When training a model on the Adience dataset, we have two choices:
1. Train a single classifier that is responsible for predicting both the gender and age classes, for
a total of 16 possible classes.
2. Train two classifiers, one responsible for predicting gender (2 classes) and a separate model
for age recognition (8 classes).
Both methods are viable options; however, we are going to opt for taking the approach of Levi
et al. and train two separate CNNs – not only will doing so enable us to reproduce their results (and even outperform their reported accuracies), but it will enable our classifier to be more robust.
The facial features learned to discriminate a 60+ woman are likely extremely different than the features learned to recognize a man who is also 60+;
therefore, it makes sense to separate age and gender into two separate classifiers.
