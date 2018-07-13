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

