# fedora-configs
# FEDORA WORKSTATION 33

# GNOME TWEAKS
sudo dnf install gnome-tweaks 

# GIT AND GH
sudo dnf install 'dnf-command(config-manager)'
sudo dnf config-manager --add-repo https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh
git config --global user.name "rahneverd"
git config --global user.email "rahneverd@gmail.com"
gh auth login

# CUSTOM RESOLUTION ON EXTERNAL DISPLAY - MANUALLY
cvt 1920 1080
xrandr --newmode "1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
xrandr --addmode DP-2 "1920x1080_60.00"
xrandr --output DP-2 --mode "1920x1080_60.00"

# CUSTOM RESOLUTION ON EXTERNAL DISPLAY - AUTOMATICALLY ON BOOT
cd /etc/X11/xorg.conf.d/
sudo nano 10-external-monitor.conf
-----------
copy paste from 10-external-monitor.conf to /etc/X11/xorg.conf.d/10-external-monitor.conf
-----------

# ZSH
dnf install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
sudo dnf install util-linux-user
chsh -s $(which zsh)

# GNOME TWEAKS
sudo dnf install gnome-tweaks 

# GNOME EXTENSIONS
https://extensions.gnome.org/extension/307/dash-to-dock/

# ANACONDA - PYTHON
curl -O https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh
bash ~/Downloads/Anaconda3-2024.02-1-Linux-x86_64.sh

# ZOOM
downlaod rpm pkg and gpg key from https://zoom.us/download?os=linux
gpg --import ~/Downloads/package-signing-key-5-12-6.pub
sudo dnf install ~/Downloads/zoom_86_64.rpm   
