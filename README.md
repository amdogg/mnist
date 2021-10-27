# MNIST Example

## To train and deploy a model: 

  1. Run an Experiment using the mnist.py script. This will train the model and at completion will generate the weights at output/model directory.
     ![img.png](.images/img_1.png)
  2. In the Experiment view select Artifacts and at the top right select "Merge to Master" to move these files to the master branch.
     ![img_2.png](.images/img_2.png)
  3. In Serving create a new deployment and select Web Service.
  4. For the config set the predict file = predict.py and the function = predict
     ![img_3.png](.images/img_3.png)
  5. Click Deploy 

You now have a working endpoint and example curl and python commands you can use to test from your workspace and execute code.

*** If you want to train on GPU you must comment the tensorflow line in the requirements.txt and replace with 

    tensorflow>=2.2.0
    
## Run Hyper Parameter Optimization 
  1. Launch a workspace with default compute and default cnvrg image
     ![img.png](.images/img.png)
  2. open a terminal and run 
```bash
     cnvrg run --grid='small_hyper.yaml' 'python mnist.py'
```
![img_5.png](.images/img_5.png)

This will launch multiple jobs for the range of params passed inside the small_hyper.yaml file. You can modify and run your own custom yaml. 
![img_6.png](.images/img_6.png)

Apply a search filter for the GridSearch_ID to see all hyper parameter jobs in a single view with parallel plot 
![img_7.png](.images/img_7.png)

