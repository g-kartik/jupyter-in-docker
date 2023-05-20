# jupyter-in-docker
Configuration for running jupyter lab in docker container

# Motivation
Jupyter lab is extremely useful for protyping code, learning new libraries and documenting the things we learn. However, it is quite a pain to set up a virtual 
environment, install the required packages and extensions. Also everytime we want to run it, we have to activate the virtual environment and run the jupyter command to launch the server. Well we can write a script for it and create a destop shortcut application, but it is too much to ask from a beginner.  

Enter docker based jupyter lab. I have made use of `Jupyter Docker Stacks` and used their docker image `jupyter/minimal-notebook` to create a docker based jupyter lab setup. I have created a docker compose file to make it easy to build, launch and destroy containers and also automatically restart the container on system restart.

# Guide
- Make sure we have the docker engine and docker compose installed on the system
- From the parent directory of the repository run, `docker compose up -d` to run the jupyter container in daemon mode
- Execute `docker exec -it jupyter jupyter server password` to set the password for the jupyter server
- Browse `localhost:8888` to open jupter lab
- Enter the password to login
- To add additional software packages, just add them to the requirements file in pip style format and rebuild the image and restart the containers
- We have two folders in the repo for persisting the user files after the container being destroyed
  - `config`: all the configuration files related to the jupyter application are stored here
  - `notebooks`: all the notebooks created by jupyter will be saved here. we can also add our existing notebooks to it.
- Now even if we restart our computer, jupyter lab will always be available at `localhost:8888`

Hope you enjoy this simple setup of jupyter
