# OpenMediaVault (OMV)

## 📦 Rola w systemie

OMV pełni rolę warstwy storage dla całego homelaba.

Odpowiada za:
- zarządzanie dyskami
- udziały sieciowe (SMB/NFS)
- przechowywanie danych aplikacji
- centralny punkt danych (NAS)

---

## 🏗️ Architektura

Proxmox (host)
└── VM: OMV
    ├── SMB/NFS shares
    ├── storage dla Paperless
    └── inne dane (np. backup zdjęć)

---


## 🔗 Udziały sieciowe

### SMB

Używane do:
- dostępu z Windows / Mac
- ręcznego wrzucania plików

### NFS (opcjonalnie)

Używane do:
- mountów w VM (np. Paperless)

---

## 📂 Kluczowe dane

| Usługa | Lokalizacja |
|--------|------------|
| Paperless | /mnt/paperless |

---

## 🔌 Integracje

OMV współpracuje z:

- Paperless (mount danych)

---

## ⚙️ Konfiguracja

### Dyski

- skonfigurowane w OMV GUI
- zamontowane w /mnt/

### Uprawnienia

⚠️ ważne:

- problemy często wynikają z permisji
- w testach używane:
  chmod 777

Docelowo:
- dedykowani użytkownicy + grupy

---

## 📡 Dostęp

- lokalny przez SMB
- brak wystawienia do internetu (zalecane)

---

## 🔄 Backup

OMV sam w sobie NIE robi backupu – tylko przechowuje dane.

Backup realizowany przez:
- Proxmox (VM backup)

---

## ⚠️ Problemy i pułapki

### 1. Mounty znikają

Objaw:
- Paperless traci dostęp do danych

Przyczyna:
- mount nie ustawia się automatycznie

Rozwiązanie:
- sprawdzić /etc/fstab
- ustawić automatyczny mount

---

### 2. Permission denied

Objaw:
- aplikacja nie widzi plików

Rozwiązanie:
- chmod / chown
- sprawdzenie usera kontenera/VM

---

### 3. Brak katalogów (np. archive)

Rozwiązanie:
- ręczne utworzenie katalogu

---

## 🧠 Decyzje projektowe

### OMV zamiast czystego Linuxa

Powód:
- prosty GUI
- łatwe zarządzanie dyskami
- mniej ręcznej konfiguracji

---

### SMB jako główny dostęp

Powód:
- wygoda
- kompatybilność z Windows
