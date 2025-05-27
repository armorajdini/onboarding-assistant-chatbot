# Onboarding Assistant Chatbot – Voiceflow Projekt

## 🧭 Projektübersicht

Dieses Projekt ist ein **interaktiver Onboarding-Chatbot**, der neuen Mitarbeitenden den Einstieg ins Unternehmen erleichtert.  
Er wurde mit **Voiceflow** entwickelt und dient als digitaler Assistent für häufige Einstiegsfragen am ersten Arbeitstag.

---

## 👤 Zielgruppe (Persona)

**Neuer Mitarbeitender (Beispiel: Lionel, 28, Junior Analyst)**  
- Erster Tag im Unternehmen  
- Noch keine Kenntnis über HR, Kantine, Homeoffice-Regeln  
- Wünscht sich einfache und schnelle Orientierung

---

## 🎯 Use Cases

| Frage | Antwort |
|-------|---------|
| „Where is the HR office?“ | Standort der HR-Abteilung |
| „Is there a cafeteria nearby?“ | Ja, mit detaillierter Speisekarte |
| „Can I work from home?“ | Info zur Regelung durch Vorgesetzte |
| „Tell me a fun fact“ | Zufällig gewählte Unternehmensfakten |

---

## 🔄 Dialogfluss & Logik

### Begrüßung und Personalisierung
- Der Bot fragt nach dem Namen (`user_name`)
- Begrüßung mit „Welcome, {user_name}!“

### Automatische E-Mail-Erwähnung
- Info: „I’ve already sent you an email with all important company details...“

### Hauptmenü (Choice Block)
- Auswahlmöglichkeiten für Nutzerfragen

### Kontextlogik: Menü
- `menu_seen` wird gesetzt, wenn das Menü gezeigt wurde
- Wenn das Menü nochmals abgefragt wird → Bot fragt: „Do you want to see it again?“

### Zufallsantworten (Fun Facts)
- `fun_random` generiert Wert zwischen 1–3
- IF-Block zeigt einen von 3 Speak-Blöcken mit Unternehmensfakten

---

## 📦 Verwendete Variablen

| Variable     | Zweck                              |
|--------------|-------------------------------------|
| `user_name`  | Personalisierte Ansprache           |
| `menu_seen`  | Merkt, ob Menü schon angezeigt wurde|
| `fun_random` | Zufallswert für Fun Facts           |

---

## 🧱 Blocktypen in Verwendung

- ✅ **Speak Block** – für Begrüßung, Antworten, Hinweise
- ✅ **Capture (Question Step)** – Eingabe des Namens
- ✅ **Set Block** – Kontext setzen (`menu_seen`, `fun_random`)
- ✅ **If Block** – logische Verzweigungen
- ✅ **Choice Block** – Menüauswahl
- ✅ **Go To Block** – Rückführung ins Hauptmenü
- ✅ **No Match Block** – Fallback für unklare Eingaben

---

## 🧪 Projekt testen

- Öffne den Emulator in Voiceflow
- Testeingabe: „What’s your name?“ → z. B. „Alex“
- Folgefragen aus dem Menü ausprobieren
- Fun Fact mehrfach testen für Randomisierung

- 🔗 Test it live: [Voiceflow Preview](https://creator.voiceflow.com/project/6819bf8ca462610c22041dcd/canvas/64dbb6696a8fab0013dba194))

---

## 🔗 Projektartefakte

| Datei / Link | Beschreibung |
|--------------|--------------|
| `voiceflow-export.vf` | Vollständiges Voiceflow-Projekt (als .vf-Datei) |
| `flow-screenshot.pdf` | Visualisierte Struktur als Screenshot |
| (optional) GitHub-Link | für Abgabe eintragen |
| (optional) Share-Link | Voiceflow Preview-Link |

---

## 📋 Team

- Armor Ajdini  
- Kavisan Nagarajah
- Pablo de la Cruz

---

## 📌 Hinweise für Präsentation

- Einstieg über Persona „Lionel“ (Storytelling)  
- Demo: Name → Begrüßung → Menü → Fun Fact  
- Highlight: Kontextlogik, Rückführung, zufällige Antworten

---

## ✅ Erfüllt Bewertungskriterien

- UX & Szenario: klar definiert  
- Prototype: vollständig mit Happy & Alternative Paths  
- Architektur: logisch, Variablen & Datenstruktur  
- Build: stabil & reaktiv  
- Artefakte: dokumentiert, exportierbar  
- Präsentation: vorbereitet (siehe Pitch)

---
