FROM codesignal/ubuntu-base:v5.0

RUN apt-get -qq update \
    && apt-get -qq -y install bzip2 --no-install-recommends \
    && curl -sSL https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -o /tmp/miniconda.sh \
    && bash /tmp/miniconda.sh -bfp /usr/local \
    && rm -rf /tmp/miniconda.sh \
    && conda install -y python=3 \
    && conda update conda \
    && apt-get -qq -y remove bzip2 \
    && apt-get -qq -y autoremove \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/*

ENV PATH /opt/conda/bin:$PATH
RUN conda create -n py2 -y python=2 \
       numpy \
       scipy \
       pandas \
       scikit-learn \
       tensorflow=1.11.0 \
       keras \
       nltk \
       requests \
       configparser \
       mysql-connector-python \
       MySql-Python \
       SQLAlchemy \
       toolz \
       appdirs \
       attrs \
       click \
       toml \
    && conda create -n py3 -y python=3 \
       numpy \
       scipy \
       pandas \
       scikit-learn \
       tensorflow=1.11.0 \
       keras \
       nltk \
       requests \
       mysql-connector-python \
       PyMySQL \
       SQLAlchemy \
       toolz \
       appdirs \
       attrs \
       click \
       toml

RUN ["/bin/bash", "-c", "source activate py3 && python -m nltk.downloader popular \
      && rm -rf /var/lib/apt/lists/* /var/log/dpkg.log \
      && conda clean --all --yes"]