# Phase 4.1: Code Review (reviewer.systemPrompt)

**Rolle:** Code Reviewer

## Review: `calculateGreenPoints` Funktion

### 1. Code-Qualität & Lesbarkeit
Der Code ist sauber strukturiert und nutzt TypeScript-Typing korrekt. Die Verwendung eines Objekts (`basePoints`) als Mapping ist effizienter als eine lange `switch`-Anweisung.

### 2. Verbesserungsvorschläge (Konstruktiv)
*   **Fehlerbehandlung:** Wie vom Tester angemerkt, fehlt die Behandlung von negativen Gewichten.
    *   *Vorschlag:* `if (weightGrams < 0) throw new Error("Weight cannot be negative");`
*   **Wartbarkeit:** Die `basePoints` sind aktuell hartkodiert in der Funktion.
    *   *Vorschlag:* Lagere diese Konfiguration in eine externe Datei oder Datenbank aus, damit Punkte geändert werden können, ohne den Code neu zu kompilieren.
*   **Magic Numbers:** Die Zahl `500` für den Multiplikator ist eine "Magic Number".
    *   *Vorschlag:* Definiere eine Konstante `WEIGHT_THRESHOLD_GRAMS = 500;`.

### 3. Sicherheit
Keine unmittelbaren Sicherheitsrisiken (keine SQL-Injection oder XSS möglich, da rein logische Funktion).

### 4. Fazit
**Status: Needs Changes.** Sobald die Validierung für negative Gewichte und die Extraktion der Konstanten erfolgt ist, kann der Code gemerged werden.
