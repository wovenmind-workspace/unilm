# Use the official Python base image with version 3.7
FROM python:3.7-slim-buster

# Install system dependencies
RUN apt-get update && apt-get install -y \
        build-essential \
        ca-certificates \
        curl \
        git \
        htop \
        libssl-dev \
        nano \
        net-tools \
        ssh \
        tree \
        unzip \
        vim \
        wget \
        zlib1g-dev \
    && apt-get clean\
    && rm -rf /var/lib/apt/lists/*
    
# Install miniforge
ENV CONDA_DIR /opt/conda
RUN curl -L -o miniforge_installer.sh https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh \
    && chmod +x miniforge_installer.sh \
    && ./miniforge_installer.sh -b -p $CONDA_DIR \
    && rm miniforge_installer.sh

# Put conda in path so we can use conda activate
ENV PATH=$CONDA_DIR/bin:$PATH
