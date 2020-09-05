# Bayesian global optimization

## General Info
The framework of the code are written in Jupyter Notebook, which can help people understand the process and see the result more easily. And in our experiment, we run the code in Google Colaboratory because it support GPU accelerate which help speed up the training process of deep learning models a lot. So before the experiment begins, we can upload the whole repository to the Google Drive, then open the ".ipynb" files in Google Colaboratory according to each steps in the framework.

The whole code running process follows the steps on Algorithm 2. Firstly, before we select variables through spike and slab algorithm, we need to generate some data points for both Hartmann 6-Dimensional function and CNN. We need to open "../variable selection/run_data_for_variable_selection.ipynb" and run all the cells. It will automatically generate 2000 data points for Hartmann function and 500 data points for choosing hyperparameters of CNN, because of limited computing power we can not generate more points but it is still effective according to the theory. And all these data will be save in "../Data", named as "X_hartamann.csv", "Y_hartamann.csv" and "X.csv", "Y.csv", the former two represents for inputs and outputs for Hartmann function while the later two are data for CNN. Next, we just need to open "../variable selection/variable selection.ipynb" and run all the cells, it will generate the images and text results like Figure 3 to help us select variable.

After finishing the variable selection, we can begin to use MTBO to optimize the Black-Box function we want. We just need to run the code in "../MTBO/multi_task_hartmann6.ipynb" and "../MTBO/tune_cnn_mtbo.ipynb", they are code for Hartmann function and CNN respectively. Run all the cells and the result plots we got in next few sections will be shown in the file. Besides, we want to save the results data "obj0\_rep5.csv" and "obj1\_rep5.csv" for CNN because it takes hours to run, after running the fifth cell, all you need to do is click the URL that cell shows you and enter the authorization code, if success the cell will show "Mounted at /content/gdrive". To use GPU accelerator, you can change the setting via "Runtime -> Change runtime type -> Hardware accelerator -> GPU -> SAVE". If loaded successfully, in the sixth cell it would print out "device(type='cuda')".

## Technologies

* Google colab
* Jupyter notebooks 

## Process

generate data for variable selection -> select variable via spike and slab algorithm -> optimize hartmann6 function by using our framework -> tune hyperparameters of the CNN

## How to use Google Colab

1. Download this repo file and unzip it, upload the whole folder to the Google Drive.

2. Open the .ipynb file inside the floder by using Google Colaboratory.

3. To use GPU accelerator, you can change the setting via “Runtime->Change runtime type->Hardware accelerator->GPU->SAVE”. If loaded successfully, in the sixth cell it would print out "device(type='cuda')".

