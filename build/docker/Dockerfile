FROM nvcr.io/nvidia/pytorch:23.06-py3

RUN wget -qO - https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/3bf863cc.pub | apt-key add - && \
    wget -qO - https://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu2004/x86_64/7fa2af80.pub | apt-key add - && \
    apt-get update -y && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        g++ \
        gcc \
        git \
        graphviz \
        openssh-client \
        python3-dev && \
    rm -rf /var/lib/apt/lists/*

RUN rm -r /usr/local/lib/python3.10/dist-packages/cupy_cuda12x-12.0.0b3.dist-info

RUN pip3 install pip --upgrade

RUN pip3 install --extra-index-url https://test.pypi.org/simple/ XPySom-dask git+https://github.com/discovery-unicamp/dasf-core.git cupy_xarray cupy==13.0.0b1

RUN pip install "numpy<1.24" bokeh==2.4.3 "protobuf<=3.20.1" "charset-normalizer<3.0" "tornado<6.2"

WORKDIR /dasf

LABEL dasf=latest


