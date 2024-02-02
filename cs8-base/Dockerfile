FROM cern/cs8-base:latest

MAINTAINER Matthias J. Schnepf  <matthias.jochen.schnepf@cern.ch>

# CERN CA
RUN update-ca-trust
ADD repos/wlcg-centos8.repo /etc/yum.repos.d/
ADD repos/egi-trustanchors.repo /etc/yum.repos.d/
ADD locale.conf /etc/locale.conf

RUN yum -y update && yum clean all
#RUN yum -y install -y ca-policy-egi-core
RUN yum -y install \
  authconfig \
  boost-devel \
  glibc-headers \
  epel-release \
  which

RUN yum -y install \
attr cyrus-sasl-devel e2fsprogs-devel expat-devel \
file-devel giflib-devel gmp-devel gpm-devel kernel-devel libacl-devel \
libattr-devel libcap-devel libcom_err-devel libcurl-devel libdrm-devel \
libdrm-devel libstdc++-devel libuuid-devel libxml2-devel lockdev-devel \
libjpeg-turbo-devel netpbm-devel popt-devel \
rpm-devel tcl-devel tk-devel openssh-clients \ 
voms-clients-cpp wlcg-voms-cms ca-policy-egi-core \
HEP_OSlibs time tar perl bzip2 gcc freetype glibc-headers glibc-devel \
subversion make gcc gcc-c++ binutils patch wget python3 libxml2-devel \
libX11-devel libXpm-devel libXft-devel libXext-devel bzip2-devel openssl-devel \
ncurses-devel readline-devel mesa-libGL-devel libgfortran.x86_64 glew-devel \
git krb5-workstation libtool-ltdl bc tcsh atlas \
gsl gsl-devel xrootd-client && yum clean all 
