# hash:sha256:ba3bc6dd94b4735a26bc21d68601e5e296e160837bea39621492b162c598e929
FROM registry.codeocean.com/codeocean/ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

# install some important stuff
# ---
RUN apt-get update && apt-get install -y apt-transport-https
RUN  apt-get install -y -qq curl git
RUN apt-get install -y software-properties-common
RUN apt-get update
RUN add-apt-repository universe
RUN apt update
RUN apt install -y git
RUN apt install -y vim

# python installation
# ---
RUN apt install -y -qq python2.7 python-pip

RUN apt-get install -y --no-install-recommends python-tk python3-tk libglu1-mesa-dev libgl1-mesa-dev libosmesa6-dev xvfb ffmpeg patchelf libglfw3 libglfw3-dev cmake zlib1g zlib1g-dev swig

# requirements installation
# ---

RUN pip install -U --no-cache-dir --upgrade-strategy=only-if-needed \
    absl-py==0.9.0 \
    decorator==4.4.1 \
    enum34==1.1.6 \
    ipython==5.8.0 \
    ipython-genutils==0.2.0 \
    lark-parser==0.7.8 \
    numpy==1.16.5 \
    pygame==1.9.6 \
    pymunk==5.6.0 \
    scipy==1.2.1 \
    tqdm==4.41.1 \
    opencv-python==4.2.0.32 \
    ipdb==0.13.2 \
    gevent==1.4.0 \
    typing==3.7.4.1 \
    imageio==2.6.1 \
    webcolors==1.10 \
    matplotlib==2.2.5 \
    sklearn==0.0 \
    guppy==0.1.11 \
    atari-py==0.2.6 \
    gym==0.16.0 \
    GitPython==2.1.15 \
    grpcio==1.37.1 \
    grpcio-tools==1.37.1 \
    psutil==5.8.0


# R installation
# ---
RUN set -uex; \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9; \
    add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu bionic-cran40/'; \
    apt-get update; \
    apt-get install -y r-base; \
    rm -rf /var/lib/apt/lists/*

RUN echo 'options(repos = c(CRAN = "https://cran.microsoft.com/snapshot/2018-04-01/"), download.file.method = "libcurl")' >> /etc/R/Rprofile.site
RUN echo 'options(Ncpus = parallel::detectCores())' >> /etc/R/Rprofile.site

RUN Rscript -e 'install.packages("EnvStats", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("RColorBrewer", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("colorspace", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("cowplot", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("dplyr", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("ggExtra", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("ggplot2", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("here", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("plotrix", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("plyr", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("purrr", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("zoo", dependencies=TRUE, repos="http://cran.rstudio.com/")'
RUN Rscript -e 'install.packages("zoom", dependencies=TRUE, repos="http://cran.rstudio.com/")'

# R installation
# ---
# Missing instalation of VGEnngine once the repo is cloned.
#

# TODO
# Install VGEngine
#RUN cd VGEngine
#RUN python setup.py install
#RUN cd ..

#RUN cd VGTranspiler
#RUN python run.py
