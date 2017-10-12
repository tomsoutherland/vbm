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

