# Minion_robot
Reinforcement Algorithm with Deep Q nework (DQN)  
Here we are training the agent to grab yellow bananas(Reward +1) and leave the blue ones(Reward -1). 
In our case environment is considered to be solved if it can get at average of 16 points over 100 episodes.

To train your own model and understand how the Agent works, refer to the below file:

[Navigation Controller](https://github.com/koyalbhartia/DQN-Banana-Collector/blob/main/Navigation_Controller/Navigation.ipynb)

## Setup environment:

1. First we have to install conda once the conda is installed we need to update the bash script.  [Install anaconda](https://docs.anaconda.com/anaconda/install/linux/)

2. Run the following commands in the terminal.
```
conda create --name drlnd python=3.6
source activate drlnd
```

3. Clone this repo :
```
git clone https://github.com/koyalbhartia/DQN-Banana-Collector
```

4. Install python dependencies:
```
cd DQN-Banana-Collector/python
pip install .
```

5. Setup drlnd environment :
```
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```
6. Open Jupyter noetbook to start learning and experimenting :

```
cd DQN-Banana-Collector/Navigation_Controller
jupyter notebook
```

And select the appropiate file to train and test the model.
(Eg. Navigation_Controller >> Navigation.ipynb)

**Note : Do not forget to select Kernal >> Change kernal >> drlnd**

7. Edit the location of Banana linux in code cell 2 with your username and run the notebook( Hit  **Shift + Enter**) 


## Project Report :

[Architecture and project report](https://github.com/koyalbhartia/DQN-Banana-Collector/blob/main/Report.md)

## Overall Results :

![Screenshot from 2021-07-05 17-28-20](https://user-images.githubusercontent.com/40532456/124523231-dd847380-ddbb-11eb-9e1a-f084f0d81aee.png)
