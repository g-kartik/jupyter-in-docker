# jupyter-in-docker
Configuration for running jupyter lab in docker container

# Instructions
- Make sure we have the docker engine and docker compose installed on the system
- From the parent directory of the repository run, `docker compose up -d` to run the jupyter container in daemon mode
- Execute `docker exec -it jupyter jupyter server password` to set the password for the jupyter server
- Browse `localhost:8888` to open jupter lab
- Enter the password to login
- To add additional software packages, just add them to the requirements file in pip style format and rebuild the image and restart the containers
