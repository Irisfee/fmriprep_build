# FMRIPREP from poldracklab

BootStrap: docker
From: poldracklab/fmriprep:latest

%labels
Author zhifang.ye.fghm@gmail.com/yzhao17@uoregon.edu
Build-date 2019.3.7
Vendor Ubuntu:Xenial
Version 1.1.8

%runscript
    exec /usr/local/miniconda/bin/fmriprep "$@"

%environment
    export FS_LICENSE=/opt/freesurfer/license.txt

%post
    #------------------------------------------------------------------------------
    # Add license
    #------------------------------------------------------------------------------
    echo "cHJpbnRmICJ6aGlmYW5nLnllLmZnaG1AZ21haWwuY29tXG4zMDgyN1xuICpDQWp0eWJDWTQwck1cbiBGUzl2ZU14OGdudXFRXG4iID4gL29wdC9mcmVlc3VyZmVyL2xpY2Vuc2UudHh0" | base64 -d | bash

