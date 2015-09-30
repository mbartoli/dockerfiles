FROM ubuntu:14.04

MAINTAINER Michael Bartoli <michael.bartoli@pomona.edu>

ENV JAVA_VERSION_MAJOR 8
ENV JAVA_VERSION_MINOR 60
ENV JAVA_VERSION_BUILD 27
ENV JAVA_PACKAGE       server-jre

RUN apt-get update
RUN apt-get -y install \
	curl \
	wget \
	unzip \
	xorg \
	git

WORKDIR /home
RUN git clone https://github.com/mbartoli/docker-matlab
WORKDIR /home/docker-matlab
RUN mkdir /mcr-install
RUN cp matlab.txt /mcr-install

RUN curl -jksSLH "Cookie: oraclelicense=accept-securebackup-cookie"\
  http://download.oracle.com/otn-pub/java/jdk/${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-b${JAVA_VERSION_BUILD}/${JAVA_PACKAGE}-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-x64.tar.gz \
    | tar -xzf - -C /opt &&\
    ln -s /opt/jdk1.${JAVA_VERSION_MAJOR}.0_${JAVA_VERSION_MINOR} /opt/jdk


RUN	cd /mcr-install && \
	wget -nv http://de.mathworks.com/supportfiles/downloads/R2015b/deployment_files/R2015b/installers/glnxa64/MCR_R2015b_glnxa64_installer.zip && \
	unzip MCR_R2015b_glnxa64_installer.zip && \
	mkdir /opt/mcr && \
	./install -inputFile matlab.txt && \
	cd / && \
	rm -rf mcr-install

ENV JAVA_HOME /opt/jdk
ENV PATH ${PATH}:${JAVA_HOME}/bin

CMD ["bash"] 
