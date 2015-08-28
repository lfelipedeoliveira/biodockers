FROM debian:jessie
MAINTAINER lfelipedeoliveira, felipe@lfelipedeoliveira.com

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -y; \
    apt-get install -y openjdk-7-jre-headless file; \
    apt-get install -y gcc; \
    apt-get install -y make; \
    apt-get install -y bioperl, \
    apt-get clean

ADD https://github.com/lfelipedeoliveira/biodockers/blob/master/pgap-modif.tar.gz /tmp/pgap-modif.tar.gz
RUN mkdir /pgap; \
    tar xzf /tmp/pgap-modif.tar.gz --directory /pgap; \
    rm /tmp/pgap-modif.tar.gz

ADD http://mafft.cbrc.jp/alignment/software/mafft-7.245-with-extensions-src.tgz /tmp/mafft-7.245-with-extensions-src.tgz
RUN mkdir //mafft; \
    tar xzf /tmp/mafft-7.245-with-extensions-src.tgz --directory /mafft --strip-components=1; \
    rm /tmp/mafft-7.245-with-extensions-src.tgz

WORKDIR /mafft/core
RUN make clean; \
    make; \
    make install

ADD http://evolution.gs.washington.edu/phylip/download/phylip-3.696.tar.gz /tmp/phylip-3.696.tar.gz
RUN mkdir /phylip
    tar xzf /tmp/phylip-3.696.tar.gz --directory /phylip --strip-components=1; \
WORKDIR /phylip/src
RUN make -f Makefile.unx install

ADD http://micans.org/mcl/src/mcl-14-137.tar.gz /tmp/mcl-14-137.tar.gz
RUN mkdir /mcl; \
    tar xzvf /tmp/mcl-14-137.tar.gz --directory /tmp --strip-components=1; \
WORKDIR /tmp/mcl-14-137
RUN ./configure --prefix=/mcl; \
    make install

WORKDIR /
ADD ftp://ftp.ncbi.nih.gov/blast/executables/release//2.2.12/blast-2.2.12-x64-linux.tar.gz /tmp/blast-2.2.12-x64-linux.tar.gz
RUN tar xzvf /tmp/blast-2.2.12-x64-linux.tar.gz; \

RUN (echo y;echo o conf prerequisites_policy follow;echo o conf commit)|cpan; \
    cpan Bio::AlignIO
