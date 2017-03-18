# Installation von Paketen

```bash
#Installation:
pacman -S paketname

# Deinstallation:
pacman -Rns paketname

#Update
pacman -Syu
```

# Installation einer Desktopumgebung

## Gnome3

```bash
# Installation
pacman -S gnome

# Autostart
systemctl enable gdm.service
```

# Konfiguration & Zusatztools

```bash
# Support für zusätzliche Dateisysteme & Automount für Wechseldatenträger
pacman -S udisks2 gvfs gvfs-smb gvfs-mtp gvfs-afc gvfs-nfs gvfs-gphoto2

# Anpassung der Swappiness
# Legt fest, ab wann vom RAM auf die SSD ausgelagert wird.

vi /etc/sysctl.d/99-sysctl.conf
  vm.swappiness=1

# Paket-kompilierung durch multithreading beschleunigen
vi /etc/makepkg.conf
  MAKEFLAGS="-j4"

# Wget, git, subversion
pacman -S wget git svn

# Bluetooth
pacman -S blueman bluez-utils gnome-bluetooth bluez-hcidump pulseaudio-bluetooth

# Intel Powersave
vi /etc/modprobe.d/60-snd_hda_intel.conf
  # Experimental options to improve power saving on Intel Graphics
  options i915 enable_rc6=1 enable_fbc=1 lvds_downclock=1

# ToDo: TLP & Powertop

# Thermald
# Schutz vor Überhitzen
wget https://aur.archlinux.org/cgit/aur.git/snapshot/thermald.tar.gz
tar xzvf
cd [...]
makepkg -rsi
sudo systemctl enable thermald
sudo systemctl start thermald

```
