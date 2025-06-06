# OS

## Kernel Parameters

### AMDGPU

```sh
rpm-ostree --append-if-missing=amdgpu.abmlevel=0
rpm-ostree --append-if-missing=amdgpu.dcdebugmask=0x10
```

## Flatpak

### Locales

> https://github.com/bottlesdevs/Bottles/issues/2189#issuecomment-1354412658

```sh
flatpak config --set extra-languages 'zh_CN.UTF-8;ja_JP.UTF-8'
flatpak update
```

### Fonts

> https://github.com/flatpak/flatpak/issues/1563

```sh
mkdir -p ~/.config/fontconfig/conf.d
cp /usr/share/fontconfig/conf.avail/99-os.conf ~/.config/fontconfig/conf.d/99-os.conf
sudo flatpak override --system --filesystem=xdg-config/fontconfig:ro
```

### Additional Runtimes

> https://github.com/blue-build/modules/pull/142#issuecomment-1962458757

```sh
flatpak install org.freedesktop.Platform.VulkanLayer.MangoHud
flatpak install org.freedesktop.Platform.VulkanLayer.OBSVkCapture
flatpak install org.freedesktop.Platform.VulkanLayer.gamescope
flatpak install org.freedesktop.Platform.VulkanLayer.vkBasalt
```
