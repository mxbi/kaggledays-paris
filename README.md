# kaggledays-paris
Winning Solution to the Kaggle Days Paris offline competition

The competition can be seen here: https://www.kaggle.com/c/kaggledays-paris

## Solution

There are two notebooks, `nb1.ipynb` (raddar) and `nb2.ipynb` (anokas) - the first notebook generates a submission file as well as a dataframe of features. These features are then loaded into the second notebook, and they are used in addition to it's own feature engineering

The final solution is an ensemble of the submissions:

`submission = (nb1 * 0.25 + nb2 * 0.5 + nb2_without_nb1_features * 0.25) * 0.93`

The 0.93 constant is applied to the submission before uploading - this improves performance significantly as the test set tends to have fewer sales than the training set. This is an example of LB probing.

The code is somewhat messy due to the fast pace of the competition, which didn't allow time for any sort of code management or cleaning. I wouldn't hold my breath for the solution to be completely reproducible!
