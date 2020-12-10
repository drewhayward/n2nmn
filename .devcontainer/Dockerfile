FROM nvidia/cuda:8.0-cudnn5-devel-ubuntu16.04

WORKDIR /usr/src/n2nmn

ADD exp_shapes /usr/src/n2nmn/exp_shapes/
ADD models_shapes /usr/src/n2nmn/models_shapes/
ADD util /usr/src/n2nmn/util/

RUN apt-get update
RUN apt-get -y install software-properties-common
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get update
RUN apt-get -y install python3.6 python3.6-dev
RUN apt-get -y install python3-pip

RUN python3.6 -m pip install tensorflow-gpu==1.0.0
RUN python3.6 -m pip install https://storage.googleapis.com/tensorflow_fold/tensorflow_fold-0.0.1-py3-none-linux_x86_64.whl
RUN python3.6 -m pip install jupyter

# Exposing tensorboard for debugging
EXPOSE 6006

ENTRYPOINT [ "/bin/bash" ]