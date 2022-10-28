<h1 align="center"> Music Recommendation System using Deep Reinforcement Learning  </h1>
<p align="center">
  <img width="460" height="300" src=other/music_recommend.png>
</p>


## Overview

To build Music Recommender with the capability to handle a large number of discrete actions (e.g. millions of songs in database), I implemented the model Deep Deterministic Policy Gradient (DDPG)

The algorithm DDPG has the ability to simultaneously learn a policy and a Q-function. To simulate the sequential interactions between users and the recommender system, DDPG uses an actor-critic framework. Actor network produces a policy function that assesses all music and then recommends the top three songs with the highest scores for the user based on the songs that a user has been listening to in a listening session. The Q-value function, which determines if a song's selection matches the user's recent behavior, is then learned by Critic Network using approximation. The Actor network modifies its policy parameters in response to the Critic network's assessment to enhance recommending performance in subsequent iterations.

<p align="center">
  <img width="400" height="330" src=other/ddpg.png>
</p>

## Evaluation

To measure Music Recommender's performance offline, I tracked multiple metrics such as music diversity and song skip rates. Compared to the original methods used in the dataset, it recommends a more diverse selection of music (9.3 % vs 7.6%) and also better identifies songs that are skipped by users (49% vs 54%).

## Limitations

One major impediment of applying reinforcement learning to recommender system is the lack of simulation platforms for sequential user interactions. This makes the full evaluation of Music Recommender difficult, especially when it comes to reasoning about ordering of songs in a playlist.

## Example usage

```
cd src
from main import *
run('../data/user_mini_data.tar.gz', '../data/music_mini_data.tar.gz')
```

## Data

I built the project based on a real-world dataset from Spotify. As entire dataset is very large (e.g. 130 million listening sessions), I will not store it here on github. If you are interested, please check out their website [https://www.aicrowd.com/challenges/spotify-sequential-skip-prediction-challenge](https://www.aicrowd.com/challenges/spotify-sequential-skip-prediction-challenge).

## Inspiration

1 [https://arxiv.org/abs/1801.00209](https://arxiv.org/abs/1801.00209)

2 [https://github.com/egipcy/LIRD](https://github.com/egipcy/LIRD)

3 [https://github.com/luozachary/drl-rec](https://github.com/luozachary/drl-rec)
