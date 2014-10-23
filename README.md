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
   1. run "setup.exe" (or "bin\win32\setup.exe" to install 32-bit Matlab under 64-bit Windows)
   2. choose "install manually without using the internet"		
   3. set the "file installation key" to be 25716-63335-16746-06072
   4. setup Matlab with required components
   5. when asked to activate the product select “Activate manually without internet”
   6. select "X:\serial\license.lic" when asked for license file (where "X" is drive letter with this DVD-disk at your computer)
