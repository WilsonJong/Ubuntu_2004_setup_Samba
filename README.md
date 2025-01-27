# Ubuntu_2004_setup_Samba

### 1. Install Samba in Ubuntu.
```
sudo apt update
sudo apt install samba
```

### 2. Check the installation of Samba.
```
whereis samba

* The result should look like this:
  - samba: /usr/sbin/samba /usr/lib/samba /etc/samba /usr/share/samba /usr/share/man/man7/samba.7.gz /usr/share/man/man8/samba.8.gz
```

### 3. Open the Samba configuration file.
```
sudo nano /etc/samba/smb.conf
```

### 4. Add the following command at the bottom of the configuration file.
```
[sambashare]
    comment = Samba on Ubuntu
    path = /target/folder/path
    read only = no
    browsable = yes
```

### 5. Restart the Samba service.
```
sudo service smbd restart
```

### 6. Allow the Samba traffic pass through the firewall.
```
sudo ufw allow samba
```

### 7. Add user to access the Samba service.
```
sudo smbpasswd -a < username>

* After added the new user, Samba service need to restart by using command in step 5.
```
### 8. Connect Samba service from a Windows machine.
```
//targetIP/sambashare
```
