!SLIDE bullets

# DPK Overview

* Deployment Packages
* Automated deployment method
* Puppet and ACM for Config Management
* _**ONLY**_ way to install PeopleTools 8.57+

!SLIDE bullets

# DPK Archives

* DPK ships with middleware archives *(tarballs)*
* Archives used to install middleware
* Archives are old at release, unpatched
* Only one version of software in Archive directory

!SLIDE bullets

# DPK Patching

* Delivered DPK - `psft_patches.yaml`
* Delivered DPK - Custom Archives
* Custom DPK - Custom Archives

!SLIDE bullets

# Dellivered DPK - `psft_patches.yaml`

* Linux Only
* Uses `psft_patches.yaml` and `$FIXES_DIR`
* Applies patches to delivered archive installation 
* Doc: Install PeopleTools 8.56 
    * Task 3-4: Applying CPUs, POCs, and IDDAs 

!SLIDE bullets

# Delivered DPK - `psft_patches.yaml`

    @@@yaml
    ---
    weblogic_patches:   
      patch_file:    "/opt/io/patches/wls/p21983457_121300_Generic.zip"
    tuxedo_patches:
      patch_file:    "/opt/io/patches/tux/p22389246_121300_Linux-x86-64.zip"

!SLIDE bullets

# Delivered DPK - Custom Archives

* Create your own, fully patches, Archives
    1. Start with base installs
    1. Manually patch them once
    1. Package in tarball
        * Use movement scripts, if needed
    1. Replace tarball in `$PSFT_BASE_DIR/dpk/archives`
    1. Cleanup previous install
    1. Run `puppet apply`


[psadmin.io/blog](https://psadmin.io/2017/05/02/apply-cpu-patches-with-deployment-packages)

!SLIDE bullets

# Custom Archives - Package

    @@@bash
    # package
    TUX_HOME=/opt/oracle/psft/pt/tux
    TUX_VERSION=12.2.2.0.0.rp30
    TUX_ARCHIVE_DIR=/opt/io/archives/tux
    
    tar -zcf "${TUX_ARCHIVE_DIR?}/pt-tuxedo${TUX_VERSION?}.tgz" \
        -C "${TUX_HOME?}" .

!SLIDE bullets

# Custom Archives - Package

    @@@bash
    $ tree -L 2 /opt/io/archives/
    /opt/io/archives/
    ├── jdk
    │   ├── pt-jdk1.8.0_144.tgz
    │   └── pt-jdk1.8.0_171.tgz
    ├── pt
    │   ├── pt-pshome8.56.07.tgz
    │   └── pt-pshome8.56.09.tgz
    ├── tux
    │   ├── pt-tuxedo12.2.2.0.0.rp26.tgz
    │   └── pt-tuxedo12.2.2.0.0.rp30tgz
    └── wls
        ├── pt-weblogic12.2.1.20180117.tgz
        └── pt-weblogic12.2.1.20180417.tgz    

!SLIDE bullets

# Custom Archives - Cleanup

    @@@bash
    # cleanup
    sudo rm -rf /opt/oracle/psft/pt/tux
    sudo rm -rf /opt/oracle/psft/cfg/appserv
    sudo rm -rf /opt/oracle/psft/db/oraInventory
    sudo rm /opt/oracle/psft/dpk/archives/pt-tuxedo*

!SLIDE bullets

# Custom Archives - Add New Archive

    @@@bash
    # link
    TUX_VERSION=12.2.2.0.0.rp30
    TUX_ARCHIVE_DIR=/opt/io/archives/tux
    DPK_ARCHIVE_DIR=/opt/oracle/psft/dpk/archives
    
    sudo ln -s ${TUX_ARCHIVE_DIR?}/pt-tuxedo${TUX_VERSION?}.tgz ${DPK_ARCHIVE_DIR?}

!SLIDE bullets

# DPK Overview

* 

!SLIDE bullets

# DPK Overview

* 

!SLIDE bullets

# DPK Overview

* 

!SLIDE bullets

# DPK Overview

* 

!SLIDE bullets

# DPK Overview

* 

!SLIDE bullets

# DPK Overview

* 

!SLIDE bullets

# DPK Overview

* 

