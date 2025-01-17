# GMFSS_Fortuna

The all-in-one GMFSS

---

* I have optimized the training process and this time it will definitely not be always erratic like union.
* We offer several models for inference or as pre-training models for finetune.

## Installation

Our code is developed based on pytorch 1.13.1, CUDA 11.8 and python 3.9. Lower version pytorch should also work well.

To install, run the following commands:

```
git clone https://github.com/98mxr/GMFSS_Fortuna.git
cd GMFSS_Fortuna
pip install -r requirements.txt
```

## Model Zoo

If you want to validate the results then you need the [GMFSS model](https://drive.google.com/file/d/1BKz8UDAPEt713IVUSZSpzpfz_Fi2Tfd_/view?usp=sharing) or [union model](https://drive.google.com/file/d/1Mvd1GxkWf-DpfE9OPOtqRM9KNk20kLP3/view?usp=sharing)

If you want to train your own model, you can use my [pre-trained model](https://drive.google.com/file/d/1y5Spgidahk12Q0MO-ZlSVLDMRQoj6FJI/view?usp=sharing) to skip the baseline training process

## Run Video Frame Interpolation

To run video frame interpolation, unzip the downloaded model and place the `train_log` folder in the root directory. Then, run the following commands:

Using gmfss mode

```
python3 inference_video.py --img=demo/ --scale=1.0 --multi=2
```

Using union mode

```
python3 inference_video.py --img=demo/ --scale=1.0 --multi=2 --union
```

## Train

To train the models, unzip the pre-trained model and place the `train_log` folder and training data in the root directory. You may need to modify `model/dataset.py` to be compatible with different datasets.

Train gmfss with gan optimization

```
python3 train_pg.py
```

Train gmfss_union with gan optimization

```
python3 train_upg.py
```

Train pre-trained models

```
python3 train_nb.py
```

## Acknowledgment

This project is supported by [SVFI](https://steamcommunity.com/app/1692080) [Development Team](https://github.com/Justin62628/Squirrel-RIFE) 
