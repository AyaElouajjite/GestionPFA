# GestionPFA — Plateforme de gestion des Projets de Fin d'Année

![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-4-7952B3?logo=bootstrap&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white)

Application web Django qui centralise le suivi des Projets de Fin d'Année (PFA) dans un établissement d'enseignement : constitution des binômes, attribution des sujets, dépôt et évaluation des rapports, gestion des échéances et communication entre étudiants et encadrants.

## Fonctionnalités

**Étudiants**
- Constitution des binômes (envoi et acceptation de demandes)
- Consultation et choix des sujets
- Dépôt des rapports et livrables
- Messagerie avec l'encadrant, avec pièces jointes
- Calendrier des échéances et notifications

**Enseignants**
- Publication et gestion des sujets
- Encadrement des équipes
- Évaluation des rapports
- Suivi des retards
- Statistiques et export Excel

**Administrateurs**
- Gestion des comptes et des rôles
- Définition des échéances

## Points techniques

- Projet Django structuré en trois applications : `users`, `pfa_projects`, `pfa_teams`
- Modèle utilisateur personnalisé avec gestion des rôles (étudiant, enseignant, administrateur)
- Système de notifications et de détection des retards
- Classification automatique des messages contenant un rapport
- Export des statistiques au format Excel avec **XlsxWriter**
- Commande de gestion personnalisée pour générer des données de test
- Formulaires mis en forme avec **django-crispy-forms** et Bootstrap 4

## Stack technique

Python · Django · SQLite · Bootstrap 4 · django-crispy-forms · XlsxWriter

## Architecture

```
GestionPFA/
├── pfa_management/   # Configuration du projet
├── users/            # Comptes, rôles et authentification
├── pfa_projects/     # Sujets, rapports, échéances, messagerie, statistiques
├── pfa_teams/        # Binômes et demandes d'équipe
├── templates/        # Gabarits HTML
└── manage.py
```

## Installation

**Prérequis :** Python 3.10 ou supérieur.

```bash
git clone https://github.com/AyaElouajjite/GestionPFA.git
cd GestionPFA

python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # Linux / macOS

pip install django django-crispy-forms crispy-bootstrap4 pillow xlsxwriter tabulate

python manage.py migrate
python manage.py seed_data          # facultatif : données de test
python manage.py createsuperuser
python manage.py runserver
```

L'application est accessible sur `http://localhost:8000` et l'interface d'administration sur `http://localhost:8000/admin/`.

## Contact

**Aya Elouajjite** — [github.com/AyaElouajjite](https://github.com/AyaElouajjite) — Aya.Ouajjite@emsi-edu.ma
