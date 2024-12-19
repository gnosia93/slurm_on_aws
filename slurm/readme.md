


## slurm install ##

* Download source from https://www.schedmd.com/download-slurm/

* As of Dec 20 2024, version 24.11.0 is the lastest version, and download url is https://download.schedmd.com/slurm/slurm-24.11.0.tar.bz2  

* execute following commands in each node
  ```
  sudo apt install -y build-essential fakeroot devscripts equivs
  curl https://download.schedmd.com/slurm/slurm-24.11.0.tar.bz2 -o slurm-24.11.0.tar.bz2
  tar -xaf slurm-24.11.0.tar.bz2
  cd slurm-24.11.0
  sudo mk-build-deps --install --tool='apt-get -o Debug::pkgProblemResolver=yes --no-install-recommends --yes' debian/control
  debuild -b -uc -us
  ```





Super Quick Start 
* Make sure the clocks, users and groups (UIDs and GIDs) are synchronized across the cluster.
* Install MUNGE for authentication. Make sure that all nodes in your cluster have the same munge.key. Make sure the MUNGE daemon, munged, is started before you start the Slurm daemons.
Download the latest version of Slurm.
* Install Slurm using one of the following methods:
  * Build Manually from source (for developers or advanced users)
NOTE: Some Linux distributions may have unofficial Slurm packages available in software repositories. SchedMD does not maintain or recommend these packages.
Build a configuration file using your favorite web browser and the Slurm Configuration Tool.
NOTE: The SlurmUser must exist prior to starting Slurm and must exist on all nodes of the cluster.
NOTE: The parent directories for Slurm's log files, process ID files, state save directories, etc. are not created by Slurm. They must be created and made writable by SlurmUser as needed prior to starting Slurm daemons.
NOTE: If any parent directories are created during the installation process (for the executable files, libraries, etc.), those directories will have access rights equal to read/write/execute for everyone minus the umask value (e.g. umask=0022 generates directories with permissions of "drwxr-r-x" and mask=0000 generates directories with permissions of "drwxrwrwx" which is a security problem).

* Install the configuration file in <sysconfdir>/slurm.conf.
NOTE: You will need to install this configuration file on all nodes of the cluster.
* systemd (optional): enable the appropriate services on each system:
  Controller: sudo systemctl enable slurmctld
  Database: sudo systemctl enable slurmdbd
  Compute Nodes: sudo systemctl enable slurmd
* Start the slurmctld and slurmd daemons.
