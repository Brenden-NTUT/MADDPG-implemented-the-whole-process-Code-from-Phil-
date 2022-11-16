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

![image](https://user-images.githubusercontent.com/64890777/202291874-83fafd29-60bf-44a6-b5d9-f8630f01695a.png)
- You can observe that the rewards will end up bigger than the beginning, and it's the same result as Phil's
- Here's another result (I forget to screenshot it)
- 
episode 500 average score -187.2
episode 1000 average score -185.9
episode 1500 average score -192.5
episode 2000 average score -189.3
episode 2500 average score -185.3
episode 3000 average score -175.1
episode 3500 average score -187.3
episode 4000 average score -200.3
episode 4500 average score -190.2
episode 5000 average score -108.9
episode 5500 average score -118.9
episode 6000 average score -109.6
episode 6500 average score -106.5
episode 7000 average score -105.1
episode 7500 average score -110.9
episode 8000 average score -106.6
episode 8500 average score -113.5
episode 9000 average score -98.7
episode 9500 average score -106.2
episode 10000 average score -105.6
episode 10500 average score -108.2
episode 11000 average score -103.3
episode 11500 average score -92.9
episode 12000 average score -99.0
episode 12500 average score -95.4
episode 13000 average score -100.1
episode 13500 average score -117.5
episode 14000 average score -127.3
episode 14500 average score -127.7
episode 15000 average score -127.3
episode 15500 average score -123.5
episode 16000 average score -133.5
episode 16500 average score -123.8
episode 17000 average score -113.1
episode 17500 average score -105.9
episode 18000 average score -98.1
episode 18500 average score -98.1
episode 19000 average score -109.3
episode 19500 average score -96.1
episode 20000 average score -101.4
episode 20500 average score -117.0
episode 21000 average score -106.3
episode 21500 average score -109.1
episode 22000 average score -110.5
episode 22500 average score -104.5
episode 23000 average score -113.8
episode 23500 average score -113.1
episode 24000 average score -105.2
episode 24500 average score -104.0
episode 25000 average score -87.1
episode 25500 average score -109.6
episode 26000 average score -120.2
episode 26500 average score -110.6
episode 27000 average score -118.7
episode 27500 average score -101.9
episode 28000 average score -107.6
episode 28500 average score -109.9
episode 29000 average score -61.9
episode 29500 average score -56.2
episode 30000 average score -41.9
episode 30500 average score -53.7
episode 31000 average score -50.0
episode 31500 average score -48.7
episode 32000 average score -43.4
episode 32500 average score -47.1
episode 33000 average score -45.4
episode 33500 average score -48.8
episode 34000 average score -39.2
episode 34500 average score -45.2
episode 35000 average score -48.8
episode 35500 average score -41.1
episode 36000 average score -38.9
episode 36500 average score -44.7
episode 37000 average score -38.1
episode 37500 average score -41.0
episode 38000 average score -50.9
episode 38500 average score -43.9
episode 39000 average score -34.4
episode 39500 average score -46.1
episode 40000 average score -48.0
episode 40500 average score -48.2
episode 41000 average score -6.8
episode 41500 average score -2.6
episode 42000 average score -1.2
... saving checkpoint ...



