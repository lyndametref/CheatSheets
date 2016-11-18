# VirtualBox

Resize disk of a VM (provided installed with a dynamic disk option)

on the host
```
 'C:\Program Files\Oracle\VirtualBox\VBoxManage.exe' modifymedium disk 'Ubuntu.vdi' --resize 15000
```

on the VM
```
 sudo cryptsetup status /dev/mapper/sda5_crypt
 sudo cryptsetup resize /dev/mapper/sda5_crypt
 sudo cryptsetup status /dev/mapper/sda5_crypt
 
 sudo pvdisplay
 sudo pvresize /dev/mapper/sda5_crypt
 sudo pvdisplay
 
 sudo lvdisplay
 sudo lvresize -L 12.17G --resizefs /dev/ubuntu-gnome-vg/root
 sudo lvdisplay
 
 df -h
 ```
