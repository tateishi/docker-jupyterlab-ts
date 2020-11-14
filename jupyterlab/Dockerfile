FROM jupyter/datascience-notebook:latest

ARG PASSWD

USER root

RUN apt-get update && curl -sL https://deb.nodesource.com/setup_14.x | bash - && apt-get install -y \
        nodejs

RUN npm install -g tslab && tslab install

RUN groupadd -g 1000 ubuntu
RUN usermod -g ubuntu jovyan

USER jovyan
RUN echo "c.NotebookApp.password = '${PASSWD}'" >> /home/jovyan/.jupyter/jupyter_notebook_config.py
