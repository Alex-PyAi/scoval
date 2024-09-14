# **Plateforme intelligente pour la configuration, l'analyse et la supervision des machines industrielles**

## 1. **Description du projet**

La **plateforme intelligente** que nous proposons a pour objectif de transformer la gestion des machines industrielles en une expérience moderne, intuitive et efficace. Elle permet aux ingénieurs et opérateurs de configurer dynamiquement les machines (telles que des malaxeurs, des robots, etc.), de surveiller leurs performances en temps réel via un tableau de bord IoT, et d’analyser les données de production pour améliorer l’efficacité opérationnelle.

En plus des fonctionnalités de configuration et d'analyse, la plateforme intègre un modèle de langage naturel (LLM), qui permet aux utilisateurs d'interagir avec les machines via des commandes simples en langage naturel, facilitant ainsi l'accès aux données complexes et à la gestion des paramètres, même pour les utilisateurs non techniques.

Les principaux avantages incluent :
- **Amélioration des performances des machines** grâce à l'analyse de données en temps réel.
- **Réduction des temps d'arrêt** grâce à la maintenance prédictive basée sur les données des capteurs.
- **Accessibilité accrue** grâce à l'intégration d'une IA permettant des interactions en langage naturel.

## 2. **Fonctionnalités principales**

1. **Configuration dynamique des machines** :
   - Ajustez à distance les paramètres essentiels des machines comme la vitesse, la température, et les angles des robots via une interface web conviviale.
   - Créez, modifiez et enregistrez des profils de configuration pour redémarrer facilement des processus répétitifs.

2. **Tableau de bord IoT en temps réel** :
   - Suivi des données provenant des capteurs connectés sur les machines en temps réel (température, pression, vibrations, etc.).
   - Visualisation intuitive des KPI à travers des graphiques dynamiques.
   - Système d’alerte automatique en cas de dépassement de seuil critique, réduisant ainsi les risques de panne imprévue.

3. **Analyse des performances** :
   - Génération de rapports détaillés sur les performances des machines, mettant en évidence les tendances et les anomalies.
   - Analyse des données historiques et actuelles pour optimiser les opérations et prévenir les pannes.

4. **Assistant en langage naturel (LLM)** :
   - Posez des questions et envoyez des commandes à la machine via des phrases simples comme « Quelle est la température du malaxeur ? » ou « Configure la machine à 2000 RPM ».
   - L'IA comprend et répond en temps réel, rendant les interactions plus accessibles et rapides.

## 3. **Architecture du projet**

L’architecture est divisée en plusieurs modules pour permettre une meilleure organisation et évolutivité du projet :

```
/mon-projet-configuration-dynamique-machines
│
├── /backend                     # Backend API (FastAPI ou Django)
│   ├── /app
│   │   ├── /routers             # Endpoints/API routes
│   │   ├── /models              # Modèles de données (Pydantic ou ORM)
│   │   ├── /schemas             # Schémas de validation des données (Pydantic)
│   │   ├── /services            # Logique métier, interaction avec les capteurs/machines
│   │   ├── /database            # Connexion à la base de données (PostgreSQL, etc.)
│   │   └── main.py              # Point d'entrée de l'application backend
│   ├── /tests                   # Tests unitaires et d'intégration backend
│   └── requirements.txt         # Dépendances Python
│
├── /frontend                    # Frontend (React)
│   ├── /public                  # Fichiers statiques (images, logos, etc.)
│   ├── /src
│   │   ├── /components          # Composants React
│   │   ├── /pages               # Pages principales de l'application (dashboard, configuration)
│   │   ├── /services            # Interaction avec l'API backend
│   │   ├── /styles              # Feuilles de styles (CSS ou SCSS)
│   │   └── App.js               # Composant principal React
│   ├── /tests                   # Tests unitaires et fonctionnels frontend
│   └── package.json             # Dépendances JavaScript
│
├── /iot                         # Gestion des capteurs et IoT (si nécessaire)
│   ├── /firmware                # Code source pour microcontrôleurs (si applicables)
│   ├── /simulations             # Scripts de simulation de capteurs/machines
│   └── /scripts                 # Scripts pour la collecte de données
│
├── /models                      # Modèles Machine Learning (s'il y en a)
│   ├── /training                # Scripts d'entraînement des modèles
│   ├── /data                    # Datasets (ou liens vers les datasets)
│   └── /inference               # Modèles de prédiction/maintenance
│
├── /docs                        # Documentation du projet
│   ├── /api                     # Documentation de l'API backend
│   ├── /architecture            # Documentation de l'architecture du projet
│   └── README.md                # Présentation du projet
│
├── /scripts                     # Scripts utilitaires pour le projet (déploiement, tests, etc.)
│   └── init_db.py               # Script d'initialisation de la base de données
│
├── .env                         # Variables d'environnement (à exclure du repo avec .gitignore)
├── .gitignore                   # Fichier gitignore
├── docker-compose.yml           # Configuration Docker pour l'orchestration des services
└── README.md                    # Documentation principale du projet
```

---

## 4. **Installation**

### 1. Cloner le dépôt :
```bash
git clone https://github.com/username/mon-projet-configuration-dynamique-machines.git
cd mon-projet-configuration-dynamique-machines
```

### 2. Backend (FastAPI/Django) :
1. Naviguez vers le répertoire `backend` :
   ```bash
   cd backend
   ```
2. Créez un environnement virtuel et activez-le :
   ```bash
   python -m venv venv
   source venv/bin/activate   # sur Windows: venv\Scripts\activate
   ```
3. Installez les dépendances Python :
   ```bash
   pip install -r requirements.txt
   ```
4. Créez un fichier `.env` avec vos variables d’environnement (connexion à la base de données, etc.).
5. Démarrez le serveur backend :
   ```bash
   uvicorn app.main:app --reload
   ```

### 3. Frontend (React) :
1. Naviguez vers le répertoire `frontend` :
   ```bash
   cd frontend
   ```
   
2. Installez les dépendances JavaScript :
   ```bash
   npm install
   ```
   
3. Démarrez l'application frontend :

    ```bash
   npm start
   ```

### 4. Optionnel : Lancer avec Docker :
Si Docker est configuré, exécutez tous les services via Docker Compose :
```bash
docker-compose up --build
```

## 5. **Utilisation**

### 1. Accéder à l'interface web :
   - L’interface utilisateur React est accessible via [http://localhost:3000](http://localhost:3000).
   - Vous pouvez configurer et surveiller les machines depuis cette interface.

### 2. Utiliser l’API backend :
   - L'API FastAPI est disponible sur [http://localhost:8000](http://localhost:8000).
   - Utilisez des endpoints comme `/configurations` pour modifier les paramètres des machines et `/status` pour récupérer des données en temps réel.

### 3. Interaction en langage naturel :
   - Posez des questions comme « Quelle est la performance du malaxeur aujourd'hui ? » ou « Configure le robot à 2000 RPM » via l’interface web pour utiliser l’IA intégrée.
