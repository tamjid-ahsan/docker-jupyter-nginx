# base image
FROM mambaorg/micromamba:1.4.6

LABEL vendor="Tamjid Ahsan"

# chnage directory for code
WORKDIR /jupyter
COPY /code /code
WORKDIR /code

# install packeges & clean temp files
RUN micromamba install -y -n base -f ./assets/req/env_files/base.yml && \
    micromamba clean --all --yes

# activate mamba env
ARG MAMBA_DOCKERFILE_ACTIVATE=1

# switch user
USER mambauser

# expose port for communication
EXPOSE 8888

# use mamba env to start jupyrtlab server
ENTRYPOINT ["/usr/local/bin/_entrypoint.sh", "jupyter", "lab", "--ip=0.0.0.0", "--port", "8888", "--allow-root", "--ServerApp.token=", "--ServerApp.password=", "--ServerApp.allow_origin", "*"]