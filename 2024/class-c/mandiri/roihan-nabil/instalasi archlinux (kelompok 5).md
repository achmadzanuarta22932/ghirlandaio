# Instalasi Arch Linux 
---

## 1. Masuk ke live environtment archlinux

#### BIOS HP
Pencet esc sampai masuk BIOS, terus F9 untuk ke BOOT MENU.. pilih yg flashdisk

---
<img width="4064" height="3048" alt="1  masuk ke arch live environment dgn pencet esc berkali kali" src="https://github.com/user-attachments/assets/686b3947-07bd-4862-9876-1f4119cfa21a" />

---

## 2. Jaringan

```iwctl``` dulu, terus ketik perintah ```station wlan0 connect "nama wifi"``` buat nyambungin. Kalau sudah, tinggal masukin password-nya aja. Ketik ```exit``` kalau sudah dan cek internet dgn ```ping 8.8.8.8```

---
<img width="4064" height="3048" alt="2  Iwctl trus masuk ke wifi dgn command station wlan0 connect (nama wifi), stelah itu masukkan password" src="https://github.com/user-attachments/assets/a75a1015-4527-4ce5-9d10-3822da8be103" />
---

## 3. Cek Internet dan Sinkronisasi Waktu

Ketik ```exit``` kalau sudah dan cek internet dgn ```ping 8.8.8.8``` dan memasukkan timedatectl

---
<img width="3631" height="1162" alt="3  tes internet dengan command ping 8 8 8 8 dan memasukkan timedatectl(sinkronisasi waktu)" src="https://github.com/user-attachments/assets/c27b3726-4be9-4fcf-8de1-54776c06a201" />
---

## 4 Partisi (format root, membuat swap dan juga aktivasi swap)

```lsblk``` untuk melihat partisi, ketik ```cfdisk _dev_nvme0n1``` untuk format partisi

---
<img width="4064" height="3048" alt="4  lsblk untuk melihat partisi, ketik cfdisk _dev_nvme0n1 untuk format partisi" src="https://github.com/user-attachments/assets/a689eb6a-55c8-483b-9851-ce9d8e6f9b9a" />
---

Input partisi nvme0n1p5 512M(EFI BOOT), p6 4G(Swap), p7 45G(Root). setelah itu format partisi root ```mkfs.ext4 /dev/nvme0n1p7```, membuat swap ```mkswap /dev/nvme0n1p6```dan aktivasi ```swapon /dev/nvme0n1p6```

---
<img width="4064" height="3048" alt="5  input partisi 0n1p5 512M(EFI BOOT), p6 4G(Swap), p7 45G(Root)  setelah itu format partisi root _mkfs_, membuat swap dan aktivasi swap" src="https://github.com/user-attachments/assets/6bb1aa73-b8fb-410d-afa4-4bdf07bd224e" />
---

## 5 Format EFI(Boot)

```mkfs.fat -F 32 /dev/efi_system_partition``` 

Untuk Mount partisi Root, ketik:

```mount /dev/root_partition /mnt```

Untuk Mount partisi EFI, ketik:

```mount --mkdir /dev/efi_system_partition /mnt/boot```

---
<img width="4064" height="3048" alt="6  format EFI stelah itu mount root dan EFI" src="https://github.com/user-attachments/assets/8b577bcc-6f37-4099-8bc8-50bf3e612ac2" />
---

## 6 

































