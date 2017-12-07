# FMRIPREP from poldracklab

BootStrap: docker
From: poldracklab/fmriprep:latest

%runscript
    exec /usr/local/miniconda/bin/fmriprep "$@"

%environment

%labels
Author zhifang.ye.fghm@gmail.com
Build-date 7/12/2017
Vendor Ubuntu:Xenial
Version 1.0.0

%post
    #------------------------------------------------------------------------------
    # Fix possible permission issue
    #------------------------------------------------------------------------------
    chmod -R a+rX /usr/local/miniconda
    chmod +x /usr/local/miniconda/bin/*
    #------------------------------------------------------------------------------
    # Change timezone to Shanghai
    #------------------------------------------------------------------------------
    ln -fs /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
    dpkg-reconfigure --frontend noninteractive tzdata
