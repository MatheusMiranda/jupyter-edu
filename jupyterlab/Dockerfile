# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
# Ubuntu 18.04 LTS - Bionic
FROM jupyterhub/k8s-singleuser-sample:0.8.2

# pip packages
RUN pip install --upgrade pip
RUN pip install setuptools --ignore-installed --upgrade

RUN python -m ipykernel install --user

ENV NBGITPULLER_APP=lab
ENV JUPYTER_LAB_ENABLE=yes
ENV NOTEBOOK_DIR=/home/jovyan/work

# Install Lab and NB2KG. Enable NB2KG extension. Lab is enabled by default
#RUN pip install --upgrade jupyterlab nb2kg && \
#    jupyter serverextension enable --py nb2kg --sys-prefix && \
#    jupyter serverextension enable --py jupyterlab --sys-prefix

RUN pip install --upgrade jupyterlab && jupyter serverextension enable --py jupyterlab --sys-prefix

USER root

RUN mkdir /notebooks
RUN chown -R jovyan:users /notebooks

USER jovyan

# Run with remote kernel managers
#CMD ["/usr/local/bin/start-nb2kg.sh"]

# Add local files as late as possible to avoid cache busting
#ADD jupyter_notebook_config.py /etc/jupyter/jupyter_notebook_config.py
#ADD start-nb2kg.sh /usr/local/bin/start-nb2kg.sh
#© 2020 GitHub, Inc.
