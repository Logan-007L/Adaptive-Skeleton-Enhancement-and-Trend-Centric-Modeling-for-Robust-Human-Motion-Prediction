# SEFormer

## Recommand Dependencies
* Cuda 12.1
* Python 3.8
* Pytorch 1.8.0

## Data preparation
### Human3.6M
Download Human3.6M dataset from its [website](http://vision.imar.ro/human3.6m/description.php) and put the files into "data" with the dataset folder named "h3.6m".

### CMUMocap
Download CMUMocap dataset from its [website](http://mocap.cs.cmu.edu) and put the files into "data" with the dataset folder named "CMUMocap".

### 3DPW
Download 3DPW dataset from its [website](https://virtualhumans.mpi-inf.mpg.de/3DPW) and put the files into "data" with the dataset folder named "3DPW".

After the prepartion work, the data folder should have the following structure:
```
/data
├── h3.6m
    ├── dataset
        ├── S1
        ├── S5
        ├── ...
├── CMUMocap
    ├── test
    ├── train
├── 3DPW
    ├── sequenceFiles                       
```

## Train
### Human3.6M
To train a short-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python main_h36m.py --task short
```
To train a long-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python main_h36m.py --task long
```

The trained model will be saved in ckpt/ .

### CMUMocap
To train a short-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python main_cmu.py --task short
```

To train a long-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python main_cmu.py --task long
```

The trained model will be saved in ckpt/ .

### 3DPW
To train a short-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python main_3dpw.py --task short
```

To train a long-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python main_3dpw.py --task long
```

The trained model will be saved in ckpt/ .

### Evaluate
### Human3.6M

To evaluate a long-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python test_h36m.py --task long --model_save_name pretrain_h36m_ckpt_long
```

### CMUMocap
Take our trained model as an example, to evaluate a short-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python test_cmu.py --task short --model_save_name pretrain_cmu_ckpt
```

To evaluate a long-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python test_cmu.py --task long --model_save_name pretrain_cmu_ckpt_long
```

### 3DPW
Take our trained model as an example, to evaluate a short-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python test_3dpw.py --task short --model_save_name pretrain_3dpw_ckpt
```

To evaluate a long-term motion prediction model, run
```
CUDA_VISIBLE_DEVICES={GPU_ID} python test_3dpw.py --task long --model_save_name pretrain_3dpw_ckpt_long
```

