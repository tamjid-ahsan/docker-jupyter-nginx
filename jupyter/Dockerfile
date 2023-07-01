FROM mambaorg/micromamba:1.4.6

LABEL vendor1="Tamjid Ahsan"

WORKDIR /jupyter
COPY /code /code
WORKDIR /code

RUN micromamba install -y -n base -f ./assets/req/env_files/base.yml && \
    micromamba clean --all --yes

ARG MAMBA_DOCKERFILE_ACTIVATE=1
RUN python -c "import uuid; print(uuid.uuid4())"

USER mambauser

EXPOSE 8888

ENTRYPOINT ["/usr/local/bin/_entrypoint.sh", "jupyter", "lab", "--ip=0.0.0.0", "--port", "8888", "--allow-root", "--ServerApp.token=", "--ServerApp.password=", "--ServerApp.allow_origin", "*"]