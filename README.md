# JupyterLab using nginx by Docker

- Deliver Jupyter Lab to users so that each user would have their own isolated “instance”. There is an off-the-shelf solution for this called `JupyterHub` that probably makes the most sense for your organization. This example will be a proof of concept on how you could roll your solution.

# Reference:

- [link](https://alex-jacobs.com/posts/jupyterlab2/)
- [docker hub](https://hub.docker.com/r/tiangolo/uwsgi-nginx/)
- [conda env](https://uwekorn.com/2021/03/01/deploying-conda-environments-in-docker-how-to-do-it-right.html)
- [minforge](https://github.com/conda-forge/miniforge-images/blob/master/ubuntu/Dockerfile)
- [mamba](https://hub.docker.com/r/mambaorg/micromamba)
- [mamba docker](https://github.com/mamba-org/micromamba-docker/blob/main/Dockerfile)
- [docker best practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

# TODO:

- change working dir for jupyter and add project files, boot to that
- install packages; may use virtual env | conda
- usw `uWSGI` or `ASGI` protocol if possible.
- reduce image size, if possible.
- install mamba to ubuntu base image and use that image, might have to use multi stage docker build
- use volumes for data inside docker