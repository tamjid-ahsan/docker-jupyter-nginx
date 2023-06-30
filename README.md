# JupyterLab using nginx by Docker

- Deliver Jupyter Lab to users so that each user would have their own isolated “instance”. There is an off-the-shelf solution for this called `JupyterHub` that probably makes the most sense for your organization. This example will be a proof of concept on how you could roll your solution.

# Reference:

- [link](https://alex-jacobs.com/posts/jupyterlab2/)
- [docker hub](https://hub.docker.com/r/tiangolo/uwsgi-nginx/)

# TODO:

- change working dir for jupyter and add project files, boot to that
- install packages; may use virtual env | conda
- usw `uWSGI` or `ASGI` protocol if possible.
- reduce image size, if possible.