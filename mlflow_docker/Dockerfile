FROM python:3.7-slim-stretch as Base

LABEL maintainer='Andrew Bauman'

RUN apt-get update && apt-get install -y \
    vim \
    nano \
    iputils-ping \
    curl \
    tmux \
    dumb-init \
    git \
    && rm -rf /var/lib/apt/lists/*

FROM Base as MFlow

RUN pip install mlflow['extras']

FROM MFlow as Loaded

RUN git clone https://github.com/mlflow/mlflow.git
COPY quickstart.py .
COPY run_server.sh .
RUN chmod a+x run_server.sh



CMD ["tail", "-f", "/dev/null"]