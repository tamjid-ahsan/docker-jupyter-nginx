# FROM ubuntu:22.10
FROM mambaorg/micromamba:1.4.6
# FROM condaforge/mambaforge

# ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /jupyter
COPY /code /code
WORKDIR /code

# works with ubuntu base
# RUN apt-get update && apt-get install -y \
#       python3-pip \
#       python3-dev \
#     && python3 -m pip install jupyterlab
# RUN pip install pandas

# Er: mamba not found
# RUN apt-get update && apt-get install -y \
#     && mamba create -n learn ./assets/req/env_files/learn-env.yml \
#     && mamba init \
#     && mamba activate learn

RUN micromamba install -y -n base -f ./assets/req/env_files/base.yml && \
    # micromamba install -y -n base jupyter -c conda-forge && \
    micromamba clean --all --yes

ARG MAMBA_DOCKERFILE_ACTIVATE=1
RUN python -c "import uuid; print(uuid.uuid4())"

# add user and switch to it
# RUN useradd -ms /bin/bash jupyter
# USER jupyter
USER mambauser


EXPOSE 8888

# ENTRYPOINT ["/usr/local/bin/_entrypoint.sh", "jupyter", "lab", "--ip=0.0.0.0", "--port", "8888", "--allow-root", "--ServerApp.token=", "--ServerApp.password=", "--ServerApp.allow_origin", "*"]
ENTRYPOINT ["/usr/local/bin/_entrypoint.sh", "jupyter", "lab", "--ip=0.0.0.0", "--port", "8888", "--allow-root", "--ServerApp.token=", "--ServerApp.password=", "--ServerApp.allow_origin", "*"]
# CMD [ "/bin/bash" ]