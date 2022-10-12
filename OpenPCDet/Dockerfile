#Ubuntu 18.04 - CUDA 11.3 - PyTorch 1.12.1 - Python 3.7.13
FROM nvidia/cuda:11.7.1-cudnn8-devel-ubuntu20.04
ENV DEBIAN_FRONTEND=noninteractive
SHELL ["/bin/bash", "-c"]
RUN apt update
RUN apt install --no-install-recommends python3-pip git -y
RUN pip install spconv-cu117
RUN pip install --pre torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/nightly/cu117
RUN git clone https://github.com/open-mmlab/OpenPCDet.git
RUN cd OpenPCDet && python3 setup.py develop