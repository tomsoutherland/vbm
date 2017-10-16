# vbm
perl wrapper for VirtualBox

usage:

    vbm -l [ -L ] [ -N VMx,VMy,VMz,... ]
    vbm -d
    vbm -e
    vbm -E X,network -n VM
    vbm -w X,Y -n VM
    vbm -B -n VM [ -O OS_TYPE ] [ -M RAM_MB ] [ -c CPUs ] [ -H ]
    vbm -C VM,CLONE
    vbm -b -n VM [ -V ] [ -o DEVx,DEVy,... ] [ -v ]
    vbm -m /path/to/cdimage.iso -n VM -c XXX
    vbm -p -n VM
    vbm -P -n VM
    vbm -A DISKUUID -c XXX -N VMx,VMy,VMz,... [ -v ]
    vbm -a X -c XXX -s XX -N VMx,VMy,VMz,... [ -v ]
    vbm -r DISKUUID -N VMx,VMy,VMz,... [ -R ] [ -v ]
    vbm -D -n VM -R
    vbm -h

    -l : list VMs
    -d : list VirtualBox disks
    -e : list VirtualBox networks
    -E : set network NIC X attachment for VM
    -w : set network X attached (1) or disconnected (0)
    -L : long listing includes networks and disks
    -n : name of the VM
    -B : build or modify VM
    -C : create CLONE from VM
    -O : OS type (Solaris_64,OpenSolaris_64,Solaris11_64) see "VBoxManage list ostypes"
    -H : make VM headless (remove graphics controller, disable keyboard and mouse)
    -M : amount of RAM for this VM
    -b : power on and boot machine
    -m : mount iso on node
    -o : when used with -b, specify the BIOS boot device order (dvd, disk, net, floppy)
    -V : enable VRDE server
    -a : add X drives to VM(s)
    -c : controller name. Use SAS or SCSI for shared. Single attach may use IDE or SATA.
    -s : size of drive(s) in GB
    -N : comma seperated list of VMs to which the disk operation shoud be performed
    -r : detach disk UUID from the given nodes
    -R : delete the disk medium
    -A : attach disk UUID to the given nodes
    -D : delete the VM
    -p : power off machine
    -P : send ACPI power off request
    -v : verbose output
    -h : duh!

ABOUT

vbm is a perl wrapper for the most commonly used features of VirtualBox. When used to boot a virtual machine, it will create a serial port in the virtual machines configuration and attach the shell to that device for console use. You will need to configure the virtual machine to use serial port 0 as the console device. Once this is done, you can use your favorite terminal app to boot and console to the virtual machine.

When adding drives to multiple machines, the drives will be created as "--variant Fixed" and attached as "--mtype shareable".

INSTALL

1) Make sure the script is using your version of perl. Mine is "#!/usr/bin/perl" but yours may be different.

2) Install socat as this is used to connect to the console device.

3) Copy the script to your favorite directory included in your path. Ensure it is executable (chmod +x ~/bin/vbm).

5) Copy vbm-config to ~/.vbm and edit it to point to your installation of VirtualBox and socat.

6) Enjoy never having to use the GUI again (or at least limited need for the GUI).
