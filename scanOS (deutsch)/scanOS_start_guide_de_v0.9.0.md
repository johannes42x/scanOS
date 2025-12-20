# Willkommen bei scanOS 👋

Schön, dass du scanOS in dein Setup einbindest!

scanOS ist dein zentrales **Einlese- und Erfassungsmodul**. 
Immer dann, wenn irgendwo schon Daten existieren – aber noch nicht in einem strukturierten, weiterverwendbaren Format – springt scanOS ein.

Kurz gesagt:

- Du hast **Screenshots oder Fotos** (z. B. von Fitness-Apps, Schlaftrackern, Dashboards)? → ab damit in scanOS. 
- Du hast **Exporte aus Apps oder Plattformen** (CSV, JSON, PDF, …)? → ab damit in scanOS. 
- Du möchtest Daten **regelmäßig in derselben Struktur** erfassen (z. B. Trainings, Schlaf, Schritte)? → scanOS hilft dir, ein wiederverwendbares Template zu erstellen.

Das Ziel: 
Alle wiederkehrenden Informationen landen als **einheitlich normalisiertes JSON** vor dir. Andere Module können diese Daten dann direkt übernehmen und weiterverarbeiten.

---

## Wie scanOS arbeitet

scanOS kennt zwei Betriebsmodi:

### 1️⃣ Ad-hoc-Erfassung  
Für einzelne Screenshots oder Exporte. 
Du postest einfach die Datei – scanOS liest sie aus und gibt dir Text oder Datei aus - sag einfach, was du gerne hättest.

### 2️⃣ Template-Modus  
Für Datenquellen, die du **immer wieder** nutzt (z. B. dieselbe Fitness-App). 
scanOS baut dir ein **Template**, das beschreibt:

- welche Felder typischerweise vorkommen 
- wie sie heißen 
- wie fehlende Werte behandelt werden 
- welche Struktur zukünftige Einträge haben sollen

Dieses Template wird in einer gemeinsamen `templates.json` abgelegt. 
Ab dann weiß scanOS bei jedem neuen Screenshot: 
*„Ah, das ist Quelle X – ich lege es in Struktur Y ab.“*

## 🖼️ Automatische Bildbeschreibung (Text & Struktur)

scanOS kann mehr als Text lesen.

Wenn du ein **Foto hochlädst, das nicht überwiegend aus Text besteht**, erkennt scanOS das automatisch und erzeugt eine **Bildbeschreibung**.

Diese besteht aus **zwei Teilen**:

- einer **menschenlesbaren Beschreibung** (für schnelles Verstehen)
- einer **maschinenlesbaren Struktur** (für Weiterverarbeitung, Archivierung oder Analyse)

### Was scanOS dabei macht

- erkennt, **dass es sich um ein Bild** handelt (nicht primär Text)
- beschreibt **sichtbare Inhalte, Objekte, Anordnung und Kontext**
- trennt klar zwischen:
  - *Was ist zu sehen?*
  - *Wie ist es strukturiert?*
- gibt das Ergebnis **strukturiert** aus (JSON-kompatibel)

Das ist besonders nützlich für:

- Fotos von Räumen, Objekten oder Situationen  
- Screenshots von Apps, UIs oder Dashboards  
- Dokumentations- und Erinnerungszwecke  
- spätere Referenz oder automatisierte Auswertung  

### Manuell auslösen (falls nötig)

Falls scanOS einmal **keine Bildbeschreibung erzeugt**, kannst du sie jederzeit explizit anfordern, z. B. mit:

```
Bitte erstelle eine Bildbeschreibung.
```

---

## Was ein Template enthält

Ein Template ist ein JSON-Rahmen für eine typische Datensatzstruktur. Es definiert:

- **Feldnamen** 
- **Datentypen / erwartete Inhalte** 
- **optionale Felder** (können `null` sein) 
- **Verarbeitungshinweise** für scanOS

Ganz oben steht immer das feste Platzhalterfeld:

```json
"id": "ID-###"
```

In scanOS bleibt es bewusst ein Platzhalter. Die echte ID wird später vom Modul vergeben, das den Eintrag übernimmt (z. B. `trainingOS`).

---

## Ein neues Template erstellen

Wenn du für eine bestimmte Datenquelle (z. B. deine Fitness-App) ein Template bauen möchtest, läuft das so:

1. **Screenshots sammeln** 
   Poste einen oder mehrere Screenshots, die zusammen alle relevanten Daten enthalten.

2. **Screenshots im scanOS-Kontext posten** 
   Lade alles in einem Schritt hoch.

3. **Template-Prompt (unten) schicken** 
   Damit sagst du scanOS: 
   *„Bitte kein einzelnes Training extrahieren, sondern eine Vorlage bauen.“*

4. **scanOS analysiert die Rohdaten** 
   Es prüft, was zuverlässig lesbar ist und welche Struktur stabil funktioniert.

5. **Template wird erzeugt** 
   scanOS baut ein JSON-Template, setzt oben den `ID-###` Platzhalter und ordnet alle Felder sinnvoll an.

6. **templates.json wird aktualisiert** 
   scanOS fügt das neue Template in die bestehende `templates.json` ein und gibt dir die Datei zum Download.

---

## Kopierbarer Prompt für die Template-Erstellung

```text
Hi scanOS, ich möchte aus diesen Screenshots ein Template für wiederkehrende Datenerfassung erstellen.

Bitte:
1. Schau dir alle hochgeladenen Screenshots an und erfasse, welche Rohdaten daraus zuverlässig gelesen werden können.
2. Überlege dir eine stabile JSON-Struktur, in die zukünftige Datensätze aus dieser Quelle immer einsortiert werden können.
3. Ganz oben im Template-Block soll ein Platzhalter stehen:
   "id": "ID-###"
   Die echte ID wird später von einem anderen Modul (z. B. trainingOS) vergeben.
4. Erzeuge ein JSON-Template für genau diese Datenquelle.
5. Füge dieses Template als neuen Block in die bestehende templates.json ein und gib mir die aktualisierte Datei zum Download.
6. Zeig mir das Template zusätzlich separat zur schnellen Prüfung.
```

---

## 🎉 4. Viel Spaß mit scanOS

Mit scanOS hast du jetzt ein **universelles Einlese-Werkzeug**, das dir im Alltag jede Menge Arbeit abnimmt:

- Du brauchst Text aus einem Buch, Brief oder Dokument digital? 
  → *Foto machen, hochladen, „bitte OCR“ sagen — erledigt.*

- Du willst Daten aus Apps oder Plattformen vorformatiert übernehmen? 
  → *Export reinwerfen, scanOS normalisiert alles.*

- Du möchtest wiederkehrende Daten sauber strukturiert ablegen — Training, Schlaf, Schritte, Ernährung, was immer du willst? 
  → *Einmal ein Template bauen, danach läuft’s automatisch.*

- Du willst sogar komplette Einträge für deine Literaturverwaltungssoftware erzeugen? 
  → *Zotero-Templates kannst du selbst erstellen — oder als günstiges Preset dazukaufen.*

Es ist nicht schwer, und scanOS ist geduldig — und ehrlich gesagt auch ein bisschen stolz, wenn du’s schick einsetzt.

---

## 💚 DANKE

Danke, dass du scanOS nutzt. 
Hab Spaß beim Einlesen, Extrahieren, Sortieren — und beim leisen Triumphgefühl, wenn Daten plötzlich nicht mehr chaotisch, sondern richtig schön strukturiert sind.

**MetaMemoryWorks – do EVERYTHING.**

---

*Preliminary findings indicate that feeding scanOS a blurry photo while listening to King Gizzard & the Lizard Wizard increases OCR accuracy by up to 0.7%. 
Causality unknown. Studies pending.*
