## Models
## Using Dataset 2
We rate the model based on how well they predict segmentation for the 3 validation images.
### Model 1- Fine tuned pspnet , Error function: default cce

#### Predictions


**Inference:**

1. Classifies every pixel as class 0 , due to class 0 being the most present. This reduces error but is also not the right intended way

**Proposed solution to the problem**

1. Use Categorical cross entropy with weights. assign very low weight ranging from 0 to 1e-5 for class 0 and give very high loss scalar for missclassifying other classes. we can then adjust after trial and error


### Model 2- Pretrained pspnet with weighted CCE

#### Predictions

### Model 3- Pretrained pspnet with wieghted Focal loss

#### Predictions

**Inference**

1) Still bad predictions . One possible reason is pretrained on rgb data and is now being transfer learned with greyscale images.

2) Another possible reason is bad dataset. 


**Solutions**

1) we will use the dataset 1 and record observations

## Using dataset 1
We rate the model based on how well they predict segmentation for the 3 validation images
### Model 4- Pretrained unet with weighted cce on dataset 1

#### Predictions
