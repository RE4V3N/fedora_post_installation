# fedora_postinstall

# Theme
sudo dnf install adw-gtk3-theme papirus-icon-theme
flatpak install org.gtk.Gtk3theme.adw-gtk3 org.gtk.Gtk3theme.adw-gtk3-dark

#Xpadneo
sudo dnf copr enable sentry/xpadneo
sudo dnf install xpadneo

#Grub
sudo nano /etc/default/grub
nvidia-drm.modeset=1 to GRUB_CMDLINE_LINUX line
GRUB_GFXMODE=2560x1440
sudo grub2-mkconfig -o /boot/grub2/grub.cfg

#Nvidia
sudo nano /etc/environment
__GL_SYNC_DISPLAY_DEVICE=DP-2

sudo dnf clean packages

#Open RGB
sudo dnf install openrgb-udev-rules
Exec=/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=openrgb org.openrgb.OpenRGB --startminimized --profile "fedora"
