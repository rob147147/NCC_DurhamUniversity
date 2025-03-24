# RAPIDS environment on NCC

The examples here will work if you are using [https://ncc1.clients.dur.ac.uk/COMP0000](https://ncc1.clients.dur.ac.uk/COMP0000) with a custom Python virtual environment.

After logging in you can fetch the "Create Jupyter Environment Script" tool from the "Assignments" tab if you've not already.
Open the notebook in that folder, set the python version to "python3.12" and give your environment and kernel a sensible name.
Edit the modulesToLoad variable to read: 
  modulesToLoad = "cuda/12.3-cudnn8.9"

Run all cells, and this will create your Python virtual environment. Once all cells have run you can close this notebook. 

Now you can run any of the Jupyter notebooks in this directory (once you set the kernal to be the one you've created) to compare the difference between the CPU and GPU implementations. Each notebook will start with a pip install to load the relevant CUDA packages for CUDA 12.


# RAPIDS Random Forest with scikit-learn
File: RandomForest.ipynb

Request 4 cores, at least 8GB RAM, 1 GPU and at least 1 hour of runtime.
In my testing the CPU code provided takes around 10-11 minutes of wall clock time with 4 cores (around 42 minutes of CPU time in total).
A one line change to use the cuML accelerator utilises the 10GB virtual GPU (1/8 of an A100) we requested and reduces the runtime to under 7 seconds!
