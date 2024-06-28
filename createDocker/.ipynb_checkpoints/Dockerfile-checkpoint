# img Jupyter Notebook
FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive

# update system
RUN apt-get update && apt-get install -y \
    r-base \
    python3-pip \
    libzmq3-dev \
    libfontconfig1-dev\
    libharfbuzz-dev \
    libfribidi-dev \
    libcurl4-openssl-dev \
    libssl-dev \ 
    libfreetype6-dev\ 
    libpng-dev\  
    libtiff5-dev\ 
    libjpeg-dev


# install 

RUN pip3 install jupyterlab

RUN R -e "install.packages('IRkernel') "
RUN R -e "IRkernel::installspec()"
RUN R -e "install.packages('tidyverse') "




# workdir
WORKDIR /home/hailt/Desktop/Thanh_Hai/docker/createDocker/

# Copy file Jupyter Notebook to container
COPY cleanData.ipynb .
COPY taiwan_2024_03_21_11_05_45.csv .
# RUN run.sh



# install library

# RUN pip install -r requirements.txt

# open port 8888 for Jupyter Notebook
EXPOSE 8888


# run Jupyter Notebook
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
