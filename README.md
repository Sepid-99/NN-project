## *Unsupervised Representation Learning by Predicting Image Rotations (Report)*

### Introduction

**Title:**      "Unsupervised Representation Learning by Predicting Image Rotations (Report)"    
**Authors:**     Sepideh HajiHosseinKhani    
**Institution:** York University    


**Abstract:**  
In paper UNSUPERVISED REPRESENTATION LEARNING BY PREDICTING IMAGE ROTATIONS, they presents a novel approach to unsupervised representation learning, which involves predicting image rotations to learn useful representations of images. The proposed method takes advantage of the fact that images tend to have symmetries, and that predicting their rotation can serve as a good proxy task for learning a rich feature representation. The authors demonstrate that this approach outperforms other unsupervised methods, as well as some supervised methods, on a range of benchmark datasets. Furthermore, they show that the learned representations are useful for downstream tasks such as image classification and object detection. Overall, this paper provides a promising direction for unsupervised representation learning, which has important implications for a wide range of applications in computer vision and beyond.


### Requirements
It was developed and tested with pytorch version 0.2.0_4

### Before running the experiments
* Inside the *FeatureLearningRotNet* directory with the downloaded code you must create a directory named *experiments* where the experiments-related data will be stored: `mkdir experiments`.
* You must download the desired datasets and set in [dataloader.py](https://github.com/gidariss/FeatureLearningRotNet/blob/master/dataloader.py#L21) the paths to where the datasets reside in your machine. We recommend creating a *datasets* directory `mkdir datasets` and placing the downloaded datasets there. 
* Note that all the experiment configuration files are placed in the [./config](https://github.com/gidariss/FeatureLearningRotNet/tree/master/config) directory.

### CIFAR-10 experiments
* In order to train (in an unsupervised way) the RotNet model on the CIFAR-10 training images and then evaluate object classifiers on top of the RotNet-based learned features see the [run_cifar10_based_unsupervised_experiments.sh](https://github.com/gidariss/FeatureLearningRotNet/blob/master/run_cifar10_based_unsupervised_experiments.sh) script. Pre-trained model (in pytorch format) is provided [here](https://mega.nz/#!bk8ggYRa!CJoP3yugsI31rFGVtAX0nFBFtL_4a6BMlP9h6N56KH0) (note that it is not exactly the same model used in the paper).
* In order to run the semi-supervised experiments on CIFAR-10 see the [run_cifar10_semi_supervised_experiments.sh](https://github.com/gidariss/FeatureLearningRotNet/blob/master/run_cifar10_semi_supervised_experiments.sh) script.

### ImageNet and Places205 experiments
* In order to train (in an unsupervised way) a RotNet model with AlexNet-like architecture on the **ImageNet** training images and then evaluate object classifiers (for the ImageNet and Places205 classification tasks) on top of the RotNet-based learned features see the [run_imagenet_based_unsupervised_feature_experiments.sh](https://github.com/gidariss/FeatureLearningRotNet/blob/master/run_imagenet_based_unsupervised_feature_experiments.sh) script.
* In order to train (in an unsupervised way) a RotNet model with AlexNet-like architecture on the **Places205** training images and then evaluate object classifiers (for the ImageNet and Places205 classification tasks) on top of the RotNet-based learned features see the [run_places205_based_unsupervised_feature_experiments.sh](https://github.com/gidariss/FeatureLearningRotNet/blob/master/run_places205_based_unsupervised_feature_experiments.sh) scritp.


### Download the already trained RotNet model
* In order to download the RotNet model (with AlexNet architecture) trained on the ImageNet training images using the current code, go to: [ImageNet_RotNet_AlexNet_pytorch](https://mega.nz/#!n81AnC6L!xTbo_D3xd7QOpOSG1UFSChmDr8mbcuWbVjhQMaC4yoE). Note that:   
  1. The model is saved in pytorch format.   
  2. It is not the same as the one used in the paper and probably will give (slightly) different outcomes (in the ImageNet and Places205 classification tasks that it was tested it gave better results than the paper's model).    
  3. It expects RGB images that their pixel values are normalized with the following mean RGB values `mean_rgb = [0.485, 0.456, 0.406]` and std RGB values `std_rgb = [0.229, 0.224, 0.225]`. Prior to normalization the range of the image values must be [0.0, 1.0].


 * In order to download the RotNet model (with AlexNet architecture) trained on the ImageNet training images using the current code and convered in caffe format, go to: [ImageNet_RotNet_AlexNet_caffe](https://mega.nz/#!ekVRlLJC!N23AlTHuGwJF87sS6f7QjUyGfVFllEOFVgKtcrvZvYk). Note that:   
   1. The model is saved in caffe format.  
   2. It is not the same as the one used in the paper and probably will give (slightly) different outcomes (in the PASCAL segmentation task it gives slightly better results than the paper's model).   
   3. It expects BGR images that their pixel values are mean normalized with the following mean BGR values `mean_bgr = [0.406*255.0, 0.456*255.0, 0.485*255.0]`. Prior to normalization the range of the image values must be [0.0, 255.0].   
   4. The weights of the model are rescaled with the approach of [Kraehenbuehl et al, ICLR 2016](https://github.com/philkr/magic_init).      
   

