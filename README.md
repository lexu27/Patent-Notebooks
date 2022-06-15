# Patent Code
## _The Last Markdown Editor, Ever_


## Reading order

- BERT
- Electra
- XLNET

## Some important Notes
> XLNet has a different tokenizer than BERT and Electra. Its CLS token is at the end and all inputs are right padded.
> The XLNet file has two versions of XLNet. The one I used for ensembling is the base XLNet. Large XLNet is also there because I've tried to train it uncessfully...
> **Both BERT and XLNet seem to be unstable. Successful training is likely due to lucky learning rates and training data...**

## Current Attempts to fix the above problems and increase performance (ranked in order of priority)

| Ideas | Approach |
| ------ | ------ |
| BERT is unstable due to poor training data | Parse all chemical formulas (nacl = Sodium...) May even retrain all models on this new training data|
| BERT is unstable due to poor output specification | A sigmoid doesn't seem to be good enough. Let's go with ordinal regression: https://arxiv.org/pdf/1901.07884.pdf |
| I'm doing something wrong with my folds | Try a voting ensemble instead, or retrain all models (hopefully not) |
| Not enough data | Scour the internet for more training data and look for online labels. Might honestly go train a KMeans network for unsupervised labeling. Will take time, but I've pulled allnighters before|
| Pearson Loss is implemented incorrectly... | Most likely not the case, but could be a possibility... |
| Pearson Loss doesn't have smooth gradients | Most likely not the case, but could be a possibility. Maybe Cross Validation or negative log liklihood would work better???? |
| Poor ensembling | Requires retraining all models, reserving an extra part of the training set for ensemble preparation, but could lead to better performance. Training a weighted ensemble the way it is currently is a shitty idea since models will overfit |
