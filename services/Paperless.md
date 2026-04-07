# 📄 Paperless-ngx

## 📦 Rola w systemie

System do zarządzania dokumentami.

Odpowiada za:
- przechowywanie dokumentów
- OCR (rozpoznawanie tekstu)
- tagowanie i archiwizację
- import z maila

---

## 🏗️ Architektura

Paperless działa jako VM na Proxmox.

### Flow danych:

Dokument (plik / mail)  
→ Paperless  
→ zapis na storage (OMV)  
→ dostęp przez web UI  

---

## 🔌 Integracje

| Integracja | Rola |
|----------|------|
| OMV | storage dokumentów |
| Email (IMAP) | automatyczny import |
| Proxmox | host VM |

---

## ⚙️ Konfiguracja

### Storage

Dane przechowywane w:

/opt/paperless_data

Mount z OMV:
/mnt/paperless

---

### Struktura katalogów

/opt/paperless_data/
├── archive/
├── consume/
├── media/

---

## 📥 Import dokumentów

### 1. Ręczny
- wrzucenie pliku przez UI

### 2. Mail (IMAP)

Paperless sprawdza skrzynkę i importuje dokumenty.

---

## 💾 Dane

- dokumenty → storage (OMV)
- metadane → baza danych (w VM)

---

## 🔄 Backup

Obecnie:
- brak dedykowanego backupu Paperless

Zależność:
- backup całej VM (Proxmox)

---

## ⚠️ Problemy (REALNE)

### 1. Mail import nie działa

Objaw:
- klikam "przetwarzaj" → nic się nie dzieje

Co się stało:
- mail przestał być pobierany

Rozwiązanie:
- restart Paperless
- sprawdzenie konfiguracji maila

Status:
✔️ naprawione

---

### 2. Brak katalogu archive

Objaw:
- błędy przy przetwarzaniu dokumentów

Rozwiązanie:

```bash
mkdir /opt/paperless_data/archive
