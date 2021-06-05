# 2021-TPAMI-Concealed Object Detection (SINetV2-Jittor Implementation)

## Introduction

The repo provides inference code of **SINet-V2 (TPAMI-2021)** with Jittor deep-learning framework.

> **Jittor** is a high-performance deep learning framework based on JIT compiling and meta-operators. The whole framework and meta-operators are compiled just-in-time. A powerful op compiler and tuner are integrated into Jittor. It allowed us to generate high-performance code with specialized for your model. Jittor also contains a wealth of high-performance model libraries, including: image recognition, detection, segmentation, generation, differentiable rendering, geometric learning, reinforcement learning, etc. The front-end language is Python. Module Design and Dynamic Graph Execution is used in the front-end, which is the most popular design for deeplearning framework interface. The back-end is implemented by high performance language, such as CUDA,C++.

## Usage

SINet-V2 is also implemented in the Jittor toolbox which can be found in `./jt_lib`.
+ Create environment by `python3.7 -m pip install jittor` on Linux. 
As for MacOS or Windows users, using Docker `docker run --name jittor -v $PATH_TO_PROJECT:/home/SINet-V2 -it jittor/jittor /bin/bash` 
is easier and necessary. 
A simple way to debug and run the script is running a new command in the container through `docker exec -it jittor /bin/bash` and start the experiments.

+ First, run `sudo sysctl vm.overcommit_memory=1` to set the memory allocation policy.

+ Second, switch to the project root by `cd /home/SINet-V2`

+ For testing, run `python3.7 jittor/MyTesting.py`. 

## Performance

The performance has slight difference due to the difference of two frameworks. Note that the Jittor model is just converted from the original PyTorch model via toolbox, and thus, the trained weights of PyTorch model 
can be used to the inference of Jittor model.

| CHAMELEON dataset    	| $S_\alpha$  	| $E_\phi$  	| $F_\beta^w$  	| M     	|
|----------------------	|-------------	|-----------	|--------------	|-------	|
| PyTorch              	| 0.888       	| 0.942     	| 0.816        	| 0.030 	|
| Jittor               	|             	|           	|              	|       	|

|  CAMO-Test dataset   	| $S_\alpha$  	| $E_\phi$  	| $F_\beta^w$  	| M     	|
|----------------------	|-------------	|-----------	|--------------	|-------	|
|  PyTorch             	| 0.820       	| 0.882     	| 0.743        	| 0.070 	|
|  Jittor              	|             	|           	|              	|       	|

|  COD10K-Test dataset 	| $S_\alpha$  	| $E_\phi$  	| $F_\beta^w$  	| M     	|
|----------------------	|-------------	|-----------	|--------------	|-------	|
|  PyTorch             	| 0.815       	| 0.887     	| 0.680        	| 0.037 	|
|  Jittor              	|             	|           	|              	|       	|

## Citation

If you find our work useful in your research, please consider citing:
    
    
    @article{fan2021concealed,
      title={Concealed Object Detection},
      author={Fan, Deng-Ping and Ji, Ge-Peng and Cheng, Ming-Ming and Shao, Ling},
      journal={IEEE TPAMI},
      year={2021}
    }
    
    @article{hu2020jittor,
      title={Jittor: a novel deep learning framework with meta-operators and unified graph execution},
      author={Hu, Shi-Min and Liang, Dun and Yang, Guo-Ye and Yang, Guo-Wei and Zhou, Wen-Yang},
      journal={Information Sciences},
      volume={63},
      number={222103},
      pages={1--21},
      year={2020}
    }