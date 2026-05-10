# Phase 2.2: System-Architektur (architect.systemPrompt)

**Rolle:** System-Architekt

## Technisches Design: GreenCycle Mobile Platform

### 1. Technologie-Stack
*   **Frontend:** React Native (Cross-Platform für iOS/Android, ermöglicht schnelles Prototyping).
*   **Backend:** Node.js mit Express (TypeScript) für hohe Performance und einfache Integration von ML-Bibliotheken.
*   **Datenbank:** PostgreSQL (Relationale Daten für User & Punkte) + Redis für schnelles Caching der Leaderboards.
*   **Bilderkennung:** TensorFlow Lite (on-device) zur Reduzierung der Serverlast und für bessere Offline-Performance.

### 2. High-Level Architektur
*   **Mobile App:** Hält lokalen State via Redux-Persist (Offline-First).
*   **API Gateway:** Validierung und Routing der Anfragen.
*   **Point Service:** Microservice zur Berechnung der Punkte und Verwaltung des "Baum-Wachstums".
*   **Partner Integration Service:** Schnittstelle zu externen Coupon-Systemen.

### 3. Sicherheitskonzept
*   **JWT-basierte Authentifizierung.**
*   **Rate-Limiting** an der API, um Missbrauch beim Punktesammeln zu verhindern.
*   **Hashing** von sensiblen Nutzerdaten (DSGVO-konform).

### 4. Skalierbarkeit
*   Containerisierung mittels **Docker** für einfaches Deployment.
*   Nutzung von **Cloud-S3** zur Speicherung der anonymisierten Müll-Fotos für das weitere Training des ML-Modells.
