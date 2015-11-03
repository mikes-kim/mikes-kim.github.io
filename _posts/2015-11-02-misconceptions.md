---
layout: default
title: "First hand experience"
date: 2015-11-02
---

I'm just going to list a few (vague) things I believe you have to experience first hand (even if theoretically justified or not) in ML. Obviously I could write many blog posts on each statement regarding both the theory and practice and edge cases, but for now I'll just leave it here. You don't have to believe me - most secrets are just out in the open:
1) More data is better than fancy algorithms.
2) Feature engineering is better than tuning (or usually algorithms).
3) Ensembling is usually better than tuning.
4) If you have a lot of rows (billions) of training data, it's probably okay just to hash (one hot) the features.
5) Your hardware won't save you when the algorithm has time complexity of O(n^2) and you have trillions of rows (it's 2015 right now).
6) It's better to use all the data when you can versus sampling. Perhaps weighted resampling is the way to go here.
7) Bag it when it's possible to bag. It usually works - even if you have millions of rows. 
8) When using FTRLP shuffle your rows, and ensemble with other orderings (maybe by date?).
9) I think feature engineering without looking at ground truth is best (like TSNE), but if you have to look at ground truth do it out of fold/bag and try not to leak.
10) As for algos, I think the basic (highly undefendable) order I try things is XG(GBM)/ANN > RGF > RF > SGD/FTRLP/GLMNET > GP/SVM . Any claim that it doesn't matter is fundamentally false in the sense that you can't apply a GP/SVM when data is big. 
