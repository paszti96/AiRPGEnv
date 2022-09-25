# Online RPG Environment for Reinforcement Learning 👾🤖👻 

# For more information: 
## [Publication @IEEE](https://ieeexplore.ieee.org/document/9263405)
## [Publication @GitHub](https://github.com/paszti96/AIRPGEnv/blob/master/WAIT_AI_RPG.pdf)

## About: 
The  main  goal  of  the  following  project  is  to  create  asimple,  lightweight  and  modifiable  MMORPG  (MassivelyMultiplayer  Online  Role-playing  Game)  Game  with  basic graphic design and functionality, and train Deep Reinforce-ment Learning Algorithms on it.
Although the purpose of the project is not only to develop an envi-ronment but to challenge multi-agent reinforcement learningalgorithms in it.

### Our main contributions are the following:
* Creating an environment that is massively multiplayer andcan be used from multiple training machines
* Train and compare popular Deep Learning algorithms
* Show that environment can be learned to some degree

This project is created during my Electrical engineering MSc. at Budapest University of Technology and Economics.
The project has been supervised by Marton Szemenyei.

### Implementation

#### Client
* Provides an interface fo the players to control the heroes
* Recreates the game state based on the messages from the server
* OpenAI Gym, OpenCV
* Observation Space: 64x64 pixel surrounding territory, 16x16 pixel mini map 
  * Red dot: Hero 
  * Blue dot: Monster
  * Black dot: NPC
  * Purple dot: High value target

![Territory](https://github.com/paszti96/AIRPGEnv/blob/master/map.png "Territory")
![Minimap](https://github.com/paszti96/AIRPGEnv/blob/master/minimap2.png "Minimap")

* 6-Dimensional action space: Move, Attack, Interract
* Reward for exploration and attack


#### Server
* Managing and supervising
* 5 NPCs, 50 Monsters in the initial setting
* 3 different map with different structure
* blue territory represents water which is forbidden for heroes but not for monsters

##### Maps:

![arctic](https://github.com/paszti96/AIRPGEnv/blob/master/arctic.png "Arctic")
![lake](https://github.com/paszti96/AIRPGEnv/blob/master/lake.png "Lake")
![valley](https://github.com/paszti96/AIRPGEnv/blob/master/valley.png "Valley")

#### Reinforcement Learning Agents
* Advantage Actor-Critic 
* Proximal Policy Optimization 

### Gameplay: 
* Main goal is to eliminate evey hostile characters
* NPCs can give a huntlist with marked characters for extra XP
* XP: for combat and for exploration

![gameplay](https://github.com/paszti96/AIRPGEnv/blob/master/gif.gif "Gameplay")

## Requirements: 
* OpenCV
* PyTorch

## Usage:

All command should be executed from the main directory:

To start the server:
```bash
python Server_py/game.py
```

To train the reinforcement learning algorithm:
```bash
python (PPO or A2C)/train.py
```

To play as a human: 
```bash
python Environment/environment.py
```
