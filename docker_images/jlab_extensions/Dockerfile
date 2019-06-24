# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# docker build -t jlab .
#
# docker run -it -p 8787:8888 jlab bash
# docker run -it -p 8787:8888 --mount source=snp-vol,target=/Users/jbianco/Documents/repo_github/jupyterlab_extensions/snippet_jlab_ext jlab bash
# docker run -it -p 8787:8888 -v /Users/jbianco/Documents/repo_github/jupyterlab_extensions:/var/code/ jlab bash
#
# nohup jupyter lab --ip=0.0.0.0 --allow-root --NotebookApp.token='' --NotebookApp.password='' --NotebookApp.notebook_dir=/ --watch &
# nohup jupyter lab --ip=0.0.0.0 --allow-root --NotebookApp.token='' --NotebookApp.password='' --NotebookApp.notebook_dir=/ &

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

FROM ubuntu:18.04
FROM python:3.6

# Configs
EXPOSE 8888

# Install Tools
## Anaconda
RUN curl -O https://repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh
RUN bash Anaconda3-5.0.1-Linux-x86_64.sh -b
ENV PATH="/root/anaconda3/bin:${PATH}"

## Cookiecutter
RUN conda install -y -c conda-forge cookiecutter

## NodeJS
RUN conda install -y nodejs

# Jupyter Lab
RUN conda install -y -c conda-forge jupyterlab

## JLPM
RUN jlpm install