# Onboarding Assistant Chatbot – Voiceflow Projekt

## 🧭 Projektübersicht

Dieses Projekt ist ein **interaktiver Onboarding-Chatbot**, der neuen Mitarbeitenden den Einstieg ins Unternehmen erleichtert.  
Er wurde mit **Voiceflow** entwickelt und dient als digitaler Assistent für häufige Einstiegsfragen am ersten Arbeitstag.
## Problemstellung: Neue Mitarbeitende fühlen sich anfangs oft überfordert – Informationen zu Policies, Zuständigkeiten, Tools etc. sind verstreut.

## Lösung: Ein digitaler Assistent, der personalisiert Auskunft gibt – z. B. zu HR-Fragen, Abteilungsrichtlinien, Tagesaufgaben oder Bürostandorten.
---

## 👤 Zielgruppe (Persona)

**Neuer Mitarbeitender (Beispiel: Lionel, 28, Junior Analyst)**  
- Erster Tag im Unternehmen  
- Noch keine Kenntnis über das Unternehmen 
- Wünscht sich einfache und schnelle Orientierung (Kontakte, Orientierung, Richtlinien, allgemeine Infos etc.)

---

## 🎯 Use Cases

| Frage | Antwort |
|-------|---------|
| „Where is the HR office?“ | Standort der HR-Abteilung |
| „Is there a cafeteria nearby?“ | Ja, mit detaillierter Speisekarte |
| „Can I work from home?“ | Info zur Regelung durch Vorgesetzte |
| „Tell me a fun fact“ | Zufällig gewählte Unternehmensfakten |
"Show me my department policies" | Abfrage der passenden Knowledge Base je nach user_department (z. B. HR, Finance, IT) mit gezieltem Routing zu den richtigen Antworten
"What can I  do today?"|  Tagesplan je nach Abteilung und Tag 

## 🔄 Dialogfluss & Logik

### Begrüssung und Personalisierung
Der Bot fragt: Name + Abteilung

Variable user_name und user_department werden gesetzt

Begrüssung je nach Abteilung (z. B. "Welcome to Finance, {user_name}!")


### Automatische E-Mail-Erwähnung
- Info: „I’ve already sent you an email with all important company details...“

### Kontextlogik: Menü
- `menu_seen` wird gesetzt, wenn das Menü gezeigt wurde
- Wenn das Menü nochmals abgefragt wird → Bot fragt: „Do you want to see it again?“

### Department-basierte Inhalte (Homeoffice)

IF-Logik: Unterscheidung von Teamlead und Richtlinien (Homeoffice, Urlaub )
Basierend auf dem jeweiligen Department in der der Nutzer arbeitet werden im direkt die passenden Richtlinien zurverfügung gestellt.

### Zufallsantworten (Fun Facts)
- `fun_random` generiert Wert zwischen 1–3
- IF-Block zeigt einen von 3 Speak-Blöcken mit Unternehmensfakten
## Fortschrittslogik: „Was kann ich heute machen ?“Der Chatbot erkennt automatisch, welcher Onboarding-Tag gerade aktiv ist (Tag 1, 2 oder 3), und zeigt dem Nutzer passende Tagesaufgaben an.
Wie es funktioniert

    Eine Variable namens onboarding_day speichert den aktuellen Tag (z. B. 1)

    Beim ersten Start steht sie auf 1

    Am Ende  wird die Variable um +1 erhöht → am nächsten Tag sieht der User die Inhalte für onboarding_day = 2 usw. bis der Nutzer mit dem Programm durch ist und er auf andere Inhalte verwisen wird (aktuelle Events, Menü karte)
---

## 📦 Verwendete Variablen

| Variable     | Zweck                              |
|--------------|-------------------------------------|
| `user_name`  | Personalisierte Ansprache           |
| `menu_seen`  | Merkt, ob Menü schon angezeigt wurde|
| `fun_random` | Zufallswert für Fun Facts           |
 `user_department`  |  Steuerung von Inhalten je Abteilung
  `onboarding_day` | Tagesfortschritt im Onboardingprozess
---

## 🧱 Blocktypen in Verwendung

- ✅ **Speak Block** – für Begrüßung, Antworten, Hinweise
- ✅ **Capture (Question Step)** – Eingabe des Namens
- ✅ **Set Block** – Kontext setzen (`menu_seen`, `fun_random`)
- ✅ **If Block** – logische Verzweigungen
- ✅ **Choice Block** – Menüauswahl
- ✅ **Go To Block** – Rückführung ins Hauptmenü
- ✅ **No Match Block** – Fallback für unklare Eingaben
- ✅ **KB Search Block** : Abfrage von Policies

---

## 🧪 Projekt testen

- Öffne den Emulator in Voiceflow
- Testeingabe: „What’s your name?“ → z. B. „Alex“
- Testeingabe: „In which department will you start working?“ --> z.B „Finance"
- Individuelle Begrüssung mit den wichtigsten Infos des jeweiligen Departments
- Folgefragen aus dem Menü ausprobieren
- Fun Fact mehrfach testen für Randomisierung
- Search company knownledge um Fragen zu den Hinterlegten Unternehmensrichtlinien zu stellen
- Bei einem „No match“ wird ein KI-Bot der die wichtigsten Infos erhalten hat. Bei Unsicherheiten wird der Nutzer zurück zum Hauptmenü geleitet.

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



