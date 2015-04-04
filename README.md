# vapr
[Sojourn Labs](http://www.sojournlabs.com) is designing a new type of electric vehicle. As part of its operations, it runs a private cloud infrastructure to host the software it uses. This is the master repository containing all of our (hackish) scripts for anyone that would like to replicate our setup, warts and all.

Getting started
===============
Run `git submodule init` to pull the files you'll need to get started. Note that commands below are run from their corresponding submodule directories rather than the relative paths shown.

For our setup, we do the following:
 1. Set up boot server certificates.
 2. Set up the iPXE boot client disk image.
 3. Set up a CoreOS disk image and distribute it.
 4. Boot using the iPXE boot client.
