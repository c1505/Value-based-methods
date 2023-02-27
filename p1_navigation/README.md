# Reinforcement learning environment details
The environment has 37-dimensional state space. It contains the velocity and ray-based perception of objects in the agent's forward direction. The agent is rewarded with +1 for collecting a yellow banana and -1 for collecting a blue banana. There are four possible actions that the agent can take: walk forward (0), walk backward (1), turn left (2), and turn right (3).

The environment is considered solved when the agent achieves an average reward of at least 13 over 100 episodes.


# Setup(Tested on Ubuntu Linux 22.04)
## Easy Install

The Banana environment is included in the repository, but it can be downloaded again from here. To create the environment, you can run conda create -f environment.yml in the terminal.

## Dependency install instructions(Copied from root of repository)

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drlnd python=3.6
	conda activate drlnd
	```
	
2. Follow the instructions in [this repository](https://github.com/openai/gym) to perform a minimal install of OpenAI gym.  
	- Install the **box2d** environment group by following the instructions [here](https://github.com/openai/gym#box2d).
	
3. Clone the repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.
```bash
git clone https://github.com/udacity/Value-based-methods.git
cd Value-based-methods/python
pip install .
```

4. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `drlnd` environment.  
```bash
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```

5. Before running code in a notebook, change the kernel to match the `drlnd` environment by using the drop-down `Kernel` menu. 

## Running code
* Start jupyter
* open `Navigation.ipynb`
* Ensure that the kernel `drlnd` is selected
* Run all cells