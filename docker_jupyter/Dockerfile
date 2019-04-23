ARG BASE_CONTAINER=jupyter/base-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Giacomo Veneri <giacomo.veneri@gmail.com>"

# Install all OS dependencies for fully functional notebook server
RUN conda install hdfs3 libhdfs3 dask xgboost fastparquet


USER root

ADD notebook1.ipynb .

EXPOSE 8888
WORKDIR $HOME

# Configure container startup
ENTRYPOINT ["tini", "-g", "--"]
CMD ["start-notebook.sh"]