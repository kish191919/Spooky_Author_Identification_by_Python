# Spooky_Author_Identification
This is a competition to identify an auther from sentences which they wrote.

This project follows the instructions of a Kaggle competition during the Halloween of 2017.

The link of the competition is https://www.kaggle.com/c/spooky-author-identification

### Data description
The competition dataset contains text from works of fiction written by spooky authors of the public domain: Edgar Allan Poe, HP Lovecraft and Mary Shelley. The data was prepared by chunking larger texts into sentences using CoreNLP's MaxEnt sentence tokenizer, so you may notice the odd non-sentence here and there. Your objective is to accurately identify the author of the sentences in the test set.

### Files
train.csv - the training set

test.csv - the test set

sample_submission.csv - a sample submission file in the correct format

### Evaluation
Submissions are evaluated using multi-class logarithmic loss. 

Each id has one true class. For each id, need to submit a predicted probability for each author. 

The formula is then:

$log loss = -\frac{1}{N}\sum_{i=1}^N\sum_{j=1}^My_{ij}\log(p_{ij})$

### Data fields
id - a unique identifier for each sentence

text - some text written by one of the authors

author - the author of the sentence (EAP: Edgar Allan Poe, HPL: HP Lovecraft; MWS: Mary Wollstonecraft Shelley)

A reminder about playground competitions: On Kaggle, the spirit of playground competitions is to have fun and learn together. Your score on the leaderboard doesn't earn you points, but you can still make it a rewarding competition for everyone by sharing your code in Kernels and contributing to Discussions (there are prizes for both!). In short, please don't look up the answers.


### Evaliation:

Random Forest:
```
Training Score: 0.43107505964550397
Confusion Matrix:
 [[7844    2   54]
 [5459   98   78]
 [5301    3  740]]
 10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.42      0.99      0.59      7900
          1       0.95      0.02      0.03      5635
          2       0.85      0.12      0.21      6044

avg / total       0.71      0.44      0.31     19579

```
AdaBoost:
```
Training Score : 0.6292977254067664
Confusion Matrix:
 [[7301  311  288]
 [2875 2627  133]
 [2858  203 2983]] 
 10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.56      0.92      0.70      7900
          1       0.84      0.47      0.60      5635
          2       0.88      0.49      0.63      6044

avg / total       0.74      0.66      0.65     19579

```
Support Vector Machine:
```
Training Score : 0.40349420090683086
Confusion Matrix:
 [[7900    0    0]
 [5635    0    0]
 [6043    0    1]]
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.40      1.00      0.58      7900
          1       0.00      0.00      0.00      5635
          2       1.00      0.00      0.00      6044

avg / total       0.47      0.40      0.23     19579

```
Naive Bayes classification :
```
Training Score : 0.8329333739756135
Confusion Matrix:
 [[7414  110  376]
 [ 631 4764  240]
 [ 588   89 5367]] 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.86      0.94      0.90      7900
          1       0.96      0.85      0.90      5635
          2       0.90      0.89      0.89      6044

avg / total       0.90      0.90      0.90     19579
```
### Prediction

Model : Naive Bayes classification

Kaggle Score : 0.48767

Kaggle rank : 793 / 1244 (63.7%) [2018.4.5] 



