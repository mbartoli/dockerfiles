#version 0.0.1
FROM kaixhin/caffe
MAINTAINER Mike Bartoli "michael.bartoli@pomona.edu"
RUN apt-get update && apt-get install -y \
	git \
	ipython \
	python-dev

WORKDIR /home
RUN git clone https://github.com/google/deepdream
WORKDIR /home/deepdream




