[![docker pulls](https://img.shields.io/docker/pulls/jupyter/scipy-notebook.svg)](https://hub.docker.com/r/jupyter/scipy-notebook/) [![docker stars](https://img.shields.io/docker/stars/jupyter/scipy-notebook.svg)](https://hub.docker.com/r/jupyter/scipy-notebook/) [![image metadata](https://images.microbadger.com/badges/image/jupyter/scipy-notebook.svg)](https://microbadger.com/images/jupyter/scipy-notebook "jupyter/scipy-notebook image metadata")

# Jupyter Notebook Scientific Python Stack

Customized to enable embedding within an iframe.


## Configuration

Config settings are in `jupyter_notebook_config.py`.

The `Content-Security-Policy` header in `c.NotebookApp.tornado_settings` must
include the iframe's host (just the scheme, host and port).

Change log levels for production.


## Build the image

If testing locally using minikube, make sure the docker command is pointing 
to minikube's container registry:

    eval $(minikube -p datahub docker-env)

Build the image:

    docker build -t "jupyter/scipy-notebook:latest" .

This image is referenced in the JupyterHub configuration file, e.g.

    singleuser:
      storage:
        type: none
      cpu:
        limit: .5
        guarantee: .2
      memory:
        limit: 1G
        guarantee: 0.5G
      image:
        name: jupyter/scipy-notebook
        tag: latest
        imagePullPolicy: Always


## Installed libraries

* beautifulsoup4=4.8.*
* conda-forge::blas=*=openblas
* bokeh=1.3*
* cloudpickle=1.2*
* cython=0.29*
* dask=2.2.*
* dill=0.3*
* h5py=2.9*
* hdf5=1.10*
* ipywidgets=7.5*
* matplotlib-base=3.1.*
* numba=0.45*
* numexpr=2.6*
* pandas=0.25*
* patsy=0.5*
* protobuf=3.9.*
* scikit-image=0.15*
* scikit-learn=0.21*
* scipy=1.3*
* seaborn=0.9*
* sqlalchemy=1.3*
* statsmodels=0.10*
* sympy=1.4*
* vincent=0.4.*
* xlrd

Additional libraries can be added to the `Dockerfile`.


Please visit the documentation site for help using and contributing to this image and others.

* [Jupyter Docker Stacks on ReadTheDocs](http://jupyter-docker-stacks.readthedocs.io/en/latest/index.html)
* [Selecting an Image :: Core Stacks :: jupyter/scipy-notebook](http://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#jupyter-scipy-notebook)
