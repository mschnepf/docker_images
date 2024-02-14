FROM cern/cc7-base:latest

MAINTAINER Matthias J. Schnepf  <matthias.jochen.schnepf@cern.ch>

RUN update-ca-trust


ADD repos/UMD-4-updates.repo /etc/yum.repos.d/
ADD repos/egi-trustanchors.repo /etc/yum.repos.d/
ADD nss-pam-ldapd-0.9.9-3.el8.x86_64.rpm /root/

ADD http://repository.egi.eu/sw/production/cas/1/GPG-KEY-EUGridPMA-RPM-3 /etc/pki/rpm-gpg/

RUN yum -y update && yum clean all
RUN yum -y groupinstall 'Development Tools' && yum clean all
RUN yum -y install \
ca-policy-egi-core authconfig boost-devel glibc-headers globus-proxy-utils \
globus-gass-copy-progs which \
attr cyrus-sasl-devel e2fsprogs-devel expat-devel \
file-devel giflib-devel gmp-devel gpm-devel kernel-devel libacl-devel \
libattr-devel libcap-devel libcom_err-devel libcurl-devel libdrm-devel \
libdrm-devel libstdc++-devel libuuid-devel libxml2-devel lockdev-devel \
libjpeg-turbo-devel netpbm-devel popt-devel python-devel \
rpm-devel tcl-devel tk-devel openssh-clients PyXML \ 
voms-clients3 wlcg-voms-cms emi-wn \
HEP_OSlibs time tar perl bzip2 gcc freetype glibc-headers glibc-devel \
subversion make gcc gcc-c++ binutils patch wget python python3 libxml2-devel \
libX11-devel libXpm-devel libXft-devel libXext-devel bzip2-devel openssl-devel \
ncurses-devel readline-devel mesa-libGL-devel libgfortran.x86_64 glew-devel \
git krb5-workstation libtool-ltdl lcg-util.x86_64 bc tcsh atlas \
gsl gsl-devel xrootd-client sssd dcap-tunnel-gsi man-db \
vim htop strace && yum clean all

RUN rpm -i /root/nss-pam-ldapd-0.9.9-3.el8.x86_64.rpm && rm -rf /root/nss-pam-ldapd-0.9.9-3.el8.x86_64.rpm
