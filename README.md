### MNIST Example

## To Run this demo flow: 

  1. Run an Experiment using the mnist.py script. This will train the model and at completion will generate the weights file model.h5 
  2. In the Experiment view select your experiment and at the bottom select "Merge to Master" to move these files to the master branch. 
  3. In Serving create a new deployment and select Web Service. 
  4. For the config set the predict file = predict.py and the function = predict
  5. Click Deploy 


*** If you want to train on GPU you must comment the tensorflow line in the requirements.txt and replace with 

    tensorflow>=2.2.0
    
    
