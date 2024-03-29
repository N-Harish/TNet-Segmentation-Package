# TNet-Segmentation

- It is a pytorch based Segmentation model inspired by the research paper ```T. M. Khan, A. Robles-Kelly and S. S. Naqvi, "T-Net: A Resource-Constrained Tiny Convolutional Neural Network for Medical Image Segmentation," 2022 IEEE/CVF Winter Conference on Applications of Computer Vision (WACV), Waikoloa, HI, USA, 2022, pp. 1799-1808, doi: 10.1109/WACV51458.2022.00186.``` published in CVPR 2022


# How to install

* run ```pip install TNet-Segmentation``` to install the package

# How to use

## Creating Model 
* The model takes three parameters: -  
    - input_channnel (defaults to 3)
    - emb_size (size of the output channel after first downsampling conv layer.Defaults to 512)
    - num_classes (the num of segmentation classes, defaults to 3)
* Usage is as simple as below:- 
    ```
    >>> from TNet_Segmentation import TNet                                
    >>> net = TNet(input_channel=3, emb_size=256, num_classes=3) 
    ```

## Visualizing 
* After creating the model call visualize function as follows:-
    ```
    >>> from TNet_Segmentation import visualize 
    >>> visualize(net)
    =================================================================
    Layer (type:depth-idx)                   Param #
    =================================================================
    TNet                                     --
    ├─Conv2d: 1-1                            7,168
    ├─TNetConvBlock: 1-2                     --
    │    └─ModuleList: 2-1                   --
    │    │    └─Conv2d: 3-1                  590,080
    │    │    └─BatchNorm2d: 3-2             512
    │    │    └─ReLU: 3-3                    --
    │    │    └─Conv2d: 3-4                  65,792
    │    │    └─BatchNorm2d: 3-5             512
    │    │    └─Conv2d: 3-6                  2,560
    │    │    └─BatchNorm2d: 3-7             512
    │    │    └─ReLU: 3-8                    --
    │    │    └─MaxPool2d: 3-9               --
    ```

## DiceLoss function

* Dice Loss is implemented in this library and can be used as follows:
    ```
    >>> from TNet_Segmentation import DiceLoss
    >>> loss = DiceLoss()


    ```