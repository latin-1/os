# OS

```sh
sudo bluebuild generate-iso --iso-name OS.iso --variant silverblue --secure-boot-url '' --enrollment-password '' image ghcr.io/latin-1/os
```

## Kernel

### AMDGPU

```sh
rpm-ostree kargs --append-if-missing=amdgpu.abmlevel=0
```

## System

### Date & Time

```sh
timedatectl set-ntp true
```

### Display

> https://gitlab.gnome.org/GNOME/gnome-control-center/-/work_items/3742

```sh
gdctl set --persistent --logical-monitor --monitor eDP-1 --primary --color-mode sdr-native
```

## Flatpak

### Locales

> https://github.com/bottlesdevs/Bottles/issues/2189#issuecomment-1354412658

```sh
flatpak config --set extra-languages 'zh_CN.UTF-8;zh_HK.UTF-8;zh_TW.UTF-8;ja_JP.UTF-8'
flatpak update
```

### Fonts

> https://github.com/flatpak/flatpak/issues/1563

```sh
mkdir -p ~/.config/fontconfig/conf.d
cp /usr/share/fontconfig/conf.avail/99-os.conf ~/.config/fontconfig/conf.d/99-os.conf
sudo flatpak override --system --filesystem=xdg-config/fontconfig:ro
```
