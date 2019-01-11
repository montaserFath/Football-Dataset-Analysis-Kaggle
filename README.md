# Football-Dataset-Analysis-Kaggle

# Objective

- Build a model to predict the number of goals in a match according to match events.

# [Kaggle Data-Set](https://www.kaggle.com/secareanualin/football-events/home)

- The dataset provides a granular view of 9,074 games, totaling 941,009 events from the biggest 5 European football (soccer) 
leagues: England, Spain, Germany, Italy, France from 2011/2012 season to 2016/2017 season. 

- There are games that have been played during these seasons for which I could not collect detailed data. Overall,
over 90% of the played games during these seasons have event data.

## The dataset is organized in 3 files:

- events.csv contains event data about each game.

- ginf.csv contains metadata and market odds about each game

- dictionary.txt contains a dictionary with the textual description of each categorical variable coded with integers.

# Data Understanding

- Event type: Corner, Foul, Substitution, Red card, Yellow card, Hand ball, Offside, etc.

- Location: Centre of the box, Outside the box , Left side of the six yard box, Long range, etc.

- Shoot place: Too high, Bit Too high, Bottom left corner, Top centre of the goal , etc.

- shoot outcome: On target, OFF target, Blocked or Hit the bar.

# Data pre-processing

- Separate each event into home or away match according to data-set.

- Missing data: we put any missing data equal -1, because data have integers and zeroes values.

- One hot encoding Values.

- Labels: labels will be number of goals per match (home and away matches).

- Vectored: 5 features have been selected (6 features have been selected but I use side as anther ID to separate matches have
 the same ID match), In every match there 180 events (maximum number of events per match). so input is a 2-d array size
 (5 X 180), by vectorized it into 1-d array (1 X 900).

# Neural Network

- Recurrent Neural Network (RNN) as a classifier.

- The inputs will 2d-array has size (number of matches X Vectored features events).

- Labels: numbers of goal in a match.
 
- Output: prediction number of goals in this match (Float number we round it).

## Network structure

- Training data: Events of 2000 matches.

- Test data: Events of Events100 matches.

- accuracy: round(prediction)== label.

- Loss function: Mean Square Error (MSE).
 
 - Optimizer: Adam.

 -Device: CPU.
 
 ## Hyper-parameters
 
 - Batch size: 100
    
- Learning rate: 1e-3

- Weight decay: 1e-3

# Results

|  |  Home with one-hot | Away with one-hot | Home without one-hot | Away without one-hot |
| :---:         |     :---:      |   :---: |   :---: | :---: |
|**Accurcy** | 1.726 %| 2.27 % | 56.017 % | 60.937 % |
|**Training time (minutes)** | 84.06| 83.046  | 83.076 | 80.479 |


# Discussion 
