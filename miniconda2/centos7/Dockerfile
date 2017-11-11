FROM centos:centos7
MAINTAINER Conda Development Team <conda@continuum.io>

RUN yum -y update \
    && yum -y install curl bzip2 \
    && curl -sSL https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh -o /tmp/miniconda.sh \
    && bash /tmp/miniconda.sh -bfp /usr/local/ \
    && rm -rf /tmp/miniconda.sh \
    && yum install -y nodejs \
    && conda update conda \
    && curl -sSL https://raw.githubusercontent.com/ClimateImpactLab/conda-docker/impactlab/miniconda2/centos7/environent.yml -o /tmp/environment.yml
    && conda env create -f /tmp/environment.yml \
    && conda clean --all --yes \
    && rpm -e --nodeps bzip2 \
    && yum -y autoremove \
    && yum clean all
    && source activate impactlab
