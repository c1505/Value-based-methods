# TODO
* change this file to README.md
* spell check


# Reinforcement learning environment details
* State space: 
    * size: 37
    * velocity and ray based perception of objects in agent's forward direction 
* reward: +1 for collecting yellow banana
              -1 for collecting blue banana
* action space
    * size: 4
    * actions:
        - `0` - walk forward 
        - `1` - walk backward
        - `2` - turn left
        - `3` - turn right

* solved environment
    Going based on the plotted rewards shown in "Bencharmk Implementation", this course is considering the environment solved at an approximate score of 14.


# Setup(Tested on Ubuntu Linux 22.04)
## Easy
* run `conda create -f environment.yml`
* The Banana environment is included in the repository.  If there are issues, re-download from here: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
* Many of the dependencies for this project are old
* In order to have the `unityagents` environment working, it was necessary to use older versions of torch and python.  
* there were challenges getting    
* The install was done as described by the Readme in the value based repo with some minor changes to prefer newer versions of dependencies when possible
  * torch==1.10.2

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




# Ideas for Future Work
  * Hyperparameter tuning
  * running with a different algorithm
  * Increasing speed of training
  * using curiosity for exploration
  * save every x episodes
  * log more learning metrics
  * integrate with tensorboard and/or weights and biases


# Misc 
* Ran with default hyperparameters to start

  I get this error on occasion when trying to create a second environment in a single jupyter session.  Fix it

```bash
  Output exceeds the size limit. Open the full output data in a text editor
---------------------------------------------------------------------------
OSError                                   Traceback (most recent call last)
<ipython-input-21-716be1dee56e> in <module>
----> 1 env = UnityEnvironment(file_name="/home/corey/reinforcement-learning/udacity/Value-based-methods/p1_navigation/Banana_Linux/Banana.x86_64")

~/anaconda3/envs/drlnd/lib/python3.6/site-packages/unityagents/environment.py in __init__(self, file_name, worker_id, base_port, curriculum, seed, docker_training, no_graphics)
     62         )
     63         try:
---> 64             aca_params = self.send_academy_parameters(rl_init_parameters_in)
     65         except UnityTimeOutException:
     66             self._close()

~/anaconda3/envs/drlnd/lib/python3.6/site-packages/unityagents/environment.py in send_academy_parameters(self, init_parameters)
    503         inputs = UnityInput()
    504         inputs.rl_initialization_input.CopyFrom(init_parameters)
--> 505         return self.communicator.initialize(inputs).rl_initialization_output
   506 
    507     def wrap_unity_input(self, rl_input: UnityRLInput) -> UnityOutput:

~/anaconda3/envs/drlnd/lib/python3.6/site-packages/unityagents/rpc_communicator.py in initialize(self, inputs)
     56                 "You may need to manually close a previously opened environment "
     57                 "or use a different worker number.".format(str(self.worker_id)))
---> 58         if not self.unity_to_external.parent_conn.poll(30):
     59             raise UnityTimeOutException(
     60                 "The Unity environment took too long to respond. Make sure that :\n"
...
--> 136             raise OSError("handle is closed")
    137 
    138     def _check_readable(self):

OSError: handle is closed
ERROR:root:Exception calling application: [Errno 32] Broken pipe
Traceback (most recent call last):
  File "/home/corey/anaconda3/envs/drlnd/lib/python3.6/site-packages/grpc/_server.py", line 385, in _call_behavior
    return behavior(argument, context), True
  File "/home/corey/anaconda3/envs/drlnd/lib/python3.6/site-packages/unityagents/rpc_communicator.py", line 25, in Exchange
    self.child_conn.send(request)
  File "/home/corey/anaconda3/envs/drlnd/lib/python3.6/multiprocessing/connection.py", line 206, in send
    self._send_bytes(_ForkingPickler.dumps(obj))
  File "/home/corey/anaconda3/envs/drlnd/lib/python3.6/multiprocessing/connection.py", line 404, in _send_bytes
    self._send(header + buf)
      File "/home/corey/anaconda3/envs/drlnd/lib/python3.6/multiprocessing/connection.py", line 368, in _send
    n = write(self._handle, buf)
BrokenPipeError: [Errno 32] Broken pipe
```