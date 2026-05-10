# Phase 2.1: Projektplanung (planer.systemPrompt)

**Rolle:** IT-Projektplaner

## Projekt: GreenCycle Recycle-Reward Tracker

### 1. Meilensteine (Roadmap)
*   **M1: MVP Definition & Core Logic (Woche 1-2):** User-Authentifizierung, einfache Müll-Kategorisierung (manuell), Punktesystem.
*   **M2: Image Recognition Integration (Woche 3-5):** Prototyp der Bilderkennung für Plastik und Glas.
*   **M3: Gamification & Rewards (Woche 6-7):** "Digitaler Baum" Logik, Partner-Coupon-Anbindung.
*   **M4: Beta-Test & Polishing (Woche 8):** Lokaler Testlauf mit 50 Usern.

### 2. Arbeitspakete (User Stories)
*   **US.1:** Als User möchte ich mich registrieren, um meine Punkte zu speichern.
*   **US.2:** Als User möchte ich eine Müllart wählen, um Punkte zu erhalten.
*   **US.3:** Als User möchte ich meinen Baum sehen, um meinen Fortschritt zu visualisieren.
*   **US.4:** Als Admin möchte ich Partner-Coupons verwalten können.

### 3. Risiken & Priorisierung
*   **Risiko:** Offline-Fähigkeit (Kunden-Feedback). Lösung: Lokales Caching der Scans, Synchronisierung bei Internetverbindung.
*   **Priorität:** Höchste Prio auf US.1 und US.2 (Core Loop). US.3 ist wichtig für die Bindung (Must-have). Bilderkennung (M2) könnte zum "Should-have" werden, falls die Tech zu komplex wird.

### 4. Nächste Schritte
*   Architektur-Review zur Offline-Sync-Strategie.
*   UI-Mockups für den "Baum-Wachstum".
