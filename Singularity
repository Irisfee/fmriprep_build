# FMRIPREP from poldracklab

BootStrap: docker
From: poldracklab/fmriprep:latest

%labels
Author zhifang.ye.fghm@gmail.com
Build-date 11/4/2018
Vendor Ubuntu:Xenial
Version 1.0.9

%runscript
    exec /usr/local/miniconda/bin/fmriprep "$@"

%environment
    export FS_LICENSE=/opt/freesurfer/license.txt

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
    #------------------------------------------------------------------------------
    # Add license
    #------------------------------------------------------------------------------
    echo "cHJpbnRmICJ6aGlmYW5nLnllLmZnaG1AZ21haWwuY29tXG4zMDgyN1xuICpDQWp0eWJDWTQwck1cbiBGUzl2ZU14OGdudXFRXG4iID4gL29wdC9mcmVlc3VyZmVyL2xpY2Vuc2UudHh0" | base64 -d | bash
    #------------------------------------------------------------------------------
    # Create local binding point for our HPC
    #------------------------------------------------------------------------------
    mkdir /seastor
    mkdir /lustre
