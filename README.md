# ⚙️ Automatisation DevOps avec Ansible & Docker

Ce dépôt illustre l'approche **Infrastructure as Code (IaC)** avec **Ansible** sur l'environnement **Cisco DEVASC**. Le Playbook automatise entièrement la construction, le déploiement et la vérification d'une application conteneurisée sous Docker.

## 🛠️ Technologies utilisées
* **Automatisation & IaC :** Ansible (`ansible-playbook`)
* **Conteneurisation :** Docker
* **Tests HTTP automatisés :** Module natif Ansible `uri`

## 📂 Structure du projet
* `hosts.ini` : Fichier d'inventaire ciblant la machine locale (`localhost`) dans le groupe `[serveurs_web]`.
* `deploy.yml` : Playbook Ansible qui nettoie les anciens conteneurs, construit l'image de l'API Flask, déploie le service sur le port `5002` et vérifie la réponse JSON de l'API.

## 💻 Exécution du déploiement automatisé

### Prérequis
Le projet `api-flask-docker` doit être présent dans `/home/devasc/api-flask-docker` et le service Docker doit être actif.

### Lancer le Playbook
```bash
ansible-playbook -i hosts.ini deploy.yml
```
Une fois l'exécution terminée, l'API déployée est accessible à l'adresse `http://localhost:5002/api/info`.

---
*Réalisé par [FAWA19-isi](https://github.com)*
