# Build instructions:

## Windows:

In order to build project make sure you have  [**Visual C++ Compiler November 2013 CTP**](https://www.microsoft.com/en-us/download/details.aspx?id=41151) installed.
Open **nheqminer.sln** under **nheqminer/nheqminer.sln** and build. 

## Linux (Ubuntu/Debian based, Tested on Ubuntu 16.04):
To build under Ubuntu Linux make sure you have Qt5 installed. You can install it manually from [Qt website](https://www.qt.io/) or install it from the command line: `sudo apt-get install qt5-default`.
Open a terminal and cd to nheqminer root folder and run the following commands (make sure you have qmake in your PATH, if installed manually from Qt website you will have to export it to your PATH):
  - `mkdir build`
  - `cd build`
  - `qmake ../nheqminer/nheqminer.pro`
  - `make`

## Linux (non Ubuntu/Debian based distros):
If you are using a Linux distribution that is not Ubuntu/Debian based you can still build but you will have to build boost 1.68 and copy the static libraries [**libboost_log.a**  **libboost_system.a**  **libboost_thread.a**] over to **nheqminer/libs/linux_ubuntu** and follow the Ubuntu/Debian instructions (installing qt5 qmake accordingly to systems package manager).

# Run instructions:

If run without parameters, miner will start mining with 75% of available virtual cores on NiceHash. Use parameter -h to learn about available parameters:

        -h              Print this help and quit
        -l [location]   Location (eu, usa, hk, jp)
        -u [username]   Username (bitcoinaddress)
        -p [password]   Password (default: x)
        -t [num_thrds]  Number of threads (default: number of sys cores)
        -d [level]      Debug print level (0 = print all, 5 = fatal only, default: 2)
        -b [hashes]     Run in benchmark mode (default: 100 hashes)
        -a [port]       Local API port (default: 0 = do not bind)
        
Example to run benchmark:

        nheqminer_x64_AVX.exe -b
        
Example to run with full logging (including network dump):

        nheqminer_x64_AVX.exe -d 0
        
Example to mine with your own BTC address and worker1 on USA server:

        nheqminer_x64_AVX.exe -l usa -u YOUR_BTC_ADDRESS_HERE.worker1
