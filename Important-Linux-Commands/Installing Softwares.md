### Installing Open-MPI

#### First, decompress the downloaded file from [https://www.open-mpi.org/software/ompi/](https://www.open-mpi.org/software/ompi/). Replace with correct version in openmpi-x.x.x
 ```
 tar -xvf openmpi-x.x.x
 cd openmpi-x.x.x
 ```
#### Then, configure with correct path in prefix options
 ```
 ./configure --prefix="{PATH_TO_INSTALL_OPENMPI}"
 ```
#### Then make all and install with availabe core options in -j{NO_OF_CORES_TO_USE} 
 ```
 make -j{NO_OF_CORES_TO_USE} all
 make install
 ```
#### Then edit ~/.bashrc to add it to PATH and LD_LIBRARY_PATH
 ```
 export PATH="$PATH:{OPENMPI_INSTALLATION_PATH}/bin"
 export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:{OPENMPI_INSTALLATION_PATH}/lib/"
 ```
#### Installing CuDNN
### To obtain the cuDNN library, you first need to create an account (free) with NVIDIA. From there, you can download cuDNN. After downloading and cd to the downloaded path
 ```
 tar xvzf cudnn-8.0-linux-x64-v5.0-ga.tgz
 sudo cp -P cuda/include/cudnn.h {CUDA_HOME_PATH}/include
 sudo cp -P cuda/lib64/libcudnn* {CUDA_HOME_PATH}/lib64
 sudo chmod a+r {CUDA_HOME_PATH}/include/cudnn.h {CUDA_HOME_PATH}/lib64/libcudnn*
 ```
 
#### Then edit ~/.bashrc to add it to PATH and LD_LIBRARY_PATH

 ```
 export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:{CUDA_HOME_PATH}/lib64:{CUDA_HOME_PATH}/extras/CUPTI/lib64"
 ```
