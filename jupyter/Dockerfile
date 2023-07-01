FROM ubuntu:22.10

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
      python3-pip \
      python3-dev \
    && python3 -m pip install jupyterlab
RUN pip install pandas

# add user and switch to it, jupyter does not need elevated privilage
RUN useradd -ms /bin/bash jupyter
USER jupyter

EXPOSE 8888

ENTRYPOINT ["jupyter", "lab", "--ip=0.0.0.0", "--port", "8888", "--allow-root", "--ServerApp.token=", "--ServerApp.password=", "--ServerApp.allow_origin", "*"]