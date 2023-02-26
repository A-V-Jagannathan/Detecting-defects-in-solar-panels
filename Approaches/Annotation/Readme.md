### Approach 1
labelling every normal panel as normal panel, and the ones with defect with their respective defect.
![image](https://user-images.githubusercontent.com/98120916/221427183-933e7ca8-f7d8-4df2-8b44-e169dd679664.png)

Encountered problem: Model classifying every single panel as normal panel which reduces error by the most.

Possible solutions:
- Edit the crossentropy function to have more error when other classes are misclassified- Not always feasible
- label some panels only as normal in a given image.

### Approach 2
labelling the panels with defect with their respective defect, and labelling only 3-5 random normal panels per image/solar array.