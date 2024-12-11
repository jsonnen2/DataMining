
## Data:

A web scraping of Steam reviews by Mohamad Tarek yielded this dataset. The data describes review messages left by
Steam community members across 290 games. I use a Natural Language Processing library, TextBlob, to produce
sentiment scores and length measurements. I use these features to predict if a user recommends a game (binary) and
the number of hours that the user played that game. 

Data can be found at:
https://www.kaggle.com/datasets/mohamedtarek01234/steam-games-reviews-and-rankings 

    
## Discussion:

- classifier comparison
- feature subsets. 
- final performance 

## File structure:

- **`eval_on_test_set.py`**
    Evaluation on the test set across my 3 different groups of experiments. I ran KNN to predict hours played,
    Random Forest to predict hours played, and Random Forest to predict recommendation.
- **`run_knn.py`** 
    This file runs my K Nearest Neighbors classifier on my data using
    several feature subsets, target discretization methods, and hyperparameter choices. 
    The script will generate _log files which stores data about classifier performance compared
    with the majority classifier.
- **`run_random_forest.py`**
    Same functionality of run_knn.py but uses sklearn's random forest to classify. 
    Also pulls sklearn metrics, which I will be using going forward. Saved in a standard format
    to my _log folder.
- **`log_analyze.py`**
    Iterates through my _log files and calculates summary statistics. Most importantly, this script
    performs the t-test to test if my classifier is significantly better than the majority class
    baseline. Saves a summary file averaged over 30 runs. Allows for t-test analysis. 
- **`log_query.py`**
    Every analysis of my _log files is here. Each method creates a table or histogram that I use
    in my slides. 
- **`log_rename.py`**
    Renames many _log files all at once. Written by ChatGPT
- **`plot_squiggle.py`**
    A plot for visualizing 1D cluster groups. Each cluster border is represented with an edge. Higher
    sloped lines show tigher cluster groups. Each line uses a different linestyle to appeal to color
    blinded individuals.
- **`plot_categorized_lines.py`**
    The best plot for comparing differences between classifiers. I can grouby any attribute then plot
    the distribution of t scores. I have a dashed line to represent the median, which is an unbiased
    estimator. I also have the option for representing certain features with shapes. 
- **`classifier.py`**
    My implementation of the K Nearest Neighbors and Naive Bayes algorithms.
- **`decision_tree.py`**
    My implementation of the Decision Tree classification algorithm.
- **`random_forest.py`**
    My implementation of a Random Forest. I use an ensembling of Decision Trees to achieve a Random Forest. 


## Dependencies:
    matplotlib==3.9.2
    numpy==2.1.3
    pandas==2.2.3
    scikit_learn==1.5.2
    scipy==1.14.1
    tyro==0.8.6



