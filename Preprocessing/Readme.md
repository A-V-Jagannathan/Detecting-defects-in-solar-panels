In this Preprocessing folder you can find codes used to preprocess data.
## Steps taken:
### i)Data augmentation
due to less available training data, i augmented data - upto 15 deg rotation , flipping (horizontal and vertical), shear.
### ii)Mask pixel value Error resolving

There were only 5 classes, but there were pixels with values >=5 while it should be in range [0,4]

So i used a dictionary and noted down sum of pixels of every class.

it all ended within 6 so in range [0,6] instead of [0,4]

initially i changed pixels 5,6 to 0. but they were actually other class.(LHS and Normal)

to combat this i took an image containing all 5 defects, changed each each class to 0 one by one and noted the values that didnt affect

the pixel values were 2 and 4. They were stray pixels.

So i changed all pixels with 

values 2 and 4 to 0,

values 3 to 2

values 5 to 3 

values 6 to 4

### iii)pixels with only class 0s were dropped/deleted
### iv)To make accessing and debugging easier, seperated masks and their images into 2 different folders and gave them readable names, using renaming and refiling.ipynb
