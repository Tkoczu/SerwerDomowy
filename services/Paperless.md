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

Paperless sprawdza skrzynkę i importuje dokumenty. (Dodany warunek aby odbierać wiadomości tylko z mojego maila)

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
