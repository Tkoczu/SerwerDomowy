# 🏠 NAS Homelab (Proxmox + OMV + HA + Paperless)

Prywatny serwer NAS + smart home + dokumenty.

## 🎯 Cel projektu

- pełna kontrola nad danymi
- self-hosting kluczowych usług
- minimalna zależność od chmury
- łatwe odtworzenie środowiska po awarii

---

## 🧱 Architektura

- Hypervisor: Proxmox VE
- VM:
  - OpenMediaVault
  - Home Assistant
  - Paperless-ngx

---

## ⚙️ Hardware
Lenovo M93P Tiny
| Komponent | Wartość |
|----------|--------|
| CPU | i5-4570T |
| RAM | 16 GB |
| Storage | 240GBSSD(System) + 2x1TB(Storage) |

---

## 🧩 Usługi

| Usługa | Opis |
|-------|-----|
| OMV | zarządzanie dyskami i udziałami |
| Home Assistant | automatyzacje i smart home |
| Paperless-ngx | zarządzanie dokumentami |
| KeePass | manager haseł (plik lokalny + backup) |

---

## 🗂️ Dane

- NAS: `/mnt/...`
- aplikacje: `/opt/...`

---

## 🔄 Backup

- KeePass → Google Drive (rsync)
- VM → Proxmox backup (manualny)
- Dokumenty → Paperless (dokumenty pobierane z maila[Głównie Faktury])

---

## 🌍 Dostęp

- lokalny + VPN
- zdalny przez integracje (Google Home / SmartThings)
- W przypadku karty sieciowej intel e1000 może wystąpić problem z zawieszeniem karty naprawia to skrypt https://community-scripts.org/scripts/nic-offloading-fix?id=nic-offloading-fix

---

## ⚠️ Status

Projekt w trakcie rozwoju.

---
