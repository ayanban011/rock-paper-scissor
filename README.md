## Getting Our Data
The basis of any Machine Learning model is DATA. Any machine learning engineer would agree that in Machine Learning the Data is far more important than the algorithm. We need to collect images for the symbols Rock, Paper adn Scissor.
Here we have getData.py which is run like this

```
python getData.py label startIndex endIndex
```

This will essentialy make a folder of name label and store (endIndex-startIndex+1) images .

## Training our Model
Next we move to training our model. Here we have used the DenseNet model available from keras.applications as a base model to work upon. It is followed by a MaxPooling Layer which is Flattened and finally run through a Dense Layer with 3 Output Neurons and SoftMax Activation to predict our output from 3 Classes Rock, Paper and Scissor.
Here we have trai.py which is run like this <br>
<p align="center"><img src = "https://user-images.githubusercontent.com/37273226/79741167-6e3d7380-831e-11ea-8e26-8e2f000568a0.png"/></p>


```
python train.py pathToImages
```

This will iterate over the files produced by getData.py and train our Model. Once trained the Model architecture is stored in a json file and the weights are stored in .h5 file.
Due to lack of computational power I had to train the model using Google Colab by setting Hardware Accelration to GPU.

## Time to play!
Now we load our Model Architecture and weights and finally play the game. Refer play.py
Before running make sure the model.h5 and model.json files are in same folder as play.py.
To Run:

```
python play.py
```

## Requirements
- tensorflow
- keras
- opencv

## Notes:
This model works with staionary backgrounds against which Model has been trained. We could implement Hand Detection followed by Gesture Classifation to improve performance. This is a very basic model that simply tries to make predictions on the input image without any major preprocessing but is enough if you play in the same physical position. If you're new at this try chaning your Dataset and re-train your model multiple times would really help you gain better insights into the project.
