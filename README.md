myNewCaffeVersionLearning
=========================

### Cuda 6.5 toolkits
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
new Version learning
<blockquote cite="http://developer.mozilla.org">
  <p>This is a quotation taken from the Mozilla Developer Center.</p>
</blockquote>
