### Installing Open-MPI:

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
#### Then edit ~/.bashrc to add PATH and LD_LIBRARY_PATH
 ```
 export PATH="$PATH:{OPENMPI_INSTALLATION_PATH}/bin"
 export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:{OPENMPI_INSTALLATION_PATH}/lib/"
 ```
