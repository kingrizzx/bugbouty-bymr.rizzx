o# bugbouty-bymr.rizzx
Fitur lumayan
ASSALAMUALAIKUM / SALOM / SALAM SEJATERA SAYA MR.RIZZX


  Berikut isi file tools KINGRIZZX-BUGBOUNTY versi full langsung bisa dipakai.


---

📁 Struktur file:

KINGRIZZX-BUGBOUNTY/
├── KINGRIZZX-BUGBOUNTY.sh
└── README.md


---

📜 KINGRIZZX-BUGBOUNTY.sh

#!/bin/bash
echo "=============================="
echo "     🔥 DEV KING RIZZX 🔥"
echo "    Bug Bounty Auto Recon"
echo "=============================="
echo ""
read -p "Masukkan domain target (contoh: example.com): " domain
mkdir -p hasil/$domain
cd hasil/$domain

echo "[+] Subfinder dijalankan..."
subfinder -d $domain -silent > subdomain.txt
echo "[+] $(wc -l < subdomain.txt) subdomain ditemukan"

echo "[+] HTTPX cek domain aktif..."
httpx -l subdomain.txt -silent > live.txt
echo "[+] $(wc -l < live.txt) domain aktif"

echo "[+] Waybackurls dijalankan..."
cat live.txt | waybackurls > wayback.txt
echo "[+] $(wc -l < wayback.txt) URL arsip ditemukan"

echo "[+] Scan nuclei dijalankan..."
nuclei -l live.txt -o nuclei_result.txt
echo "[+] Hasil nuclei tersimpan di nuclei_result.txt"

echo ""
echo "✅ Selesai! Semua hasil disimpan di folder hasil/$domain"
echo "🔥 Tools by DEV KING RIZZX 🔥"


---

📘 README.md

# KINGRIZZX-BUGBOUNTY

Tools bug bounty otomatis by DEV KING RIZZX

## Install:
```bash
pkg update && pkg install git python golang curl zip
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest
go install github.com/tomnomnom/waybackurls@latest
export PATH=$PATH:$HOME/go/bin
nuclei -update-templates

Jalankan:

git clone https://github.com/kingrizzx/bugbouty-bymr.rizzx
cd KINGRIZZX-BUGBOUNTY
chmod +x KINGRIZZX-BUGBOUNTY.sh
./KINGRIZZX-BUGBOUNTY.sh

Fungsi:

Subdomain enum (subfinder)

Live check (httpx)

Wayback URLs (waybackurls)

Vuln scan (nuclei)


---


ATAU

git clone https://github.com/kingrizzx/bugbouty-olehmr.rizzx.git

cd bugbouty-olehmr.rizzx

chmod +x KINGRIZZX-BUGBOUNTY.sh

./KINGRIZZX-BUGBOUNTY.sh

pkg install git golang python curl


