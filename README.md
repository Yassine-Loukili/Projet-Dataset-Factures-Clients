# Nettoyage de données – Projet Dataset Factures Clients

------------------------

## Description du projet
Ce projet porte sur l’analyse et le nettoyage d’un dataset de factures clients contenant des données issues d’une entreprise réelle ou simulée.  
Le but est de traiter les anomalies courantes telles que valeurs manquantes, incohérences de format, doublons et erreurs d’orthographe,  
afin de rendre le dataset exploitable pour des analyses commerciales, des visualisations ou du reporting.


## 📊 Structure des données et problèmes détectés

| Colonne       | Problèmes identifiés                                              |
|---------------|------------------------------------------------------------------|
| Nom Client    | - Valeurs manquantes (30 cas)                                    |
|               | - Incohérences de casse (majuscule / minuscule)                  |
|               | - Orthographes variées (ex : "Durand SA" vs "durand sa")         |
| Montant (€)   | - Formats incohérents (ex : "1.750", "1 000", "deux mille")      |
|               | - Type `object` alors que la colonne devrait être numérique       |
| Date Facture  | - Formats multiples (ex : "03/03/2023", "2023-03-23", "06-06-2023") |
| Payé ?        | - Variations de casse ("oui", "Oui", "NON")                      |
|               | - Valeurs manquantes (58 cas)                                    |

## ⚙️ Nettoyage réalisé

- Standardisation et correction des noms clients pour éviter les doublons logiques (uniformisation casse et orthographe)  
- Conversion des montants en valeurs numériques `float` ou `int` après nettoyage des formats variés  
- Uniformisation du format des dates de facturation au format `YYYY-MM-DD`  
- Harmonisation des valeurs de la colonne "Payé ?" en valeurs binaires standardisées (Oui / Non)  
- Gestion et suppression des lignes avec données critiques manquantes


## 📂 Fichiers inclus

- `data/` : dossier contenant les données brutes (dataset_factures_clients.csv)
- `notebooks/factures_cleaning.ipynb` : notebook détaillant le nettoyage pas à pas (Nettoyage dataset factures.ipynb)
- `outputs/factures_clean.csv` : dataset nettoyé prêt à être exploité (dataset_factures_clients.xlsx)

## 🚀 Résultat final

- Dataset nettoyé sans doublons ni valeurs critiques manquantes  
- Colonnes cohérentes avec formats normalisés (dates, montants numériques, noms clients standardisés)  
- Jeu de données prêt pour analyses avancées, visualisations ou intégration dans un dashboard


