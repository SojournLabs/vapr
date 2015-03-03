# vapr
[Sojourn Labs](http://www.sojournlabs.com) is designing a new type of electric vehicle. As part of its operations, it runs a private cloud infrastructure to host the software it uses. This is the master repository containing all of our (hackish) scripts for anyone that would like to replicate our setup, warts and all.

Getting started
===============
Run `git submodule init` to pull the files you'll need to get started. Note that commands below are run from their corresponding submodule directories rather than the relative paths shown.

For our setup, we do the following:
 1. Set up boot server certificates.
    1. Set up a root certificate authority using `certs/ca_create`.
    2. Set up a boot client certificate using `certs/new_client`.
    3. Set up a boot server certificate using `certs/new_server`.
 2. Set up the iPXE boot client disk image.
    1. Put the boot client certificate files from step 1.2 above into the `netboot/config` directory.
    2. Configure `netboot/config/bootscript.ipxe`.
    3. Install our own root certificate authority certificate (step 1.1) into `netboot/config/cacert.pem`.
    3. Run the `netboot/build_ipxe` to generate the disk images.
    4. Write the relevant disk image from `netboot/build` to bootable media.
 3. Set up an iPXE boot server. (TODO)