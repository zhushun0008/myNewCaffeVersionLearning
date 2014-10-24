myNewCaffeVersionLearning
=========================

### 1. Cuda 6.5 toolkits
1. Download cuda-6.5 from NVIDIA
2. Uninstall the current driver and install new driver and cuda-6.5 toolkits
    ```
     1. sudo service lightdm stop (stop display)
     
     2. CRTL + ALT + F1 (Change to command line)
     
     3. sudo sh cuda-6.5-run
    ```
3. Setup Environment
   ```
   export PATH=/usr/local/cuda-6.5/bin:$PATH
   
   export LD_LIBRARY_PATH=/usr/local/cuda-6.5/lib64:$LD_LIBRARY_PATH
   ```
   
4. GPU Test
   * Go to 
   ```
   
   ```
5. 
new Version learning
<blockquote cite="http://developer.mozilla.org">
  <p>This is a quotation taken from the Mozilla Developer Center.</p>
</blockquote>


### 2. Matlab Wapper
#### 1. install Matlab under Linux
* download address: <http://xxxx.need.to.add.com>
* Install Process
<blockquote>
  <p>
    1. run "setup.exe" (or "bin\win32\setup.exe" to install 32-bit Matlab under 64-bit Windows)
    
    2. choose ***"install manually without using the internet"***		
    
    3. set the "file installation key" to be ***25716-63335-16746-06072***
    
    4. setup Matlab with required components
    
    5. when asked to activate the product select ***“Activate manually without internet”***
    
    6. select "X:\serial\license.lic" when asked for license file (where "X" is drive letter amounted under /mnt/* of my Linux)
  </p>
</blockquote>

### 3. Python Wapper
* run the following command and be sure you are in the caffe-root directory
```
    for req in $(cat python/requirements.txt); do sudo pip install $req; done

```

#### install cmake 2.8.9

Note that in ***Ubuntu 12.04***, Aptitude will install version ***CMake 2.8.7 by default***, which is ***not supported by Caffe’s CMake build*** (requires at least 2.8.8). As a workaround
if you are using Ubuntu 12.04 you can try the ***following steps to install CMake 2.8.9***:

```
    sudo add-apt-repository ppa:ubuntu-sdk-team/ppa -y
    
    sudo apt-get -y update
    
    sudo apt-get install cmake
```
#### Install ***glog***, ***gflags*** and ***lmdb after*** CMake 2.8.9 installed
1.Download and Install glog before gflags
```
    wget https://google-glog.googlecode.com/files/glog-0.3.3.tar.gz
    
    tar zxvf glog-0.3.3.tar.gz
    
    cd glog-0.3.3
    
    ./configure
    
    make && make install
    
```
2. Download and Install gflags
```
    wget https://github.com/schuhschuh/gflags/archive/master.zip
    
    unzip master.zip
    
    cd gflags-master
    
    mkdir build && cd build
    
    export CXXFLAGS="-fPIC" && cmake .. && make VERBOSE=1
    
    make && make install
```
3. Download and Install lmdb
```
    git clone git://gitorious.org/mdb/mdb.git
    
    cd mdb/libraries/liblmdb
    
    make && make install
```    

### Get trained Models
* run python script
    * dependency
    * pip search yaml
    *   sudo pip install yaml


### Case Study
#### 1. Fine-tuning CaffeNet for Style Recognition on “Flickr Style” Data
[finetune_flickr_stype Tutorial http://caffe.berkeleyvision.org/gathered/examples/finetune_flickr_style.html]
