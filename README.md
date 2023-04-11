## *Unsupervised Representation Learning by Predicting Image Rotations (Report)*

### Introduction

**Title:**      "Unsupervised Representation Learning by Predicting Image Rotations (Report)"    
**Authors:**     Sepideh HajiHosseinKhani    
**Institution:** York University    


**Abstract:**  
In paper UNSUPERVISED REPRESENTATION LEARNING BY PREDICTING IMAGE ROTATIONS, they presents a novel approach to unsupervised representation learning, which involves predicting image rotations to learn useful representations of images. The proposed method takes advantage of the fact that images tend to have symmetries, and that predicting their rotation can serve as a good proxy task for learning a rich feature representation. The authors demonstrate that this approach outperforms other unsupervised methods, as well as some supervised methods, on a range of benchmark datasets. Furthermore, they show that the learned representations are useful for downstream tasks such as image classification and object detection. Overall, this paper provides a promising direction for unsupervised representation learning, which has important implications for a wide range of applications in computer vision and beyond.

### Requirements
It was developed and tested with pytorch version 0.2.0_4

### CIFAR-10 experiments
* In order to train (in an unsupervised way) the RotNet model on the CIFAR-10 training images and then evaluate object classifiers on top of the RotNet-based learned features see the [run_cifar10_based_unsupervised_experiments.sh](https://github.com/gidariss/FeatureLearningRotNet/blob/master/run_cifar10_based_unsupervised_experiments.sh) script. Pre-trained model (in pytorch format) is provided [here](https://mega.nz/#!bk8ggYRa!CJoP3yugsI31rFGVtAX0nFBFtL_4a6BMlP9h6N56KH0) (note that it is not exactly the same model used in the paper).
* In order to run the semi-supervised experiments on CIFAR-10 see the [run_cifar10_semi_supervised_experiments.sh](https://github.com/gidariss/FeatureLearningRotNet/blob/master/run_cifar10_semi_supervised_experiments.sh) script.
