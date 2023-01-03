<h1 align="center"> Music Recommendation System using Deep Reinforcement Learning  </h1>
<p align="center">
  <img width="460" height="300" src=other/music_recommend.png>
</p>


## Overview

To build a music recommendation system that can handle a large number of options (such as millions of songs in a database), I implemented the Deep Deterministic Policy Gradient (DDPG) algorithm. 

This algorithm has the ability to learn both a policy and a Q-function simultaneously. To simulate the interactions between the user and the recommendation system, DDPG uses an actor-critic framework. The actor network produces a policy function that evaluates all of the music and then recommends the top three songs with the highest scores based on the songs that the user has been listening to in a listening session. The Q-value function, which determines if a song selection matches the user's recent behavior, is then learned by the critic network using approximation. The actor network modifies its policy parameters in response to the critic network's evaluation to improve recommendation performance in subsequent iterations.

<p align="center">
  <img width="400" height="330" src=other/ddpg.png>
</p>

## Evaluation

To evaluate the performance of the music recommendation system, I tracked multiple metrics such as music diversity and song skip rates. The results showed that the system recommended a more diverse selection of music compared to the original methods (9.3% vs 7.6%) and also performed better at identifying songs that were skipped by users (49% vs 54%).

## Limitations

One challenge in using reinforcement learning for recommendation systems is the lack of simulation platforms for sequential user interactions. This makes it difficult to fully evaluate the music recommendation system, especially when it comes to understanding the order of songs in a playlist.

## Example usage

```
cd src
from main import *
run('../data/user_mini_data.tar.gz', '../data/music_mini_data.tar.gz')
```

## Data

I built this project using a real-world dataset from Spotify. The entire dataset is quite large (for example, it includes 130 million listening sessions). I am unable to include it here on GitHub, but you can find more information about it at the following website: https://www.aicrowd.com/challenges/spotify-sequential-skip-prediction-challenge.

## Inspiration

1 [https://arxiv.org/abs/1801.00209](https://arxiv.org/abs/1801.00209)

2 [https://github.com/egipcy/LIRD](https://github.com/egipcy/LIRD)

3 [https://github.com/luozachary/drl-rec](https://github.com/luozachary/drl-rec)
