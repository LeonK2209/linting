# CI/CD Pipeline – Mascot API

![Pipeline](https://github.com/LeonK2209/gha-03-cicd-pipeline/actions/workflows/pipeline.yml/badge.svg)

Lab 6 / LinkedIn Learning „Learning GitHub Actions“, Kapitel 3 (03_02 – 03_06).

Eine Python/Flask-API, die bei jedem Push automatisch durch eine dreistufige Pipeline läuft:

| Stufe | Job | Was passiert |
|---|---|---|
| 1 | `lint-and-test` | flake8 + pylint, danach Unit-Tests (`unittest`) |
| 2 | `build` | Docker-Image bauen und in die GitHub Container Registry (ghcr.io) pushen |
| 3 | `test-image` | Genau dieses Image pullen, Container starten, mit `curl` testen |

Jede Stufe startet nur, wenn die vorige erfolgreich war (`needs`).
Das gebaute Image erscheint rechts auf der Startseite unter **Packages**.

Manuell starten: **Actions → Pipeline → Run workflow**.
