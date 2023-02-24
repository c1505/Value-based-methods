# TODO
* change this file to README.md

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


# Setup
* Many of the dependencies for this project are old
* In order to have the `unityagents` environment working, it was necessary to use older versions of torch and python.  
* there were challenges getting    
* The install was done as described by the Readme in the value based repo with some minor changes to prefer newer versions of dependencies when possible
  * torch==1.10.2


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