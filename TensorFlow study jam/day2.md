# Welcome to tensorflow study Jam: day 2 !


## Representation

### Feature engineering
It means transforming raw data into a feature vector. 

Consider this dataset,

| Super hero     | Age   | Capabilities                     | Avengers cofounder|Snapified|
|----------------|-------|----------------------------------|-------------------|---------|        
| Iron man       | 48    | Flying, weapon making, tech.     |     Yes           |    No   |
| Dr. Strange    | 42    | Teleporting,weapon making, magic |     No            |    Yes  |
| Spiderman      | 18    | Webbing, spidersense,strength    |     No            |    Yes  |
| Captain America| 100   | Strength, fighting skills,fast   |     Yes           |    No   |  
| Black Panther  | 42    | Rich, fighting skills, tech,fast |     No            |    Yes  |
| Bruce Banner   | 49    | (in)ability to turn into hulk    |     Yes           |    No   |

Many machine learning models must represent the features as real-numbered vectors since the feature values must be multiplied by the model weights.


- **Integer and floating-point data** don't need a special encoding because they can be multiplied by a numeric weight.

- **Categorical values** have a discrete set of possible values. For example, there might be a feature called **Capabilities** with options that include:

[fast, fighting skills, flying, inability to turn into hulk, magic, Rich, Strength, Spidersense, tech, teleporting, webbing, weapon making]

One hot encoding for ironman : [0,0,1,0,0,1,0,0,1,0,0,1]


| Super hero     | Age   | Capabilities                     | Avengers cofounder|Snapified|
|----------------|-------|----------------------------------|-------------------|---------|        
| Iron man       | 48    | [0,0,1,0,0,1,0,0,1,0,0,1]        |     1             |   0     |
| Dr. Strange    | 42    | [0,0,0,0,1,0,0,0,0,1,0,1]        |     0             |   1     |
| Spiderman      | 18    | [0,0,0,0,0,0,1,1,0,0,1,0]        |     0             |   1     |
| Captain America| 100   | [1,1,0,0,0,0,1,0,0,0,1,0]        |     1             |   0     |
| Black Panther  | 42    | [1,0,1,0,0,1,0,0,1,0,0,0]        |     0             |   1     |
| Bruce Banner   | 49    | [0,0,0,1,0,0,0,0,0,0,0,0]        |     1             |   0     |

In **Sparse representation** only nonzero values are stored. In sparse representations, an independent model weight is still learned for each feature value, as described above.


### Qualities of Good features

- Avoid rarely used discrete feature values (power of Banner).
- Prefer clear and obvious meanings (Age of Thor).
- Don't mix "magic" values with actual data (the case of hawkeye).
- Account for upstream instability (different names of powers, for eg: "get help").

## Data Cleaning
- Scaling.
- Handling extreme outliers.
- Binning
- Scrubbing

## Faeture Crossing

A feature cross is a synthetic feature that encodes nonlinearity in the feature space by multiplying two or more input features together. 

## Classification

A logistic regression model that returns 0.9995 for a particular email message is predicting that it is very likely to be spam. Conversely, another email message with a prediction score of 0.0003 on that same logistic regression model is very likely not spam.

**True positive** is an outcome where the model correctly predicts the positive class.
**True negative** is an outcome where the model correctly predicts the negative class.

**False positive** is an outcome where the model incorrectly predicts the positive class. 
**False negative** is an outcome where the model incorrectly predicts the negative class.

### Accuracy
```
Accuracy = Correct predictions/total predictions
         = (TP+TN)/(TP+TN+FP+FN)
```
### Precision
```
precision = TP/(TP+FP)

```

### Recall

```
Recall = TP/(TP+FN)
```

