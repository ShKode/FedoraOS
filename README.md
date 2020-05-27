# FedoraOS
My Fedora OS Post Installation Steps. Use it at your own risk. Thanks.

### Update the Operating System:

`$ sudo yum update --refresh -y`

#### Alternative commands:

`$ sudo dnf update --refresh -y`

or 

`$ sudo dnf upgrade --refresh -y`

### Add RPM Repositories:
```shell
$ sudo dnf install --nogpgcheck https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-24.noarch.rpm

$ sudo dnf install --nogpgcheck https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-24.noarch.rpm
```

### Accessibility Tools:
#### GNOME Tweak Tool:
GNOME Tweak tool will help you customize the look and feel of the operating system. You can add tab options, change themes etc.

`$ sudo dnf install gnome-tweak-tool -y`

#### Battery Improvement with TLP:
`$ sudo dnf install tlp`

#### ExFat-Utils and Fuse-ExFat:
To mount exfat file system files and to view the exfat files you need exfat-utils and fuse-exfat applications. Below command installs both.

`$ sudo dnf install exfat-utils fuse-exfat`


### Applications:
#### VIM Editor:
`$ sudo yum install vim`

#### Alternative Editors:
`$ sudo dnf nano`

#### KeePassXC Password Manager:
`$ sudo dnf install keepassxc --refresh -y`

#### VLC Video Player:
`$ sudo dnf install vlc --refresh -y`

#### FireJail and FireTools:
FireJail application helps execute applications under an isolated sandbox. The application will not have access to any unwanted files and resources when running under FireJail. It is kinda like a little Virtual Machine.
FireTools is the GUI.

`$ sudo dnf install firejail`

After installation, try below command to run firefox using FireJail.

`$ firejail firefox`

`$ sudo dnf install firetools`

#### ThunderBird email Client:

Love ThunderBird email client. Have been using it for years and the best part is it is Open-source and Cross platform. Can't beat that, can you?

`$ sudo dnf install thunderbird --refresh -y`

#### Install Zipping Softwares:
Below command includes p7zip (7zip), plugins and unrar applications.

`$ sudo dnf install p7zip p7zip-plugins unrar`


### Uninstall Bloat Softwares:
I do not use below applications, hence I consider them as bloat and delete them immediately.

`$ sudo dnf remove cheese`

Uninstall 'Videos', 'Document Scanner' from Software Center.

### Install DE and ES languages in settings:

While you are at it, check the keyboard layouts.

### Create colours.sh with below code and add it to your /etc/profiles.d/

`$ cd ~` 

`$ vim colours.sh`

```shell
if [[ ! -z \$BASH ]]; then
 if [[ \$USER = "root" ]]; then
  PS1="\[\033[33m\][\[\033[m\]\[\033[31m\]\u@\h\[\033[m\] \[\033[33m\]\W\[\033[m\]\[\033[33m\]]\[\033[m\] # "
 elif [[ $(whoami) = "root" ]]; then
  PS1="\[\033[33m\][\[\033[m\]\[\033[31m\]\u@\h\[\033[m\] \[\033[33m\]\W\[\033[m\]\[\033[33m\]]\[\033[m\] # "
 else
  PS1="\[\033[36m\][\[\033[m\]\[\033[34m\]\u@\h\[\033[m\] \[\033[32m\]\W\[\033[m\]\[\033[36m\]]\[\033[m\] \$ "
 fi
fi
```

`$ sudo mv colours.sh /etc/profile.d/`

Restart terminal for the changes to take effect.

