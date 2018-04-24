#Ubuntu 16.04 Installation guide


#install errors
hdf5
> cannot find -lhdf5_hl and -lhdf5
	Solved by updateing Makefile.config
	INCLUDE_DIRS --> add /usr/include/hdf5/serial
	LIBRARY_DIRS --> add /usr/lib/x86_64-linux-gnu/hdf5/serial

glog, gflag, cmake etc

#-gencode arch 
Remove 20 for nvidia> 9.0

#ATLAS
make build --> don't use -j4 (parallel run)

#MESA
check .so dead links
ln .so.1 to .so


#Compiled without CUDNN library
> RandomGeneratorParameter error
	#include "caffe/proto/caffe.pb.h"
	in /include/caffe/util/rng.hpp

CUDA needs nvidia
#Check compatible version
CUDA 9.1 --> OpenCV 3.4.1

#OpenCV
look at pyimagesearch.com for installing with virtualenv

#Temporal network
git download recursively to get submodules.