 SOC Lab Conteneurisé

Projet de déploiement d’un Security Operations Center (SOC) basé sur Docker Compose.

 Stack utilisée
Wazuh 
Suricata 
Grafana 
TheHive 
Docker Compose
 Prérequis
Docker & Docker Compose installés
Linux / WSL recommandé
Config système :
sysctl -w vm.max_map_count=262144
 Installation
Cloner le projet :
git clone <repo-url>
cd <projet>
Configurer les variables :
cp .env.example .env
Lancer la stack :
docker compose up -d
 Accès aux services
Wazuh Dashboard : https://localhost
Grafana : http://localhost:3000
TheHive : http://localhost:9000
 Structure
.
├── docker-compose.yml
├── .gitignore
├── .env.example
├── wazuh/
├── suricata/
├── grafana/
├── thehive/
└── rapport/
 Tests réalisés
Scan réseau (Nmap) → détecté par Wazuh
Brute force SSH → alerte + blocage
Injection SQL → détectée par Suricata
Gestion d’incident via TheHive
⚠️ Sécurité
Aucun secret en dur
Utilisation de .env
.env ignoré via .gitignore
👨‍💻 Auteurs

FATOU BOYE BA
MOUHAMED SY