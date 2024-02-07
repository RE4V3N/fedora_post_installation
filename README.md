# fedora_postinstall

### Theme
```
sudo dnf install adw-gtk3-theme papirus-icon-theme gnome-tweaks
flatpak install org.gtk.Gtk3theme.adw-gtk3 org.gtk.Gtk3theme.adw-gtk3-dark
sudo dnf copr enable peterwu/rendezvous
sudo dnf install bibata-cursor-themes
```

### Xpadneo
```
sudo dnf copr enable sentry/xpadneo
sudo dnf install xpadneo
```
### Steam flatpak
```
sudo dnf install steam-devices
```

### Nvidia
```
sudo nano /etc/environment
__GL_SYNC_DISPLAY_DEVICE=DP-2
```
### Fix boot logo
```
sudo nano /etc/modprobe.d/nvidia.conf
options nvidia_drm modeset=1
sudo nano /etc/dracut.conf.d/nvidia.conf
add_drivers+=" nvidia nvidia_modeset nvidia_uvm nvidia_drm " install_items+=" /etc/modprobe.d/nvidia.conf "
sudo dracut -f
```

### Open RGB
```
sudo dnf install openrgb-udev-rules
Exec=/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=openrgb org.openrgb.OpenRGB --startminimized --profile "fedora"
```

### Repo RPM Fusion
```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

### Alias
```
sudo nano ~/.bashrc
alias update-grub='sudo grub2-mkconfig -o /boot/grub2/grub.cfg'
```

### Flatpak
```
flatpak install com.bitwarden.desktop com.discordapp.Discord com.github.tchx84.Flatseal com.heroicgameslauncher.hgl com.mattjakeman.ExtensionManager com.spotify.Client com.valvesoftware.Steam com.visualstudio.code de.haeckerfelix.Fragments io.freetubeapp.FreeTube io.github.giantpinkrobots.flatsweep io.gitlab.news_flash.NewsFlash net.cozic.joplin_desktop net.lutris.Lutris org.onlyoffice.desktopeditors org.openrgb.OpenRGB org.raspberrypi.rpi-imager org.ryujinx.Ryujinx org.signal.Signal

flatapk update
```
### Bridges IPs Gnome boxes
```
sudo systemctl enable virtnetworkd.service
```
