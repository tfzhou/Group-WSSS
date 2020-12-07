## Group-Wise Semantic Mining for Weakly Supervised Semantic Segmentation

This  is a PyTorch implementation of our model for weakly supervised semantic segmentation.

## Prerequisites

The training experiments are conducted using PyTorch 1.4.0 with four NVIDIA RTX 2080Ti GPU with 11GB memory per card.

+ Please install PyTorch 1.4.0

Other minor Python modules can be installed by running

```bash
pip install -r requirements.txt
``` 

## Train

### Clone
```git clone -- recursive https://github.com/Lixy1997/Group-WSSS```

### Download Dataset

+ Please download the [PASCAL VOC 2012](https://drive.google.com/file/d/1uh5bWXvLOpE-WZUUtO77uwCB4Qnh6d7X/view) dataset.

+ Create soft links:

    ```cd data; ln -s your/path VOC2012;```

### Train the Group-Wise Semantic Mining Network

+ Once the data is prepared, please run ```python train.py``` for training with our default parameters.

+ Then, you can resize the maps to the original image size by

```bash
cd run/pascal
python res.py
``` 
+ Move the resized maps to the ```data/VOCdevkit/VOC2012/``` folder.

+ Put the saliency maps to the ```data/VOCdevkit/VOC2012/``` folder, or you can run DSS model to generate saliency maps by yourself.

+ Run ```python gen_labels.py``` for generating pseudo labels of training set.

### Train the Semantic Segmentation Network

+ Once the pseudo labels are generated, it can be used to train the semantic segmentation network.

## The Results

1. The Class Activation Maps for our group-wise semantic mining can be downloaded from [Google Drive]().

2. The saliency maps used for proxy labels are from [Google Drive](https://drive.google.com/file/d/1Ls2HBtg3jUiuk3WUuMtdUOVUFCgvE8IX/view).

3. The segmentation results of val and test sets of PASCAL VOC 2012 dataset can be downloaded from [Google Drive](https://drive.google.com/drive/folders/1l4gijmea9zDVt2VCwb-KuL6diit2T-zZ).
For reproducing scores of the test set, please submit the results of test set to the [official website](http://host.robots.ox.ac.uk:8080/) following the requirements of the official website.




