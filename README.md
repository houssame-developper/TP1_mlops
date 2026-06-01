
# Pipeline de Données Modulaire (TP Chapitre 2)

##Full name : Houssame Bouyous
##Sector : Master AI

Ce projet implémente un pipeline de données complet utilisant une architecture moderne (Modern Data Stack).

## 1. Schéma du Pipeline
```
[ CSV Data ] -> (ingest.py) -> [ DuckDB Raw ]
                                     |
                               (validate.py)
                                     |
[ dbt Models ] <- (dbt run) <- [ DuckDB Clean ]
      |
(dbt test) -> [ Quality Reports ]
      |
[ Orchestration: Dagster ]
[ CI: GitHub Actions ]
```

## 2. Structure du Projet
- **data/** : Données brutes.
- **pipeline/** : Scripts d'ingestion, validation et orchestration.
- **dbt_pipeline/** : Transformations SQL et tests.
- **.github/workflows/** : Automatisation CI.

## 3. Historique Git du Projet
```
* [33m356e91a[m[33m ([m[1;36mHEAD -> [m[1;32mmaster[m[33m)[m Finalisation du pipeline : Tests dbt, Orchestration et CI
* [33mdcb89c8[m Ajout de la configuration dbt et des modèles de transformation
* [33mda9c95f[m Ajout de l'étape de validation minimale
* [33m9f228d9[m Ajout de l'étape d'ingestion
* [33mb8f2f55[m Ajout de l'étape d'ingestion
```

## 4. Réponses aux Questions Théoriques
1. **Pipeline vs Notebook** : Séparation des responsabilités, modularité et tests facilités.
2. **Rôle de Git** : Versionnage, collaboration et traçabilité des changements.
3. **requirements.txt** : Reproductibilité de l'environnement.
4. **validate.py** : Détection précoce des erreurs de données (fail-fast).
5. **dbt test** : Garantie de l'intégrité des données transformées.
6. **Dagster** : Gestion des dépendances et observabilité du workflow.
7. **CI** : Validation automatique du code à chaque commit.
8. **Industrialisation** : Nécessite Cloud, Secret Management et Monitoring.

## 5. Comment exécuter
1. `pip install -r requirements.txt`
2. `python pipeline/ingest.py`
3. `cd dbt_pipeline && dbt run && dbt test`
