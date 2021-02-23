# class-edge

class-edge provides the software for the edges of a smart city, i.e. smart cameras, in the context of the European Project CLASS (H2020, G.A. 780622). This branch has been developed by BSC based on the main one provided by Università di Modena e Reggio Emilia.

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
                        python3-dev \
                        libgdal-dev \
                        libcereal-dev \
                        libyaml-cpp-dev \
                        python-numpy
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
./demo ${USE_PIPES} ${CAMERA_ID} ${PIPE_PATH_WRITE} ${PIPE_PATH_READ} ${SHOW} ${STORE_RESULT}
```
<!-- ./demo ${USE_SOCKET} ${CAMERA_ID} ${PORT_NUMBER} -->

The command above will launch the demo executable previously generated. If `${USE_PIPES} == 1`, then two pipes will be created to communicate with the COMPSs workflow executed in the same machine (by default they are /tmp/pipe_yolo2COMPSs and /tmp/pipe_COMPSs2yolo). `${CAMERA_ID}` refers to the video and camera configuration that will be used, by default **20939**. `${SHOW}` refers to display the output of the tkDNN on top of the video being processed, and `${STORE_RESULT}` refers to storing this output into a result.mp4 file.

<!--a socket connection will be open to communicate with the COMPSs workflow. `${CAMERA_ID}` refers to the video and camera configuration that will be used, by default **20939**. And the port number specified by `${PORT_NUMBER}` is the port that the socket will be listening to. By default, if no port number is specified it will use the port **5559**. -->
