# build-pine64-kernel
simple script to manage building longsleep's pine64 kernel

simple method is to just run this script in /usr/src, and it'll
automatically fetch the latest git repo of the kernel.

    # cd /usr/src
    # kern-compile

It will pause for you to select a branch prior to configuration.

you can also force the script to update the repo with the command-line
option "update"

    # kern-compile update


Next, the script will check for the existance of a configuration file,
pauseing and prompting you to resolve that issue if one is not found.

Once these steps are complete, the build starts.

The script will default to using all available cores during the build
process, but you can restrict it as follows:

    # kern-compile CPUS=3

if the build is successfull, it will attempt to install
the modules and firmware into the default places.

Unless there is a major update, kernel_headers will not be installed.

The kernel image and an initrd will be installed into /boot/k0${kver}/

Finally, the script will pause and ask if you would like the /boot/uEnv.txt
updated with the new kernel information.  


