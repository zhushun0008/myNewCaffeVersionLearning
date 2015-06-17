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
##### 3.1 Install pip

```
    sudo apt-get install python-pip
    sudo apt-get install python-dev | python-devel
```

##### 3.2 Install dependency packages
<blockquote>
  <p>
    Cython>=0.19.2
    
    numpy>=1.7.1
    
    scipy>=0.13.2
    
    scikit-image>=0.9.3
    
    scikit-learn>=0.14.1
    
    ***matplotlib>=1.3.1***
    
    ipython>=1.1.0
    
    h5py>=2.2.0
    
    leveldb>=0.191
    
    networkx>=1.8.1
    
    nose>=1.3.0
    
    pandas>=0.12.0
    
    python-dateutil>=1.4,<2
    
    protobuf>=2.5.0
    
    python-gflags>=2.0
 </p>
</blockquote>


```
    $ sudo pip install -r /path/to/caffe-master/python/requirements.txt 
```

* When errors occur, note the information on the screen to install the necessary packages
* 1. ImportError: No module named numpy.distutils.core
    * Fix using following command from [run pip install numpy==1.6.2 before installing requirements.txt](https://github.com/edx/discern/issues/18)
```
    sudo pip install numpy
```
* 2. ImportError: No module named numpy.distutils.core
    * Fix using following command from [scipy official Site](http://www.scipy.org/install.html) 
```
        sudo apt-get install python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose

```
3. The required version of distribute (>=0.6.28) is not available
    * Fix using following command from [](https://pypi.python.org/pypi/setuptools)
```
    # Note that you will may need to invoke the command with superuser privileges to install to the system Python:

    wget https://bootstrap.pypa.io/ez_setup.py -O - | sudo python

```
4. The following required packages can not be built:

                        * freetype
    * Fix using following command from [install freetype](http://stackoverflow.com/questions/20533426/ubuntu-running-pip-install-gives-error-the-following-required-packages-can-no)
    
5. Prerequisites

Caffe has several dependencies.

    CUDA is required for GPU mode.
        library version 7.0 and the latest driver version are recommended, but 6.* is fine too
        5.5, and 5.0 are compatible but considered legacy
    BLAS via ATLAS, MKL, or OpenBLAS.
    Boost >= 1.55
    OpenCV >= 2.4 including 3.0
    protobuf, glog, gflags
    IO libraries hdf5, leveldb, snappy, lmdb

    Use Following Command    
    ```
        sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libboost-all-dev libhdf5-serial-dev
        
    ```
    
    1. install OpenBLAS
        * [OpenBLAS Installation](https://github.com/xianyi/OpenBLAS/wiki/Installation-Guide)
    or
        * sudo apt-get install libopenblas-dev
        
    2. Install Boost
            [how-to-install-boost-on-ubuntu](http://stackoverflow.com/questions/12578499/how-to-install-boost-on-ubuntu)

    ```
        sudo apt-get install libboost-all-dev+
        sudo apt-get install aptitude
    ```
    
    Install ***glog***, ***gflags*** and ***lmdb after*** CMake 2.8.9 installed    
    3. Install required Version for Cmake

    Note that in ***Ubuntu 12.04***, Aptitude will install version ***CMake 2.8.7 by default***, which is ***not supported by Caffe’s CMake build*** (requires at least 2.8.12). As a workaround

    [Install Cmake](http://www.cmake.org/install/)
    ```
        ./bootstrap
        make      
        make install
    ```
    4. Download and Install glog before gflags

    ```
        wget https://google-glog.googlecode.com/files/glog-0.3.3.tar.gz
        tar zxvf glog-0.3.3.tar.gz
        cd glog-0.3.3
        ./configure
        sudo make
        sudo make install
    ```

    5. Download and Install gflags
    
    ```
        wget https://github.com/schuhschuh/gflags/archive/master.zip
        unzip master.zip
        cd gflags-master
        mkdir build && cd build
        export CXXFLAGS="-fPIC" && cmake .. && make VERBOSE=1
        sudo make
        sudo make install
    ```
    
    6. Install IO libraries
    ```
        sudo apt-get install libleveldb-dev
        # sudo pip install lmdb
        # Install liblmdb-dev
        [Download liblmdb-dev](https://launchpad.net/ubuntu/+source/lmdb/0.9.14-1/+build/6496363)
        [Its dependency - liblmdb0](https://launchpad.net/ubuntu/vivid/amd64/liblmdb0)
        
        sudo apt-get install libhdf5-serial-dev
        sudo apt-get install snappy
        sudo apt-get install hdf5-tools
    ```
    

<blockquote>
[...]
Downloading/unpacking matplotlib>=1.3.1 (from -r python/requirements.txt (line 6))
  Downloading matplotlib-1.4.2.tar.gz (50.1Mb): 50.1Mb downloaded
  Running setup.py egg_info for package matplotlib
    The required version of distribute (>=0.6.28) is not available,
    and can't be installed while this script is running. Please
    install a more recent version first, using
    'easy_install -U distribute'.
    
    (Currently using distribute 0.6.24dev-r0 (/usr/lib/python2.7/dist-packages))
    Complete output from command python setup.py egg_info:
    The required version of distribute (>=0.6.28) is not available,

and can't be installed while this script is running. Please

***install a more recent version first***, using

***'easy_install -U distribute'***.

[...]

</blockquote>

1. run following scripts under caffe-master(caffe_root directory)
```
    make all 
    make pycaffe
    make distribute
    export PYTHONPATH=/home/zhuzhu/share_zhu/caffe-master/python
    
```
   1 google/protobuf/stubs/common.h: No such file or directory
   fixed from [install libprotobuf-dev](https://github.com/BVLC/caffe/issues/19)
```
sudo apt-get install libprotobuf-dev

```
libcudart.so.6.0: cannot open shared object file: No such file or directory when run make runtest

```
    export LD_LIBRARY_PATH=:/usr/local/cuda/lib64
```

2. Check ***import caffe***
```
    open ipython notebook
    cd **/caffe-master/python (go to the directory of caffe/python)
    import caffe
```
error fixed
  * Install scikit-image
```

$ sudo pip install scikit-image  
    ImportError: You need `six` version 1.3 or later.
$ sudo pip install six  
$ sudo pip install -U scikit-image  

```

2. 
http://blog.csdn.net/u011333059/article/details/38078617


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


## Case Study
### ***1. Fine-tuning CaffeNet for Style Recognition on “Flickr Style” Data***
* Go to [Finetune Flickr_stype Tutorial Page](http://caffe.berkeleyvision.org/gathered/examples/finetune_flickr_style.html) to see:
   * How to define new model to ***reuse the trained weights***
   * How to adapt learning parameters to speed up learning process
* ***My Command***

***Note: running all following commands under caffe_root directory***

1.Download data
```
    caffe-master$ python examples/finetune_flickr_style/assemble_data.py --workers=-1 --images=2000 --seed 831486
    
```
When it's done, following messages will show on the screen

```
    Downloading 2000 images with 7 workers...
    Writing train/val for 1921(1931 in reference page) successfully downloaded images.
    
```
2.Get trained bvlc net
```
    caffe-master$ ./scripts/download_model_binary.py models/bvlc_reference_caffenet.
    
```
When it's done, the follow messages will be showed on the screen

3.Train fine-tune net with pre-trained net

```
    caffe-master$ ./build/tools/caffe train -solver models/finetune_flickr_style/solver.prototxt -weights models/bvlc_reference_caffenet/bvlc_reference_caffenet.caffemodel -gpu 0
    
```
When it runs, a lot of information will on the screen
```
    [...]
    
    I0828 22:10:04.025378  9718 solver.cpp:46] Solver scaffolding done.
    I0828 22:10:04.025388  9718 caffe.cpp:95] Use GPU with device ID 0
    I0828 22:10:04.192004  9718 caffe.cpp:107] Finetuning from models/bvlc_reference_caffenet/bvlc_reference_caffenet.caffemodel
    
    [...]
    
    I0828 22:18:19.700461 11510 solver.cpp:397] Iteration 20, lr = 0.001
    I0828 22:18:24.924685 11510 solver.cpp:195] Iteration 40, loss = 2.18531
    I0828 22:18:24.924741 11510 solver.cpp:397] Iteration 40, lr = 0.001
    I0828 22:18:30.114858 11510 solver.cpp:195] Iteration 60, loss = 2.4915
    I0828 22:18:30.114910 11510 solver.cpp:397] Iteration 60, lr = 0.001
    I0828 22:18:35.328071 11510 solver.cpp:195] Iteration 80, loss = 2.04539
    I0828 22:18:35.328127 11510 solver.cpp:397] Iteration 80, lr = 0.001
    I0828 22:18:40.588317 11510 solver.cpp:195] Iteration 100, loss = 2.1924
    I0828 22:18:40.588373 11510 solver.cpp:397] Iteration 100, lr = 0.001
    I0828 22:18:46.171576 11510 solver.cpp:195] Iteration 120, loss = 2.25107
    I0828 22:18:46.171669 11510 solver.cpp:397] Iteration 120, lr = 0.001
    
    [...]
    
```
If we are eager to check all the information ,just run the command instead of previous one
```
    caffe-master$ ./build/tools/caffe train -solver models/finetune_flickr_style/solver.prototxt -weights models/bvlc_reference_caffenet/bvlc_reference_caffenet.caffemodel -gpu 0 >&./trainFinetuneNetLog.txt
    
```
