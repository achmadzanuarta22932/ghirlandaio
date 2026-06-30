Format luks
```
Cryptsetup luksFormat/dev/partisi
```
## Format Partisi
```
mkfs.ext4 /dev/[nama grup]/partisi
```
##  Format Partisi vfat
```
mkfs.vfat -F32 /dev/[nama partisi boot]
```
## Mounting
```
mount /dev/[nama grup]/root /mnt
```
```
mount --mkdir -o rw,uid=0,gid=0,fmask=0077,dmask=0077,relatime /dev/[nama partisi boot] /mnt/boot
```
```
mount --mkdir -o rw,nodev,nosuid,relatime /dev/[nama grup]/vars /mnt/var
```
```
```
## luksFormat
```
cryptsetup luksFormat /dev/[nama grup]/[nama home internal]
```
> LuksFormat digunakan untuk memformat nama grup yang menjadi partisi, dan yang menjadi partisi kita menjadi home internal

## Install Package
```
pacstrap /mnt intel-ucode base linux-hardened linux-hardened-headers linux-firmware mkinitcpio lvm2 sudo pacman git wget curl neovim iwd firewalld openssh grep podman podman-compose asciinema
```
