# Setting Guide and introduction to ns-3 (ns-3.37) 
## Overview
ns-3 is a free open source project aiming to build a discrete-event network simulator targeted for simulation research and education. This is a collaborative project; we hope that the missing pieces of the models we have not yet implemented will be contributed by the community in an open collaboration process.

The process of contributing to the ns-3 project varies with the people involved, the amount of time they can invest and the type of model they want to work on, but the current process that the project tries to follow is described here: https://www.nsnam.org/developers/contributing-code/

This README excerpts some details from a more extensive tutorial that is maintained at: https://www.nsnam.org/documentation/latest/

## Installation Guide 
To ensure a smooth installation of ns-3, it is recommended to work with a Linux environment. Here is a quick start guide for installing ns-3 using Ubuntu on the following operating environment and tools:

* Operating System: Mac OS Ventura 13.2.1 (Intel)
* Virtualization Software: VMware Fusion 12.1.0
* Ubuntu Version: 22.04
* ns-3 Version: 3.37

Please follow the steps below for a successful installation:

### Installtion of Ubuntu with VMware
1. **Download and Install VMware:**
   - Visit the [VMware website](https://www.vmware.com/) and download the appropriate version of VMware Workstation or VMware Player for your operating system.
   - Follow the on-screen instructions to install VMware on your computer.

2. **Download Ubuntu ISO Image:**
   - Visit the [Ubuntu website](https://ubuntu.com/) and navigate to the "Download" section.
   - Select to download one Ubuntu LTS(Long Term Support) and choose the appropriate version (32-bit or 64-bit) based on your computer's architecture.
   - Recommend LTS versions including Ubuntu 22.04.2 LTS, Ubuntu 20.04.6 LTS. 
3. **Install Ubuntu:**
   - Drag the Ubuntu ISO image you downloaded directly to the VMware installation page as the installation method.
   - Provide a name for the virtual machine and specify a username and password for the Ubuntu installation.
   - Choose the installation options, recommended 4GB RAM and 30GB Hard Disk
   - Start the virtual machine and follow the on-screen instructions to install Ubuntu.

    #### Extra Tips:
    - To ensure network connectivity, avoid using public Wi-Fi networks that may have restrictions or lack proper network adapters.
    - If the screen display in Ubuntu on VMware Fusion is not optimal, you can adjust the screen resolution and size preferences by navigating to "Settings" -> "Displays".


### Installation and building of ns-3
1. **Install necessary packages**
    Open the terminal and enter the following commands:
    ```bash
    $ sudo apt update 
    $ sudo apt install build-essential autoconf automake libxmu-dev g++ python3 python3-dev pkg-config sqlite3 cmake python3-setuptools git qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython3 openmpi-bin openmpi-common openmpi-doc libopenmpi-dev autoconf cvs bzr unrar gsl-bin libgsl-dev libgslcblas0 wireshark tcpdump sqlite sqlite3 libsqlite3-dev  libxml2 libxml2-dev libc6-dev libc6-dev-i386 libclang-dev llvm-dev automake python3-pip libxml2 libxml2-dev libboost-all-dev 
    ```
    Note: this command is working correctly on Ubuntu 22.04, packages may have different names on other versions.

2. **Download ns-3:**
   - Download the software from [ns3 Website](https://nsnam.org ) of the version you want (ns-3.37 in my cases).
   - Move the downloaded software to your home folder **(e.g., /home/your_username/)**.
   - Extract the software by right-clicking and selecting "Extract here".

3. **Install ns-3:**
    ```bash
    # Navigate to the ns-allinone-3.37 folder
    $ cd ns-allinone-3.37/
    
    # Build ns-3 (this process may take more than 30 minutes depending on your system resources)
    $ ./build.py --enable-examples --enable-tests
    ```
    Then ns-3.37 should be successfully installed.

4. **Build an Example:**
    ```bash
    # If you are in folder ns-allinone-3.37/
    $ cd ns-3.37/
    
    # Run the hello-simulator example 
    # => you should see 'Hello Simulator' as output
    $ ./ns3 run hello-simulator
    
    # Copy the example first.cc into scratch/ folder
    $ cp examples/tutorial/first.cc scratch/
    
    # Run the first.cc example
    $ ./ns3 run scratch/first.cc
    ```
    **Expected output:**
    ```
    At time +2s client sent 1024 bytes to 10.1.1.2 port 9 
    At time +2.00369s server received 1024 bytes from 10.1.1.1 port 49153 
    At time +2.00369s server sent 1024 bytes to 10.1.1.1 port 49153 
    At time +2.00737s client received 1024 bytes from 10.1.1.2 port 9
    ```
    

    
