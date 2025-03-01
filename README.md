# OS

## Boot Loader

```sh
sudo grub2-editenv - set menu_auto_hide=1
```

## Kernel Parameters

### AMDGPU

```sh
rpm-ostree --append-if-missing=amdgpu.abmlevel=0
rpm-ostree --append-if-missing=amdgpu.dcdebugmask=0x10
```

## Flatpak

### Locales

```sh
flatpak config --set extra-languages ja_JP.UTF-8
flatpak update
```

### Fonts

```sh
mkdir -p ~/.config/fontconfig/conf.d
cp /usr/share/fontconfig/conf.avail/99-os.conf ~/.config/fontconfig/conf.d/99-os.conf
```

### Additional Runtimes

```sh
flatpak install org.freedesktop.Platform.VulkanLayer.MangoHud//24.08
flatpak install org.freedesktop.Platform.VulkanLayer.OBSVkCapture//24.08
flatpak install org.freedesktop.Platform.VulkanLayer.gamescope//24.08
flatpak install org.freedesktop.Platform.VulkanLayer.vkBasalt//24.08
```
