## Models
## Using Dataset 2
We rate the model based on how well they predict segmentation for the 3 validation images.
![image](https://user-images.githubusercontent.com/98120916/221680996-1743becb-6bee-4ef3-b05c-e8f611d02498.png)

### Model 1- Fine tuned pspnet , Error function: default cce

#### Predictions
![image](https://user-images.githubusercontent.com/98120916/221681082-4e1faae1-824a-4535-b31c-9da7b9029ed2.png)

**Inference:**

1. Classifies every pixel as class 0 , due to class 0 being the most present. This reduces error but is also not the right intended way

**Proposed solution to the problem**

1. Use Categorical cross entropy with weights. assign very low weight ranging from 0 to 1e-5 for class 0 and give very high loss scalar for missclassifying other classes. we can then adjust after trial and error


### Model 2- Pretrained pspnet with weighted CCE

#### Predictions
![image](https://user-images.githubusercontent.com/98120916/221681152-39f91683-1221-44ce-b87f-9acdd95515fa.png)

### Model 3- Pretrained pspnet with wieghted Focal loss

#### Predictions
![image](https://user-images.githubusercontent.com/98120916/221681243-d9f23eff-c458-4243-91a7-565b657a0ce3.png)

**Inference**

1) Still bad predictions . One possible reason is pretrained on rgb data and is now being transfer learned with greyscale images.

2) Another possible reason is bad dataset. 


**Solutions**

1) we will use the dataset 1 and record observations

## Using dataset 1
We rate the model based on how well they predict segmentation for the 3 validation images
![image](https://user-images.githubusercontent.com/98120916/221681325-f882c2ee-0567-440d-ba02-7d40e4caa60e.png)

### Model 4- Pretrained unet with weighted cce on dataset 1
#### Predictions
![image](https://user-images.githubusercontent.com/98120916/221681408-e3db0231-08fd-424e-a69e-b33edae8d6c4.png)
