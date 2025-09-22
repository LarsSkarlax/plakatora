# Plan

Hier der Plan zur Entwicklung des Projekts:

## Projektbasis festlegen

Versionskontrolle: Git (GitHub/GitLab).

Lizenz: z. B. MIT oder Apache 2.0, damit klar ist, dass es Open Source ist.

Grund-Repository-Struktur (z. B.):
/backend
/frontend-web
/frontend-mobile
/docs

## Backend als Herzstück bauen

Das Backend ist das zentrale System, darauf greift später alles zu.

1. Stack wählen
   - Django Rest Framework (schneller Start, fertiges Auth, Admin-UI).
   - Datenbank: PostgreSQL (mit PostGIS für Karten-Funktionalität).

2. Minimal umsetzen
   - User-Registrierung & Login (JWT).
   - Organisations-Modell + Rollen (Admin, Member).
   - Endpunkte für „Poster-Typen“ und „Standorte“.
   - API sauber dokumentieren (z. B. mit Swagger oder ReDoc).

👉 Nach diesem Schritt kannst du schon Testdaten in der DB anlegen und mit Postman oder curl checken, ob alles läuft.

## Web-Frontend entwickeln

Warum Web zuerst?

Schneller zu entwickeln & testen.

Jeder Browser kann drauf zugreifen, auch auf dem Handy.

1. Stack wählen
    - React + Vite (leichtgewichtig, schnell).
    - Kartenanzeige: Leaflet.js oder Mapbox GL.

2. Minimal umsetzen
    - Login/Logout + Organisationswechsel.
    - Karte anzeigen.
    - Standort hinzufügen + Typ auswählen.
    - Standorte aus DB laden & rendern.

👉 Ab hier hast du schon eine funktionierende „Plakat-Tracker-Web-App“.

## Mobile App entwickeln

Sobald die Basis funktioniert:

- React Native (mit Expo) → du kannst viel Code vom Web-Frontend wiederverwenden.
- Erste Version: Karte anzeigen + Standorte hinzufügen.
- Später: Offline-Speicherung + Fotos.

## Deployment & Kollaboration

Backend + DB in die Cloud (z. B. Railway/Render oder Hetzner).

Frontend-Web auf Vercel/Netlify deployen.

App erst als Testversion über Expo verteilen, später in die Stores.

CI/CD: GitHub Actions für Tests & automatisches Deployment.

## Iterativ ausbauen

- Rechteverwaltung verbessern.
- Foto-Upload zu Standorten.
- Export (CSV/GeoJSON).
- Offline-Funktion für die App.
  