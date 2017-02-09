# Data-Visualization-with-Deep-Learning

The aim of this project is to explore the possibilities the deep learning can offer to the data visualization domain.
The first step is to train a neuronal network to classify charts.

## Using and understanding tensorFlow 

First of all , we choose tensorFlow API to build and train neuronal networks because :


  - TensorFlow is quite fast and can be used with a GPU to run even faster.  GPU can handle large amounts of data in many streams, performing relatively simple operations which is excatly what we do. (we went from 260 ms to 8 ms on convolutional.py)

  - TensorFlow has a great and active community and a lot of documentation which help develop faster.
  
  - TensorFlow comes with TensorBoard a local web server which allows an user to visualize the execution, the weight values, variables flow, variables evlotion in some categories like graph, images, histograms etc ... This is a plus because tensorFlow API have some parts in "black box" and the neuronal network can be hard to read.
  
 
 > tutorials available [here](https://www.tensorflow.org/tutorials/).
 
 To quickly have global view of this platform, you can see those videos (5 minutes each)
 
 > [TensorFlow](https://www.youtube.com/watch?v=2FmcHiLCwTU)
 
 > [TensorBoard](https://www.youtube.com/watch?v=3bownM3L5zM)

### Installation
To run TensorFlow with python you will need to install :

The folowings instruction was used in linux ubuntu 16.04 64-bits based os.
For futher information or if you have another configuration please consult tensorflow installation guide [here] (https://www.tensorflow.org/get_started/os_setup)

- Python(2.7 or above or 3.5 or above) we choose python 3.5. numpy and Pil lib can be usefull too.
- tensorFlow or tensorflow-gpu (gpu will run faster but requires more installations)

``` sh
sudo apt install python3-pip python-dev
pip3 install tensorflow-gpu
export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-0.12.1-cp35-cp35m-linux_x86_64.whl
sudo pip3 install --upgrade $TF_BINARY_URL
```
If you want to use tensor-gpu and have an Nvidia graphics card:

- CUDA
- CUDNN
*the folowings line can ve added to a bashrc*
``` sh
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64"
export CUDA_HOME=/usr/local/cuda
```
*supposing your cuda repository is at "/usr/local/cuda"*
``` sh
tar xvzf cudnn-8.0-linux-x64-v5.1-ga.tgz
sudo cp -P cuda/include/cudnn.h /usr/local/cuda/include
sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn
sudo apt install libcupti-dev
```

> Download links : [Cuda](https://developer.nvidia.com/cuda-gpus), [Cudnn](https://developer.nvidia.com/cudnn)

#### firstStepMNIST

firstStepMnist.py is a script provided by tensorflow as a demo  and learning support.
   > This script comes with an explanation available [here](https://www.tensorflow.org/tutorials/mnist/beginners/)
 
 To sum up, this script is a basic machine learning program "hello world" like. But, however it allows to understand how 
it works.

First of all, the script downloads the data set and divides it to use it efficiently. A neuronal network must never learn from validation and test data. This will make	laborious the study of any result as there will be no tracks. It may also interfer with the trainning sessions (especially if you are using the deep learning for classification and test it on pictures out of output possibilities).

  Once you have the right dataset, the next steps is modelization. The modelization can be divided in 3 parts:
  
  - Input and Output modelization must be choosen wisely as it will affect the structure of the neuronal network.
  
  - The loss modelization can be summarized in a function representing the loss to determine if the trainnig was efficient.
  
  - The test modelization is the function that we will use to train the algorithm in order to reduce the loss.


#### imagePrep

ImagePrep is a python script, developped by our hands, which can be used as a standalone with the main function or as an API to import.
It uses the PIL lib to manipulates images and os to get images from a directory.

This script has three functions :

- Convert2gray , This function uses 3 parameters the extention of the output pictures,the directory containing the pictures and the directory where the new images will be

- Resize , this function uses 2 more parameters than convert2gray which are the width and height of the new pictures

- Resize2gray do booth with the same number of parameters than resize.

This script allows us to uses images the same parameters no matter their size/color at the beginning, in order to use them in a neuronal network as an input.
















