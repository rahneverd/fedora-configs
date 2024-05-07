# fedora-configs

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
Section "Monitor"
### Monitor Identity - Typically HDMI-0 or DisplayPort-0
    Identifier    "DP-2"

### Setting Resolution and Modes
### Modeline is usually not required, but you can force resolution with it    
Modeline ""1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
    Option "PreferredMode" "1920x1080_60.00"
    Option        "TargetRefresh" "60"

### Positioning the Monitor
### Basic
    Option "RightOf" "eDP-1"
### Advanced
    Option        "Position" "1366 0"

### Disable a Monitor
###     Option        "Disable" "true"
EndSection 
-----------