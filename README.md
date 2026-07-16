# Portfolio Data Engineer

**Formation :** Data Engineer — RNCP niveau 7 (bac +5) — OpenClassrooms
**Période :** Juillet 2025 – Juillet 2026 (temps partiel)

---

## À propos

Ce portfolio présente les projets réalisés durant mon parcours de formation Data Engineer.
Il couvre l'ensemble de la chaîne de valeur de la donnée : collecte, stockage, modélisation,
transformation, orchestration de pipelines, machine learning et exposition des résultats.

---

## Récapitulatif des projets

| # | Projet | Outils clés | Compétence démontrée |
|---|--------|-------------|----------------------|
| 2 | Analyse de données de systèmes éducatifs | Python, Pandas, NumPy, Matplotlib/Seaborn | Analyse statistique descriptive, nettoyage de données |
| 3 | Base de données relationnelle | SQL, UML | Modélisation conceptuelle → relationnelle |
| 4 | Audit d'un environnement de données | SQL, analyse de risques | Rétro-ingénierie, audit technique |
| 5 | Stockage sécurisé et performant | Docker | Conteneurisation, sécurité des données |
| 6 | Prédiction de consommation de bâtiments | Python, Scikit-Learn, API | Machine learning, exposition via API |
| 7 | Base de données NoSQL | Python, MongoDB | Modélisation NoSQL, architecture on-premise |
| 8 | Infrastructure de données | Airbyte, gouvernance des données | Extraction, gouvernance, tests d'infrastructure |
| 9 | Infrastructure dans le cloud | AWS, Redpanda, PySpark | Architecture cloud, chargement de données |
| 10 | Pipeline d'orchestration des flux | Kestra | Orchestration, tests de mise en production |
| 11 | Système RAG | LangChain, Mistral, FAISS | IA générative, bases vectorielles |
| 12 | Automatisation d'un projet d'infrastructure | Pipelines automatisés | Suivi et ajustement de flux de données |
| 13 | Du POC au MVP (suite projet 11) + portfolio | LangChain, Mistral, FAISS | Gestion de projet data de bout en bout |

---

## Détail des projets

### Projet 2 — Analyse de données de systèmes éducatifs

**Contexte** : Analyse exploratoire des données éducatives mondiales (World Bank EdStats)
pour une entreprise fictive du secteur EdTech, afin d'identifier les pays les plus
performants et de recommander des cibles pour son expansion internationale.

**Outils** : Python, Pandas, NumPy, Matplotlib, Seaborn, Poetry

**Ce que j'ai fait** :
- Mis en place un environnement de travail avec Poetry
- Nettoyé et filtré le jeu de données pour ne garder que les indicateurs pertinents
- Analysé les corrélations entre indicateurs pour supprimer les redondances
- Comparé plusieurs méthodes pour sélectionner les pays les plus performants
- Classé les pays en trois catégories (Faible, Moyen, Élevé) pour faciliter la décision

**Compétence démontrée** : Analyse statistique descriptive, nettoyage et exploration de
données, configuration d'environnement de travail

---

### Projet 3 — Base de données relationnelle

**Contexte** : Conception d'une base de données relationnelle à partir de données
immobilières (transactions foncières, propriétés, référentiel géographique, données de
communes), en respectant la 3ème forme normale et les exigences RGPD.

**Outils** : SQL, SQLite, modélisation UML

**Ce que j'ai fait** :
- Analysé les données sources et construit un dictionnaire de données
- Modélisé la base de données (diagramme UML, passage au modèle relationnel, 3NF)
- Créé les tables et leurs relations (propriétés, ventes, communes, référentiel géographique)
- Écrit des requêtes SQL claires et documentées pour explorer et exploiter les données

**Compétence démontrée** : Modélisation et création de bases de données relationnelles,
structuration des données en cohérence avec leurs caractéristiques

---

### Projet 4 — Audit d'un environnement de données

**Contexte** : Investigation d'une anomalie de chiffre d'affaires détectée dans les
tableaux de bord Power BI d'une enseigne de distribution (« Super Smart Market ») :
un écart de plus de 9 000 € était apparu rétroactivement sur les ventes d'une journée,
remettant en question la fiabilité du système décisionnel (ERP → cube OLAP Azure
Analysis Services → Power BI).

**Outils** : SQL, Azure Analysis Services (cube OLAP), analyse de logs

**Ce que j'ai fait** :
- Analysé l'architecture technique existante et les flux de données (ETL, cube OLAP)
- Investigué plus de 200 000 lignes de logs pour retracer l'origine de l'anomalie
- Reconstitué le problème sur un environnement de test (prototype) pour le quantifier
- Identifié la cause racine (données arrivées en retard dans le système) et deux autres
  problèmes de fiabilité des données
- Évalué les risques associés et proposé un plan d'action priorisé (immédiat, court terme,
  moyen terme)
- Présenté le rapport d'audit et les recommandations

**Compétence démontrée** : Audit et rétro-ingénierie d'un environnement de données,
analyse et évaluation des risques, prototypage technique

---

### Projet 5 — Stockage sécurisé et performant

**Contexte** : Migration automatisée d'un jeu de données médicales (55 000+ patients,
format CSV) vers une base MongoDB, avec un système d'authentification par rôles et une
infrastructure conteneurisée.

**Outils** : Python, MongoDB, Docker / Docker Compose, Poetry, Pytest

**Ce que j'ai fait** :
- Conçu un pipeline de migration CSV → MongoDB avec insertion par lots
- Mis en place un système d'authentification avec plusieurs rôles (analyste, administrateur,
  root) et permissions différenciées
- Conteneurisé l'ensemble de la solution avec Docker Compose (base de données,
  initialisation des rôles, migration, tests)
- Sécurisé la configuration via des variables d'environnement
- Écrit des tests automatisés pour valider la migration
- Documenté l'architecture et le fonctionnement du projet

**Compétence démontrée** : Conteneurisation, sécurité et gestion des accès aux données,
configuration d'un environnement de stockage performant

[→ Voir le repo GitHub](https://github.com/PaulineFERNOUX/migration_mongodb)

---

### Projet 6 — Prédiction de consommation de bâtiments

**Contexte** : Accompagnement d'une ville dans son objectif de neutralité carbone, en
prédisant les besoins en consommation énergétique de ses bâtiments à partir de leurs
caractéristiques.

**Outils** : Python, Scikit-Learn, API REST

**Ce que j'ai fait** :
- Nettoyé les données et créé de nouvelles variables (feature engineering), en veillant à
  éviter les fuites de données (data leakage)
- Entraîné plusieurs modèles d'apprentissage supervisé et comparé leurs performances
- Évalué les modèles avec une séparation train/test et des métriques adaptées
- Développé une API pour exposer les prédictions, avec validation des données envoyées
- Présenté les résultats et la démarche de résolution du problème

**Compétence démontrée** : Machine learning (entraînement, évaluation, feature
engineering), mise à disposition de résultats via une API

---

### Projet 7 — Base de données NoSQL

**Contexte** : Restauration et sécurisation de la base de données MongoDB d'une
association étudiant l'impact des locations courte durée (type Airbnb) sur le marché
du logement à Paris et Lyon, à la suite d'un crash total de la base parisienne.

**Outils** : Python, MongoDB (CLI, Compass, ReplicaSet, Sharding), Polars, Power BI

**Ce que j'ai fait** :
- Restauré et réimporté les données dans MongoDB (dataset de plus de 100 000 annonces)
- Analysé la structure des documents et les avantages du NoSQL pour ce type de données
  (champs imbriqués, schéma flexible, gros volumes)
- Écrit des requêtes en ligne de commande et avec Polars pour produire des statistiques
  (taux de réservation, médianes, densité par quartier...)
- Connecté la base à Power BI pour visualiser les résultats
- Conçu une architecture multi-sites (Paris/Lyon) avec un ReplicaSet (tolérance aux
  pannes) et du Sharding (distribution des données par ville pour la performance)
- Schématisé l'architecture physique et le workflow de collecte et de stockage

**Compétence démontrée** : Conception et manipulation de bases NoSQL, architecture de
réplication et de distribution de données (on-premise)

---

### Projet 8 — Infrastructure de données

**Contexte** : Projet de synthèse pour GreenAndCoop, coopérative fictive de production
d'électricité renouvelable (Hauts-de-France). Objectif : intégrer des données
météorologiques hétérogènes de plusieurs sources (stations participatives) pour
améliorer les algorithmes de prévision de la demande d'électricité (projet « Forecast 2.0 »).

**Outils** : Airbyte, MongoDB, Docker / Docker Compose, AWS (S3, ECS, CloudWatch), Python, Poetry, Pytest

**Ce que j'ai fait** :
- Formalisé les processus de collecte, transformation, validation et stockage sous forme
  de logigramme, en intégrant la gestion des erreurs et des cas non nominaux
- Installé et paramétré Airbyte pour extraire les données des sources météo vers AWS S3
- Construit un pipeline Python de transformation et de chargement des données vers MongoDB
- Conçu une base MongoDB dénormalisée (une seule collection avec station embarquée),
  adaptée aux usages de data science
- Mis en place un environnement de développement local (Docker, ReplicaSet MongoDB,
  tests unitaires) et un environnement de production sur AWS (ECS, monitoring CloudWatch)
- Testé l'infrastructure : accessibilité des données, conformité au schéma, réplication

**Compétence démontrée** : Conception et industrialisation d'une infrastructure de
données de bout en bout (ingestion, stockage, tests, déploiement cloud)

---

### Projet 9 — Infrastructure dans le cloud

**Contexte** : Modélisation d'une infrastructure de données hybride pour une entreprise
fictive (« InduTechData ») souhaitant moderniser sa gestion de données sur le cloud AWS.
Le projet inclut un proof of concept (POC) de pipeline de traitement de tickets clients
en temps réel.

**Outils** : AWS (S3, datalake/datalakehouse), Redpanda (streaming compatible Kafka),
PySpark, Docker / Docker Compose, Poetry

**Ce que j'ai fait** :
- Modélisé une architecture de données combinant ingestion batch et streaming selon les
  sources, avec un datalakehouse organisé selon le modèle médaillon (bronze/argent/or)
- Développé un POC de pipeline temps réel : un producteur envoie des tickets clients
  dans un topic Redpanda, un consommateur PySpark les traite et les enrichit (ajout de
  l'équipe support selon le type de demande), puis exporte des agrégations (par type,
  équipe, priorité)
- Conteneurisé l'ensemble du pipeline avec Docker Compose
- Évalué la compatibilité des composants choisis avec l'environnement SI existant
- Documenté l'architecture et le fonctionnement du projet (schémas, README, vidéo
  explicative)

**Compétence démontrée** : Conception d'architecture de données cloud, ingestion batch
et streaming, sélection de composants adaptés au besoin métier

---

### Projet 10 — Pipeline d'orchestration des flux

**Contexte** : Automatisation mensuelle du calcul du chiffre d'affaires et de la
segmentation des produits pour une entreprise fictive de vente de vins
(« BottleNeck »), à partir de trois sources de données distinctes (ERP, site web,
fichier de liaison).

**Outils** : Kestra, Polars, DuckDB, Python, Docker

**Ce que j'ai fait** :
- Conçu un pipeline complet avec Kestra : ingestion des trois sources en parallèle,
  nettoyage et dédoublonnage, fusion des données avec DuckDB, calcul du chiffre
  d'affaires, puis classification des produits par z-score
- Automatisé le déclenchement du pipeline via un trigger planifié (le 15 de chaque
  mois), avec gestion des erreurs (retries, timeouts) sur les tâches sensibles
- Intégré trois niveaux de tests automatisés à des étapes clés du pipeline : sur les
  données sources, après la fusion (cohérence du chiffre d'affaires calculé de deux
  façons différentes), et sur la segmentation par z-score
- Réalisé un diagramme de flux détaillant les étapes et les points de décision
- Exporté les livrables attendus (rapport de chiffre d'affaires, listes de produits
  premium et ordinaires)

**Compétence démontrée** : Orchestration de pipelines de données, mise en place de
tests automatisés pour fiabiliser une mise en production

---

### Projet 11 — Système RAG (Retrieval-Augmented Generation)

**Contexte** : Conception d'un chatbot d'aide à la découverte d'événements culturels en
Occitanie (à partir des données Open Agenda), capable de répondre à des questions en
s'appuyant sur une base vectorielle et un modèle de langage.

**Outils** : LangChain, Mistral (embeddings et génération), FAISS, Python

**Ce que j'ai fait** :
- Récupéré et préparé un corpus d'événements culturels, avec un chunk par événement
- Filtré les données selon la période et la zone géographique concernées
- Vectorisé les événements avec les embeddings Mistral et indexé le tout dans FAISS
- Construit le pipeline de question-réponse avec LangChain (récupération des documents
  pertinents puis génération de la réponse)
- Écrit des tests automatisés vérifiant la cohérence de la période, du périmètre
  géographique, et l'alignement entre l'index FAISS et les métadonnées
- Documenté le projet et identifié des pistes d'amélioration pour une version plus
  industrialisée

**Compétence démontrée** : Conception d'un système RAG de bout en bout, nettoyage de
données pour améliorer la qualité des réponses, configuration d'un environnement de
travail reproductible

---

### Projet 12 — Automatisation d'un projet d'infrastructure

**Contexte** : Mise en place d'un pipeline pour calculer automatiquement deux avantages
liés au sport en entreprise (prime sportive et jours de bien-être) à partir des activités
sportives des salariés, avec notifications Slack et restitution décisionnelle.

**Outils** : Docker, PostgreSQL, Debezium, Kafka, MinIO, Spark, Power BI, Apache Airflow, Slack

**Ce que j'ai fait** :
- Construit un pipeline de données conteneurisé : ingestion des activités sportives dans
  PostgreSQL, synchronisation événementielle avec Debezium/Kafka vers un data lake MinIO
- Développé un traitement batch Spark en couches bronze/silver/gold, aboutissant à une
  table analytique (1 ligne par salarié et par année)
- Mis en place des notifications Slack automatiques à chaque nouvelle activité sportive
- Créé un rapport Power BI pour suivre l'éligibilité aux avantages et leur impact financier
- Externalisé les règles métier (taux de prime, seuils, modes de trajet éligibles) dans un
  fichier de configuration pour permettre leur ajustement sans redéploiement
- Orchestré l'ensemble avec Apache Airflow (DAG à 6 tâches, exécution quotidienne planifiée,
  gestion des erreurs avec retry) et mis en place un suivi de la volumétrie des données à
  chaque exécution

**Compétence démontrée** : Conception d'un pipeline de données automatisé et orchestré,
paramétrage métier externalisé, suivi et fiabilisation des flux de données

[→ Voir le repo GitHub](https://github.com/PaulineFERNOUX/poc-solutions_data)

---

### Projet 13 — Du POC au MVP : portfolio de synthèse

**Contexte** : Projet de synthèse final consistant à faire évoluer le système RAG conçu
au projet 11 (chatbot de recommandation d'événements culturels) d'un POC vers un MVP,
dans le cadre d'une mission avec un commanditaire fictif. Le projet inclut la gestion
complète du projet data (cadrage, planification, suivi) ainsi que la réalisation de ce
portfolio professionnel.

**Ce que j'ai fait / ce que je fais** :
- Collecté les besoins métier et analysé le contexte du commanditaire pour définir le
  périmètre du MVP
- Défini les modalités de réalisation et de suivi du projet (planning, jalons, livrables)
- Rédigé un rapport de gestion de projet complet (délais, coûts, livrables, performance)
- Réalisé ce portfolio professionnel récapitulant l'ensemble des projets du parcours
- Préparé une présentation orale démontrant la gestion de plusieurs priorités dans un
  contexte évolutif, avec un appui stratégique et méthodologique à la prise de décision

**Compétence démontrée** : Gestion de projet data de bout en bout, passage d'un POC à un
MVP industrialisable, identification et diffusion de nouvelles opportunités/pratiques
dans le champ de la data, communication avec les parties prenantes

---

## Compétences démontrées

**Techniques**
- Analyse statistique descriptive (Python, Pandas)
- Modélisation de données (relationnel, NoSQL)
- Développement de pipelines ETL / ELT (Airbyte, Kestra)
- Machine learning et mise à disposition de modèles via API
- Conteneurisation (Docker)
- Architecture et déploiement cloud
- IA générative (RAG, LangChain, bases vectorielles)
- SQL, Python, Git/GitHub

**Gestion de projet**
- Cadrage des besoins métiers et analyse de contexte
- Pilotage délais / coûts / livrables / performance
- Analyse et anticipation des risques projet
- Coordination des parties prenantes

**Valeur ajoutée pour une organisation**
- Fiabilisation et automatisation des flux de données
- Réduction du temps de traitement manuel
- Mise à disposition de données exploitables pour les équipes data science et métier
- Sécurisation et gouvernance des environnements de données

---

## Stack technique globale

`Python` · `SQL` · `Pandas` · `Scikit-Learn` · `Docker` · `Airbyte` · `Kestra` ·
`MongoDB` · `LangChain` · `Mistral` · `FAISS` · `Git / GitHub` · `AWS`
