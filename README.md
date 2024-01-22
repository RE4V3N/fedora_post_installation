# fedora_postinstall

# Theme
```
sudo dnf install adw-gtk3-theme papirus-icon-theme
flatpak install org.gtk.Gtk3theme.adw-gtk3 org.gtk.Gtk3theme.adw-gtk3-dark
```

#Xpadneo
```
sudo dnf copr enable sentry/xpadneo
sudo dnf install xpadneo
```

#Nvidia
```
sudo nano /etc/environment
__GL_SYNC_DISPLAY_DEVICE=DP-2
```
#Fix boot logo
```
sudo nano /etc/modprobe.d/nvidia.conf
options nvidia_drm modeset=1
sudo nano /etc/dracut.conf.d/nvidia.conf
add_drivers+=" nvidia nvidia_modeset nvidia_uvm nvidia_drm " install_items+=" /etc/modprobe.d/nvidia.conf "
dracut -f
```

#Open RGB
```
sudo dnf install openrgb-udev-rules
Exec=/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=openrgb org.openrgb.OpenRGB --startminimized --profile "fedora"
```
