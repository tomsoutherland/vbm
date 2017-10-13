# vbm
perl wrapper for VirtualBox

$ vbm -h

    usage:

    vbm -l [ -L ]
    vbm -n VM -A
    vbm -n VM -b [ -v ]
    vbm -n VM -b [ -o dev1,dev2,dev3,dev4 ]
    vbm -n VM -m /path/to/cdimage.iso
    vbm -n VM -p
    vbm -a X -c XXX -s XX -N VMx,VMy,VMz,... [ -v ]
    vbm -h

    -l : list VirtualBox machines
    -L : long listing includes networks and disks
    -n : name of the VirtualBox machine
    -A : send ACPI power off request
    -b : power on and boot machine
    -m : mount iso on node
    -o : when used with -b, specify the 4
         devices none,floppy,dvd,disk,net
    -r : enable VRDE server
    -a : add X drives to VM(s)
    -c : controller name should be SAS or SCSI
    -s : size of drive(s) in GB
    -N : comma seperated list of VMs to which the disks should be attached
    -p : power off machine
    -v : verbose output
    -h : duh!

ABOUT

vbm is a perl wrapper for the most commonly used features of VirtualBox. When used to boot a virtual machine, it will create a serial port in the virtual machines configuration and attach the shell to that device for console use. You will need to configure the virtual machine to use serial port 0 as the console device. Once this is done, you can use your favorite terminal app to boot and console to the virtual machine.

INSTALL

1) Make sure the script is using your version of perl. Mine is "#!/usr/bin/perl" but yours may be different.

2) Install socat as this is used to connect to the console device.

3) Copy the script to your favorite directory included in your path. Ensure it is executable (chmod +x ~/bin/vbm).

5) Copy vbm-config to ~/.vbm and edit it to point to your installation of VirtualBox and socat.

6) Enjoy never having to use the GUI again (or at least limited need for the GUI).
