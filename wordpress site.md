●setup a lamp server and host a wordpress site on your local system Note: Don't install php directly using yum or apt-get
●compile it from source using PREFIX with /usr/local/php directory

In order to compile PHP from source you need to install few tools and libraries. First you need EPEL repository to be enabled.

EPEL (Extra Packages for Enterprise Linux) is open source and free community based repository project from Fedora team which provides 100% high quality add-on software packages for Linux distribution including RHEL (Red Hat Enterprise Linux), CentOS, and Scientific Linux.

# yum install epel-release -y

Below are required packed to compile php

# yum install autoconf libtool re2c bison libxml2-devel bzip2-devel libcurl-devel libpng-devel libicu-devel gcc-c++ libmcrypt-devel libwebp-devel libjpeg-devel openssl-devel -y

Download the php 7.2.3 package and unpack

# curl -O -L https://github.com/php/php-src/archive/php-7.2.3.tar.gz
# tar -zxvf php-7.2.3.tar.gz
# cd php-src-php-7.2.3
