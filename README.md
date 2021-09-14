# VASP
 VASP 是一个用于模拟量子力学分子动力学的复杂软件包。
 
 以下是VASP在 Ubuntu 上的编译过程。
 
1．	安装Ubuntu 18.04.2，下载地址：http://cdimage.ubuntu.com/releases/18.04.2/release/ubuntu-18.04.2-server-ppc64el.iso

2．	安装开发环境
sudo apt-get install build-essential gcc-8 g++-8 gfortran-8 libopenmpi-dev libopenmpi1.6 openmpi1.6 libfftw3-double3 libfftw3-single3 libfftw3-dev libscalapack-openmpi-dev

3．	针对vasp.5.4.4打patch
cp arch/makefile.include.linux_gnu makefile.include

patch -p1 < ../vasp544_op_gnu_ips.patch

4．	编译过程
export OMPI_CC=gcc

export OMPI_CXX=g++

export OMPI_FC=gfortran

make std

make gam

make ncl
