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

# CUSTOM RESOLUTION ON EXTERNAL DISPLAY
cvt 1920 1080
xrandr --newmode "1920x1080_60.00"  173.00  1920 2048 2248 2576  1080 1083 1088 1120 -hsync +vsync
xrandr --addmode DP-2 "1920x1080_60.00"
xrandr --output DP-2 --mode "1920x1080_60.00"
