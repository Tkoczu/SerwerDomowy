# 🏠 Home Assistant

## 📦 Rola w systemie

Centralny system sterowania smart home.

Odpowiada za:
- automatyzacje
- integrację urządzeń
- sterowanie głosowe (pośrednio)

---

## 🏗️ Architektura

Home Assistant działa jako VM na Proxmox.

### Flow:

Home Assistant  
→ Matter Bridge  → SmartThings  → Google Home  → użytkownik (głos / aplikacja)

---

## 🔌 Integracje

| Integracja | Rola |
|----------|------|
| Matter Bridge | eksport urządzeń z HA |
| SmartThings | pośrednik (np. TV Samsung) |
| Google Home | sterowanie głosowe |

---

## 🎙️ Sterowanie głosowe

Sterowanie NIE idzie bezpośrednio do HA.

---

## ⚙️ Automatyzacje

Przykłady:
- światła włączają się przy TV
- odkurzacz sterowany głosowo

---

## ⚠️ Problemy

### 1. Światło włącza się nie wtedy co trzeba

Objaw:
- włącza się mimo że jest jasno

Rozwiązanie:
- dodać warunek:
  - poziom jasności
  - pora dnia

---

### 2. Automatyzacje uruchamiają się za często

Rozwiązanie:
- dodać:
  - `condition`
  - opóźnienie (delay)
  - sprawdzanie stanu

---

### 3. Opóźnienia (delay za długi)

Objaw:
- wygląda jakby system się zawiesił

Rozwiązanie:
- zmniejszyć delay (np. 5s → 1s)

---

## 💾 Dane

- konfiguracja: VM (Home Assistant OS)
- automatyzacje: YAML / GUI

---

## 🔐 Dostęp

- lokalny (LAN)
- zdalny przez Google Home

---

## 🧠 Decyzje projektowe

### Google Home jako główny interfejs

Powód:
- wygoda
- sterowanie głosowe

---

### SmartThings jako pośrednik

Powód:
- kompatybilność z TV Samsung
- integracja z ekosystemem Google (Do sterowania głosem)
