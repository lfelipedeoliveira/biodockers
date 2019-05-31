FROM ubuntu:latest
ENV DEBIAN_FRONTEND noninteractive
MAINTAINER LFelipedeOliveira <felipe@lfelipedeoliveira.com>

RUN apt-get -y update; \
    apt-get -y upgrade; \
    apt-get -y install python3 python3-pip build-essential zlibc libc6 gcc g++ libboost1.54-all-dev cmake; \
    apt-get -y install curl; \
    apt-get -y install vim; \
    apt-get -y install postgresql; \
    apt-get -y install wget; \
    apt-get -y install ; \
    apt-get -y install software-properties-common python-software-properties unzip; \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections; \
    add-apt-repository -y ppa:webupd8team/java; \
    apt-get update; \
    apt-get install -y oracle-java8-installer; \
    apt-get install -y r-base; \
    rm -rf /var/lib/apt/lists/*; \
    rm -rf /var/cache/oracle-jdk8-installer; \
    apt-get clean

RUN pip3 install celery; \
    pip3 install requests; \
    pip3 install bitstring; \
    pip3 install docopt; \
    pip3 install numpy; \
    pip3 install pandas; \
    pip3 install openpyxl; \
    pip3 install xmltodict; \
    pip3 install requests; \
    pip3 install sqlalchemy; \
    pip3 install regex

