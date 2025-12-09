# 📊 LohnScanner Professional - Datenpflege

## 📁 Ordnerstruktur

```
LohnScanner_Daten/
│
├── 📄 README.md              ← Diese Datei
│
├── 📂 quellen/               ← Hier pflegst du die Daten!
│   ├── berufe_allgemein.json    → Branchenübergreifende Berufe
│   ├── berufe_transport.json    → LKW, Spedition, Logistik
│   ├── berufe_bau.json          → Baubranche
│   ├── berufe_produktion.json   → Industrie & Fertigung
│   ├── berufe_buero.json        → Verwaltung, HR, Controlling
│   ├── berufe_gastro.json       → Gastronomie & Hotellerie
│   ├── berufe_handel.json       → Handel & E-Commerce
│   └── berufe_handwerk.json     → Elektro, SHK, Tischler, etc.
│
└── 📂 tools/
    └── build_kv_daten.py     → Baut die finale JSON-Datei
```

---

## 🔧 Wie pflege ich die Daten?

### 1. Lohn ändern

Öffne die passende Quell-Datei (z.B. `quellen/berufe_transport.json`):

```json
"gefahrgutfahrer_adr": {
    "bezeichnung": "Gefahrgutfahrer (ADR)/Hazmat Driver",
    "basis_lohn": 17.5,   ← DIESEN WERT ÄNDERN
    "fuer": "transport"
}
```

### 2. Neuen Beruf hinzufügen

Füge einen neuen Block hinzu:

```json
"neuer_beruf": {
    "bezeichnung": "Berufsbezeichnung DE/EN",
    "basis_lohn": 15.50,
    "fuer": "alle"
}
```

### 3. Build ausführen

```bash
cd tools
python build_kv_daten.py
```

---

## 📋 Kategorien für "fuer"

| Wert | Bedeutung |
|------|-----------|
| `alle` | Kommt in allen Branchen vor |
| `alle_mittel` | Mittlere und große Betriebe |
| `alle_gross` | Nur Großbetriebe |
| `industrie` | Produktion & Fertigung |
| `transport` | Transport & Logistik |
| `bau` | Baubranche |
| `handel` | Handel & Einzelhandel |
| `gastro` | Gastronomie & Hotellerie |
| `handwerk` | Handwerksbetriebe |

---

## 💰 Lohnfaktoren nach Branche

Die Basis-Löhne werden automatisch angepasst:

| Branchenkategorie | Faktor | Beispiel (Basis €15) |
|-------------------|--------|----------------------|
| Chemie, Energie, IT | +15% | €17,25 |
| Bau | +10% | €16,50 |
| Metall, Produktion | +8% | €16,20 |
| Standard | ±0% | €15,00 |
| Handel | -5% | €14,25 |
| Dienstleistung | -8% | €13,80 |

---

## ⚠️ Wichtige Hinweise

1. **Encoding:** Immer UTF-8 ohne BOM speichern!
2. **JSON-Syntax:** Auf Kommas achten (kein Komma nach letztem Element)
3. **Backup:** Vor größeren Änderungen Backup machen
4. **Testen:** Nach Build die App testen

---

## 📊 Aktuelle Statistik

- **87 Branchen** der österreichischen Privatwirtschaft
- **11.151 Berufsklassifikationen**
- **Stand:** Dezember 2025

---

## 📞 Support

Bei Fragen zur Datenpflege:
- 📧 schwarzlose.frank@gmx.at

---

*© 2025 Frank Schwarzlose - LohnScanner Professional*
