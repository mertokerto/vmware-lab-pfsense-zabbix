# pfSense Temel Kurulum ve İlk Yapılandırma

Bu belge, VMware Workstation üzerinde pfSense firewall sisteminin temel kurulumunu ve ilk yapılandırmasını açıklamaktadır. Hedef, LAN ve WAN arayüzlerini yapılandırmak ve WebGUI erişimini sağlamaktır.

---

## 1️ Sanal Makine Oluşturma

### VMware Ayarları:
- **ISO Dosyası**: `pfSense-CE-2.7.2-RELEASE-amd64.iso` (resmi siteden indirildi)
- **VM Tipi**: FreeBSD 64-bit
- **RAM**: 2 GB
- **Disk**: 10 GB
- **İşlemci**: 1 veya 2 core

### Ağ Kartları:
- **Adapter 1 (LAN)**: Host-Only (VMnet1)
- **Adapter 2 (WAN)**: NAT

---

## 2️ pfSense Kurulumu

1. VM başlatıldı, pfSense ISO ile boot edildi
2. `Install pfSense` seçeneğiyle kurulum başlatıldı
3. Disk bölümleme varsayılan olarak bırakıldı (Auto ZFS)
4. Root şifresi belirlendi (örnek: `admin123`)
5. Kurulum tamamlandıktan sonra sistem yeniden başlatıldı
6. ISO bağlantısı kesildi, diskten boot edildi

---

## 3️ Arayüz Atamaları (Console)

- WAN: `em0` (NAT’a bağlı)
- LAN: `em1` (VMnet1’e bağlı)
- DHCP atamaları otomatik yapılandırıldı

---

## 4️ LAN IP Ayarı

- pfSense LAN IP’si olarak `192.168.111.1` atanmıştır
- Subnet: `/24` (255.255.255.0)
- DHCP sunucusu etkinleştirildi (dilersen elle IP verilebilir)

---

## 5️ Ana Bilgisayar IP Ayarı

- Ana bilgisayara statik IP verildi: `192.168.111.2`
- Subnet Mask: `255.255.255.0`
- Varsayılan ağ geçidi: boş bırakıldı (sadece LAN bağlantısı)

---

## 6️ WebGUI Erişimi

- Tarayıcıdan şu adresle erişildi: `http://192.168.111.1`
- İlk giriş bilgileri:
  - **Username**: `admin`
  - **Password**: `pfsense`
- İlk yapılandırma sihirbazı (Setup Wizard) çalıştırıldı
  - Saat dilimi: Europe/Istanbul
  - DNS Sunucuları: 1.1.1.1, 8.8.8.8
  - WAN: DHCP ile IP aldı
  - WebGUI şimdilik HTTP üzerinden çalışıyor

---

##  Kurulum Sonrası Durum

- Ana bilgisayar ile pfSense LAN arayüzü arasında bağlantı sağlandı
- pfSense NAT üzerinden internete çıkabiliyor
- Temel firewall kuralları henüz yazılmadı