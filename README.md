# EDMSeg: Explicit Doppler Modeling for Motion-Consistent Radar Semantic Segmentation

The CARRADA dataset is available at this link: [https://arthurouaknine.github.io/codeanddata/carrada](https://arthurouaknine.github.io/codeanddata/carrada).

## Installation

### Installation Steps

1. Install basic multi-view RSS network lib using pip:

```bash
$ cd TARSS/
$ pip install -e .
```

2. Install all the dependencies using pip or conda (taking ***pip*** as an example):

```bash
$ pip install numpy==1.20.3 Pillow>=8.1.1  
```

```bash
$ pip install scikit-image==0.18.3 scikit-learn==0.24.2 scipy==1.7.1
```

```bash
$ pip install tensorboard==2.6.0 torch==1.9.0 torchvision==0.10.0a0
```

### Path Setup (Data & Logs)

1. Put the downloaded dataset "CARRADA" in your data dir, e.g., `/home/usrname/datasets`;
2. Specify the path for train/val logs, e.g., `/home/usrname/logs`;
3. Using ./utils/set_paths.py to set the data/log paths:

```bash
$ cd TARSS/mvrss/utils/
$ python set_paths.py --carrada /home/usrname/datasets --logs /home/usrnames/logs
```

### Training

Using training script `train.py` to train a model, this script will load the configuration info from a JSON config file, e.g., `config_files/tarssnet_v1.json`. The command line is as follows:

```bash
$ python train.py --cfg config_files/tarssnet_v1.json
```

### Testing

Actually, if you finished the training stage, the test results will also be calculated and saved in the log file. However, you can also just test the saved model using the script `test.py`.

Similar with the training stage, using the script `test.py` to evaluate the trained model as the following command line:

```bash
$ python test.py --cfg /home/logs/carrada/tarssnet_v1/name_of_the_model/config.json
```

