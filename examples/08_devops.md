# Phase 4.2: DevOps & Release (devops.systemPrompt)

**Rolle:** DevOps Ingenieur

## Deployment-Strategie: GreenCycle Platform

### 1. CI/CD Pipeline (GitHub Actions)
Ich habe eine Pipeline definiert, die bei jedem Push in den `main` Branch folgende Schritte ausführt:
*   **Linting & Type-Check:** Sicherstellung der Code-Qualität.
*   **Unit Tests:** Ausführung der Jest-Tests (Phase 3).
*   **Docker Build:** Erstellung eines neuen Images für den Point-Service.
*   **Security Scan:** Überprüfung der Node-Module auf bekannte Schwachstellen (via `npm audit`).
*   **Deploy to Staging:** Automatisches Deployment in die Testumgebung.

### 2. Infrastruktur (Docker & Cloud)
```dockerfile
# Einfaches Dockerfile für den Point-Service
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY . .
EXPOSE 3000
CMD ["node", "dist/main.js"]
```

### 3. Monitoring
*   **Logging:** Integration von Winston/Morgan zur strukturierten Protokollierung in den ELK-Stack.
*   **Health Checks:** Endpoint `/health` zur Überwachung der Service-Verfügbarkeit.

### 4. Nächste Schritte
*   Einrichtung von Blue-Green-Deployments zur Vermeidung von Downtime.
*   Konfiguration von Auto-Scaling-Gruppen basierend auf der CPU-Auslastung.
