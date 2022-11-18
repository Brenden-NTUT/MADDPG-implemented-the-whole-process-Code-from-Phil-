# MADDPG-implemented-the-whole-process-Code-from-Phil-
This is just the tutorial of how to successfully run the code that Phil taught on the YouTube(https://www.youtube.com/watch?v=tZTQ6S9PfkE)
# Environment install
   - Open CMD or Git Bash (https://git-scm.com/downloads). This tutorial will use the Git Bash. 
   - Switch to the root directory that you want to save the file( cd your root directory address)   ex: `cd d:`
   - Enter this command `git clone https://github.com/openai/multiagent-particle-envs` (Which is the enivornment provided by openai)
   - cd into that folder `cd multiagent-particle-envs`
   - `python -m venv maddpg` Creating the virtual environment call maddpg(You can change the name) 
   - `source bin/activate` Get into the maddpg environment, if you face the error that "file can't be found", just check where's the activate file are, those might in the maddpg/Scripts 
   - `pip install gym==0.10.5` Install OpenAI version 0.10.5
   - `pip insstall numpy==1.14.5` Install numpy version 1.14.5
   - `pip install -e .` Install the MADDPG environment provided from OpenAI
   - `pip install torch==1.4.0+cpu torchvision==0.5.0+cpu -f https://download.pytorch.org/whl/torch_stable.html \`
    Install torch. Notice! The code can be successfully run in torch 1.4.0, not sure other versions will run successfully. (I faced errors in version 1.5.0, 1.6.0, 1.8.0, 1.9.0)
   - `pip list`, To see if all dependencies are met. Python (3.5.4), OpenAI gym (0.10.5), numpy (1.14.5)
   - `pip uninstall python` and `pip install python==3.5.4` As Phil said in the video, the python version won't affect the result. However, if you don't want to put any risk, I suggested just downloading the same version in dependencies.

# Code Combination
- Phil provided his code on GitHub [thub.com/philtabor/Multi-Agent-Deep-Deterministic-Policy-Gradients](https://github.com/philtabor/Multi-Agent-Deep-Deterministic-Policy-Gradients) 
- `vim do.py` Open a new .py file, again, the file name can be named by yourself
- I suggest copying all .py files code into one file, just follow Phil's code combination in the video.
- Phil's code which was provided in GitHub, are all been corrected, no need to change it. 

# Testing
- After finishing combining the code, we should start running it. But there's something we need to do first.
- ` mkdir tmp` , `mkdir tmp/maddpg`, `mkdir tmp/maddpg/simple_adversary`, `mkdir tmp/maddpg/simple_adversary/agent_0_actor` These commands are used to create folders that can help avoid saving point errors. 
- If you faced the error `from torch._C import * (ImportError: DLL load failed: The specified module could not be found.`
- The way I solved this error, is to download ANACONDA(https://docs.anaconda.com/anaconda/install/)
- Install Torch 1.4.0 in the ANACONDA environment, and look for the file  _C.lib_
- Copy it to the `multiagent-particle-envs\maddpg\Lib\site-packages` folder. The reason to do this is that somehow ANACONDA will help install the complete package for torch 1.4.0, and the package downloaded from the official PyTorch website missing the _C.lib_ file.
- I also found out some people's packages downloaded from the official PyTorch website including the _C.lib_ file, but the location of it isn't able to let the code import. So ypu need to find the file and put it into the right path.
- Or you can download  _C.lib_ file from the attached.
- `python do.py` If you all set, you can start running the code!
- It may take some time to run it, depending on your computer.
- Here's my result

![image](https://user-images.githubusercontent.com/64890777/202645025-f1d4f80e-dd8a-4cd4-a084-707d04517f63.png)
![image](https://user-images.githubusercontent.com/64890777/202645086-36e1d0bd-ca71-43e7-bc43-5557b7766fae.png)
![image](https://user-images.githubusercontent.com/64890777/202645114-e8cc2785-6c81-46a0-b607-792355c087fa.png)
![maddpg](https://user-images.githubusercontent.com/64890777/202645142-fb4a34ac-55d4-4b49-b673-b90fcfc3dd4c.png)
- You can observe that the rewards will end up bigger than the beginning, and it's the same result as Phil's
- Here's another result (I forget to screenshot it)
