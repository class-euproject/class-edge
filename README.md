# class-edge

class-edge provides the software for the edges of a smart city, i.e. smart cameras, in the context of the European Project CLASS (H2020, G.A. 780622)

## Dependencies

This projects depends on: 

  * CUDA 10.0
  * CUDNN 7.603
  * TENSORRT 6.01
  * OPENCV 3.4
  * yaml-cpp 0.5.2 
  * Eigen
  * GDal
  * cmake v3.15

```
sudo apt-get install -y libeigen3-dev \
                        python3-matplotlib \
                        python-dev \
                        libgdal-dev \
                        libcereal-dev \
                        libyaml-cpp-dev \
                        python-numpy
```

required for tkCommon
```
sudo apt-get install -y libgles2-mesa-dev libglew-dev libmatio-dev libpcap-dev
bash scripts/install-glfw-3.3.sh
```

## Installation 

```
cd class-edge
git submodule update --init --recursive 
cd tkDNN
mkdir build
cd build
cmake ../
make
```

The previous procedure generates an executable called `demo`.


## Execution

To execute the tkDNN, use the following command:
```
./demo ${PORT_NUMBER}
```

The command above will launch the demo executable previously generated, and the port number specified is the port that the socket will be listening to. By default, if no port number is specified it will use the port **5559**.
