# Multi-Agent Development Workflow

Dieses Repository enthält eine Sammlung spezialisierter System-Prompts, um den gesamten Software-Entwicklungs-Lifecycle mit KI-Unterstützung abzubilden.

## Rollenübersicht

| Datei | Rolle | Fokus |
| :--- | :--- | :--- |
| `kundeX.systemPrompt` | Stakeholder | Business-Value, UX, Endanwender-Sicht |
| `kundeX.anforderungPrompt` | Anforderungs-Vorlage | Strukturierte Erfassung von Features |
| `sokratischeProvokateur.systemPrompt` | Kritischer Denker | Hinterfragen von Annahmen, Logik-Check |
| `planer.systemPrompt` | Projektmanager | Milestones, Priorisierung, Roadmaps |
| `architect.systemPrompt` | System-Architekt | Tech-Stack, Skalierbarkeit, System-Design |
| `coder.systemPrompt` | Entwickler | Implementierung, Clean Code, SOLID |
| `tester.systemPrompt` | QA / Tester | Testpläne, Edge-Cases, Bug-Suche |
| `reviewer.systemPrompt` | Code-Reviewer | Qualitätssicherung, Security-Check |
| `devops.systemPrompt` | DevOps/SRE | CI/CD, Deployment, Automatisierung |

---

## Empfohlener Workflow

Um das beste Ergebnis zu erzielen, sollten die Prompts in einer logischen Reihenfolge eingesetzt werden:

### Phase 1: Exploration & Definition
1.  **`kundeX.anforderungPrompt`**: Formuliere die Idee oder Anforderung.
2.  **`kundeX.systemPrompt`**: Lass die KI die Anforderung aus Sicht des Kunden "challenge" (Ist das intuitiv?).
3.  **`sokratischeProvokateur.systemPrompt`**: Nutze diesen Prompt, um die Anforderung auf logische Lücken oder versteckte Komplexität zu prüfen.

### Phase 2: Planung & Architektur
4.  **`planer.systemPrompt`**: Zerlege die Anforderung in Arbeitspakete und erstelle eine Roadmap.
5.  **`architect.systemPrompt`**: Entscheide über den Tech-Stack und entwirf das System-Design.

### Phase 3: Implementierung
6.  **`coder.systemPrompt`**: Schreibe den eigentlichen Code basierend auf der Architektur und den Plänen.
7.  **`tester.systemPrompt`**: Lass gleichzeitig (oder vorab als TDD) Testfälle definieren, die der Code bestehen muss.

### Phase 4: Qualitätssicherung & Release
8.  **`reviewer.systemPrompt`**: Lass den geschriebenen Code kritisch prüfen (Refactoring-Bedarf? Sicherheitslücken?).
9.  **`devops.systemPrompt`**: Erstelle die notwendigen Skripte für Deployment, Containerisierung und CI/CD.

---

## Nutzungshilfe
Kopiere den Inhalt der jeweiligen `.systemPrompt`-Datei in das System-Feld deines KI-Chats (oder nutze die entsprechenden Datei-Referenzen deiner IDE/CLI), um die KI in die gewünschte Rolle zu versetzen.

*Tipp: Nutze `kundeX.memory`, um wichtige Entscheidungen des "Kunden" dauerhaft festzuhalten.*
