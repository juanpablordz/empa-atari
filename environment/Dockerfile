# hash:sha256:53d18efee4ce14fe99c8c66fda2d7cd5489d43393f90515a336fb4497416396a
FROM registry.codeocean.com/codeocean/tensorflow:1.4.0-python2.7.12-cuda8.0.61-cudnn6.0.21-ubuntu16.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends software-properties-common \
    && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys \
        0xAD2323F17326AE31401037733E05EBFF05441C52 \
    && add-apt-repository -y 'deb http://deb.codeocean.com/rstudio-server-trusty/ ubuntu main' \
    && apt-get purge -y --autoremove software-properties-common \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential=12.1ubuntu2 \
        cmake \
        ffmpeg=7:2.8.15-0ubuntu0.16.04.1 \
        libgit2-dev=0.24.1-2ubuntu0.2 \
        libssl-dev=1.0.2g-1ubuntu4.15 \
        libxml2-dev=2.9.3+dfsg1-1ubuntu0.6 \
        pandoc=1.16.0.2~dfsg-1 \
        pkg-config=0.29.1-0ubuntu1 \
        r-base=3.2.3-4 \
        rstudio-server=1.2.5001 \
        virtualenv \
        wget \
        zlib1g-dev \
    && rm -rf /var/lib/apt/lists/*

# RUN pip install -U --no-cache-dir --upgrade-strategy=only-if-needed \
#     absl-py \
#     atari-py \
#     backports-functools-lru-cache==1.5 \
#     backports-shutil-get-terminal-size==1.0.0 \
#     cloudpickle==1.2.2 \
#     cycler==0.10.0 \
#     decorator==4.4.0 \
#     enum34==1.1.6 \
#     ffmpeg==1.4 \
#     future==0.17.1 \
#     futures==3.3.0 \
#     gin-config \
#     gym \
#     imageio==2.5.0 \
#     ipython==5.8.0 \
#     ipython-genutils==0.2.0 \
#     kiwisolver==1.1.0 \
#     matplotlib==2.2.4 \
#     networkx==2.2 \
#     numpy==1.16.4 \
#     opencv-python \
#     pathlib2==2.3.4 \
#     pexpect==4.7.0 \
#     pickleshare==0.7.5 \
#     pillow==6.1.0 \
#     prompt-toolkit==1.0.16 \
#     ptyprocess==0.6.0 \
#     pybrain==0.3 \
#     pygame==1.9.6 \
#     pygments==2.4.2 \
#     pyparsing==2.4.0 \
#     python-dateutil==2.8.0 \
#     pytz==2019.1 \
#     pywavelets==1.0.3 \
#     scandir==1.10.0 \
#     scikit-image==0.14.3 \
#     scipy==1.2.2 \
#     simplegeneric==0.8.1 \
#     six==1.12.0 \
#     subprocess32==3.5.4 \
#     tensorflow-gpu \
#     termcolor==1.1.0 \
#     torch==1.1.0 \
#     torchvision==0.3.0 \
#     traitlets==4.3.2 \
#     wcwidth==0.1.7

# RUN echo 'options(repos = c(CRAN = "https://cran.microsoft.com/snapshot/2018-04-01/"), download.file.method = "libcurl")' >> /etc/R/Rprofile.site \
#     && echo 'options(Ncpus = parallel::detectCores())' >> /etc/R/Rprofile.site \
#     && Rscript -e 'options(warn=2); install.packages("devtools")'
# RUN Rscript -e 'options(warn=2); devtools::install_version("EnvStats", version = "2.3.0")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("RColorBrewer", version = "1.1-2")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("colorspace", version = "1.3-2")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("cowplot")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("dplyr", version = "0.7.4")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("ggExtra", version = "0.7")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("ggplot2", version = "2.2.1")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("here", version = "0.1")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("plotrix", version = "3.7")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("plyr", version = "1.8.4")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("purrr", version = "0.2.4")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("zoo", version = "1.8-1")' \
#     && Rscript -e 'options(warn=2); devtools::install_version("zoom", version = "2.0.4")'

