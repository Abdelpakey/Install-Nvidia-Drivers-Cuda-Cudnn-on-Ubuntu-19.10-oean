# Install-Nvidia-Drivers-Cuda-Cudnn-on-Ubuntu-19.10-oean

Go to https://www.nvidia.com/Download/driverResults.aspx/154997/en-us figure which version of Nvidia drivers shoud you use for your GPU in my case 440.36.

Go to https://launchpad.net/~graphics-drivers/+archive/ubuntu/ppa to download the version from the last step or most suitable 
version with your linux distro.

Open a terminal and run the following 3 commands


    sudo add-apt-repository ppa:graphics-drivers/ppa
    sudo apt-get update
    sudo apt-get install nvidia-driver-440
    
Test if your machine detects the GPU 
    nvidia-smi
# Step 2: Install the CUDA Toolkit (10.0)  

If you have any Cuda PPAS remove by
    sudo rm /etc/apt/sources.list.d/cuda*
    sudo apt remove --autoremove nvidia-cuda-toolkit
Recommended to also remove all NVIDIA drivers before installing new drivers:
    sudo apt remove --autoremove nvidia-*
Then update the system:
    sudo apt update
  
Install the key:
    sudo apt-key adv --fetch-keys  http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub
Fell free to login to http://developer.download.nvidia.com/compute/cuda/repos/ to choose the proper linux disto for your machine 

 Add the repos:
    
    sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64 /" > /etc/apt/sources.list.d/cuda.list'

    sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64 /" >      /etc/apt/sources.list.d/cuda_learn.list'
    
Here  we select ubuntu 18.04 because it has cuda 10.0    
Update the system again:
    sudo apt-get update

Install CUDA 10.0:
    sudo apt install cuda-10-0

Install CUDNN 7.4:

    go to https://developer.nvidia.com/cudnn
    Select CUDNN 7.4 for CUDA 10.0
    download the cuDNN v7.4 Library for Linux (tar file)
    open a terminal in the directory the tar file is located
    unzip the tar file using the command
    tar -xzvf cudnn-10.0-linux-x64-v7.tgz
    run the following commands to move the appropriate files to the CUDA folder
    sudo cp cuda/include/cudnn.h /usr/local/cuda/include
    sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
    sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*

    



   

