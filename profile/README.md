# TeaSpoon Organisation

**TeaSpoon** spezialisiert sich auf **Webseiten für kleine Unternehmen**. Unser Fokus liegt auf **klaren, einfachen Designs**, die den Charakter des Unternehmens widerspiegeln – für echte Menschen, nicht für Suchmaschinen oder KIs.


## Mission

- Einfache, nutzerfreundliche Webseiten für Restaurants, Handwerksbetriebe, Künstler und kleine Unternehmen.
- Fokus auf **Ästhetik, Charakter und Persönlichkeit** der jeweiligen Marke.
- Bereitstellung von **sauberen, wartbaren Code-Basen**, die leicht zu deployen sind.


## Struktur der Produktions-Server

### 1. Globale Docker-Umgebung
- Repository: [global-docker-setup](https://github.com/teaspoon-de/global-docker-setup)
- Enthält die Infrastruktur für alle Websites:
  - Reverse Proxy mit NGINX
  - LetsEncrypt Companion für automatische SSL-Zertifikate
  - Zentrale MySQL-Datenbank
- Verwaltet über eine **globale Docker-Compose-Ebene**

### 2. Websites / PHP-Container
- Repository: [prod-php](https://github.com/teaspoon-de/prod-php)
- Jede Website läuft in **einem eigenen Docker-Compose-Setup**, bestehend aus:
  - NGINX als Webserver
  - Leicht modifiziertem PHP-Container (Repository: [prod-php](https://github.com/teaspoon-de/prod-php))
- Sollte leicht als Template verwendet werden können


## Deployment

- Globale Infrastruktur wird über `global-docker-setup` bereitgestellt und gepflegt
- Neue Websites können über separate Repos in die globale Umgebung eingebunden werden
- Deployment erfolgt über Docker Compose, GHCR und automatisierte Deploy-Skripte
