# 🌿 Étude de l’impact de l’urbanisation sur les oiseaux en Guadeloupe
Ce dépôt contient le code, les données et les résultats associés à l'analyse bioinformatique de la répartition des oiseaux selon l'environnement. Ce projet a été réalisé dans le cadre du Master 1 Bioinformatique et Biologie des Systèmes à l'Université de Toulouse (Paul Sabatier Toulouse III, FRANCE), année universitaire 2024-2025

## 📌 Description

Ce projet vise à étudier l'effet de l'urbanisation sur la répartition des espèces d'oiseaux endémiques de Guadeloupe, en s’appuyant sur des données écologiques et taxonomiques. L'analyse repose sur des méthodes statistiques multivariées appliquées via le langage R.

L’objectif principal est de déterminer si certaines caractéristiques environnementales (ex : urbanisation, type de sol, conditions climatiques) influencent la distribution et la physiologie des oiseaux observés.

## 📁 Structure du projet
* ```README.md``` : Fichier de présentation du projet (vous y êtes !)
* ```LICENSE``` : Licence d’utilisation
* ```AMOUROUX_RODRIGUES.pdf``` : Rapport d'analyse

* **scripts/** : Dossier regroupant l'ensemble des fichiers
  * ```Script.Rmd``` : Ensemble des codes utilisés pour l'analyse au format R markdown
  * ```Script.html``` : Ensemble des codes utilisés pour l'analyse au format HTML
  * ```Script_Q*.Rmd``` : Codes correspondants à chaque question posée dans le fichier ```Questions_envisagees.md``` au format R markdown
  * ```Script_Q*.html``` : Codes correspondants à chaque question posée dans le fichier ```Questions_envisagees.md``` au format HTML

* **data/** : Dossier abritant les données utilisées pour l'analyse
  * ```especes.tsv``` : Données des caractéristiques des espèces
  * ```habitat.tsv``` : Données environnementales par site d’écoute
  * ```communautes.tsv``` : Présence/absence des espèces sur chaque site
  * ```chi-2_q1_export*.txt``` : Résultats des tests du χ²
  * **images/** : Dossier abritant l'ensemble des graphiques produits (ACP, ACC, co-inertie, etc.)

* **documents/** : Dossier regroupant l'ensemble des documents préalables à l'analyse
  * ```PROJET_2024-25.pdf``` : Document de présentation du projet
  * ```Questions_envisagees.md``` : Problématiques scientifiques posées
  * ```Memo_ACP.md``` : Résumés de la méthode d'analyse en composantes principales


## 📋 Méthodologie
Les analyses statistiques utilisées incluent :
* Analyse en Composantes Principales (ACP)
* Analyse Factorielle des Correspondances (AFC)
* Analyse Canonique des Correspondances (ACC)
* Analyse des Correspondances Multiples (ACM)
* Analyse de Co-inertie
* Analyse Factorielle Discriminante (AFD)
* Tests du χ² d’indépendance

## ✅ Prérequis
* R version 4.x ou supérieure
* Packages : ade4, vegan, tidyverse, lmtest, MASS

## ⬇️ Installation et utilisation

Cloner ce dépôt :
```bash
git clone https://github.com/CamilleAstrid/fr.univ-tlse3_ADM_project.git
cd fr.univ-tlse3_ADM_project
```

Ouvrir une session R et charger les jeux de données :
```r
habitat <- read.table("data/habitat.tsv", sep="\t", header=TRUE)
especes <- read.table("data/especes.tsv", sep="\t", header=TRUE)
communautes <- read.table("data/communautes.tsv", sep="\t", header=TRUE)
```
Ou modifier le fichier ```script.rmd``` pour charger vos données
```r
habitat <- read.table(<chemin de votre fichier sur les caractéristiques de vos habitats>, sep=<type de séparateur>, header=<en-tête ou sans>)
especes <- read.table(<chemin de votre fichier sur les caractéristiques de vos espèces>, sep=<type de séparateur>, header=<en-tête ou sans>)
communautes <- read.table(<chemin de votre fichier sur la répartition des espèces en fonction des habitats>, sep=<type de séparateur>, header=<en-tête ou sans>)
```
Lancer les analyses statistiques du script dont les étapes sont décrites dans le PDF.

## 📊 Résultats
* Identification de variables environnementales influençant la répartition des espèces
* Évaluation du rôle de l’urbanisation
* Exploration des liens entre physiologie (taille) et milieu
* Proposition de pistes pour la conservation de la biodiversité aviaire

## 📖 Licence
Ce projet est sous licence MIT. Voir le fichier [LICENSE](https://github.com/CamilleAstrid/fr.univ-tlse3_ADM_project/blob/main/LICENSE) pour plus d’informations.

## 📍Références
* Données fournies par l'Université de Toulouse
* Données issues du Parc National de Guadeloupe, ONCFS, associations et bureaux d’études.

## 👥 Auteurs
Copyright (c) 2025 AMOUROUX J. CamilleAstrid

---
ℹ️ Pour toute question, veuillez contacter l'équipe en créant une *issue* ou par mail :
* [Camille-Astrid Rodrigues](mailto:camilleastrid.cr@gmail.com)
* [Jan Amouroux](mailto:jan.amouroux@univ-tlse3.fr)

Si des ajustements ou des ajouts sont nécessaires, n'hésitez pas à nous le signaler !
