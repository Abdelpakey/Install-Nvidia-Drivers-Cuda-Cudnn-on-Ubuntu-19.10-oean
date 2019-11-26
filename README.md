# Install-Nvidia-Drivers-Cuda-Cudnn-on-Ubuntu-19.10-oean

Go to https://www.nvidia.com/Download/driverResults.aspx/154997/en-us figure which version of Nvidia drivers shoud you use for your GPU in my case 440.36.

Go to https://launchpad.net/~graphics-drivers/+archive/ubuntu/ppa to download the version from the last step or most suitable 
version with your linux distro.

Open a terminal and run the following 3 commands


    sudo add-apt-repository ppa:graphics-drivers/ppa
    sudo apt update
    sudo apt install nvidia-driver-440
    
Test if your machine detects the GPU 
    nvidia-smi
# Step 2: Install the CUDA Toolkit (10.0)    

