
## Building gargoyle LineageOS GSIs ##

Set up your environment by referring to [LineageOS Wiki](https://wiki.lineageos.org/devices/TP1803/build) (mainly "Install the build packages" and "Install the repo command").

Set Up Environment

    mkdir ~/git/

Clone the resources repository to **~/git/**

    git clone https://github.com/rumplestilzken/lineageos_20_td.git ~/git/lineage_20_td

Create a new working directory for your LineageOS build and navigate to it:

    mkdir ~/git/lineage-20-build-td; cd ~/git/lineage-20-build-td

Initialize your LineageOS workspace:

    repo init -u https://github.com/LineageOS/android.git -b lineage-20.0

Clone both this and the patches repos:

    git clone https://github.com/rumplestilzken/lineage_build_unified lineage_build_unified -b lineage-20-td
    git clone https://github.com/rumplestilzken/lineage_patches_unified lineage_patches_unified -b lineage-20-td

Run repo sync
    
    repo sync

Run update.sh
    
    ~/git/lineageos_20_td/update.sh

Get Device Tree

    git clone https://github.com/rumplestilzken/device_unihertz_gargoyle /usr/local/lineage-20-build-td/device/unihertz
 
Finally, start the build script - for example, to build for all supported archs:

    bash lineage_build_unified/buildbot_unified.sh treble gargoyle gargoyleG

Be sure to update the cloned repos from time to time!

---

Note: VNDKLite targets are generated from built images instead of source-built - refer to [sas-creator](https://github.com/AndyCGYan/sas-creator).

---

This script is also used to make device-specific and/or personal builds. To do so, understand the script, and try the `device` and `personal` keywords.
