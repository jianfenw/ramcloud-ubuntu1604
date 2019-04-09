# Title: ramcloud-ubuntu1604
This directory has the installation package for RAMCloud on the Ubuntu 16.04 machine.

# What is RAMCloud
RAMCloud is a DRAM-based distributed data storage system. It provides super-high-speed, and super-low-latency data storage for large-scale datacenter applications. The design enables the scenario where a large number of servers in a datacenter require low-latency access to a LARGE and DURABLE data storage.

# Necessary Tools for installing RAMCloud
- GNU Make (Anything reasonably recent)
- GNU g++ (4.9.x)
- git (>= 1.6.0)
- Perl (Anything reasonably recent)
    - For mergedeps.pl, which automatically inserts included headers in source files into the make dependencies.
- Python 2.6, epydoc
- Boost
    - If you're having issues with Boost on  _Ubuntu_, check boost ticket #3844.
- pcre
- Doxygen 1.7.1
- protocol buffers
    - If you're getting lots of undefined reference errors during linking, it's likely that your libprotobuf is compiled with a different library ABI than RAMCloud. Check GCC's [Dual ABI](https://gcc.gnu.org/onlinedocs/libstdc++/manual/using_dual_abi.html)  page and the "GLIBCXX_USE_CXX11_ABI" flag in GNUMakefile.
- ZooKeeper
- java and javac (>= 1.7.0_25)

# Installing for RAMCloud
## 1.Clone
`git clone git@bitbucket.org:guozetang/ramcloud.git`
## 2.Install the packages and RAMCloud
**Note:**You need use the root privileges to run this script.
```bash
cd ramcloud
sudo su
./install.sh
```
If it doesn't finish the installing of RAMCloud, please input the command as follow.
```bash
source /etc/profile
./install_ramcloud.sh
```
## 3. Update the PATH
```bash
source /etc/profile
ldconfig
ldconfig -p | grep ramcloud
```
# Learn More about RAMCloud
- [Stanford RAMCloud](https://ramcloud.stanford.edu/wiki/display/ramcloud) 
- [Install RAMCloud](https://ramcloud.atlassian.net/wiki/spaces/RAM/pages/6848614/General+Information+for+Developers)
