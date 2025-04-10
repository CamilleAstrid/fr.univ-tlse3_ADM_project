# Jeux de données
* communautés = répartition des espèces aux points d'écoute
* habitat = caractéristiques des points d'écoutes, de l'environnement
* espèces = caractéristiques des espèces enregistrées

# Choix de la problématique à partir des *datasets*
Etude de l’impact de l’urbanisation sur les oiseaux.

# Détermination des sous-analyses

## Question 1 : Quel est l'impact de l'environnement sur la répartition des espèces ?
auteur : ***CamilleAstrid***

Recherche d'interactions ou d'évitements des points de certains environnements ou encore des congénères.

### *Datasets* utilisés
* *communautés* : quelles sont les espèces qui vivent ensemble ? même localisation ? exemple : Est-ce que pinson toujours avec pie ?
* *habitat* : différentes répartitions selon la localisation ? exemple : Quand il fait chaud, les pinsons ne blairent plus les pies ?

### ANALYSE
* test du Chi² pour vérifier la dépendance entre les données localisations et présence de l'espèce
* ACM(commu) : nous avons des données utilisant des modalités simples avec j individus et i localisations
* expected : groupes d'oiseaux, oiseaux "ubiquitaires"
* test corrélation des variables entre-elles pour diminuer le nombre de variables à étudier
* ACP(habitat) : lissage des données qualitatives au besoin, réduction du nombre de variables
* co-inertie = ACM+ACP : couplage de tableaux entre habitat et répartition espèces
* expected : présence de cluster en fonction de certaines caractéristiques du milieu
* conclure : comportements différents selon la qualité de vie du milieu (caractéristiques ciblées par l'analyse)

## QUESTION 2 : Quel est l'impact des caractéristiques de l'habitat sur les caractéristiques des espèces ?
auteur : ***AMOUROUX J.***

Notamment, petit ou grand selon la température ou autres paramètres ?

### *Datasets* utilisés
* *espèces* : caractéristiques
* *habitat* : caractéristiques

### ANALYSE
* extraire informations précédentes = subset par colonnes dont on extrait les numéros des localisations
* moyenne des données sur l'habitat pour chaque colonne du subset (espèces)
* expliquer chacune des variables de l'espèce en fonction des variables de l'environnement
  * taille petite quand température haute, alimentation quand hydrométrie élevée
* juxtaposition des tableaux :
  * tab1 : subset = colnames(especes) + moyenne de chaque caractéristique des milieux
  * transposé de tab1 sur tab2
  * tab2 : especes
* expected : certaines caractéristiques du milieu explique certaines caractéristiques de l'espèce
* conclure : physiologie différente selon les caractéristiques du milieu

## QUESTION 3 : Quel est l'impact de l'urbanisation sur la répartition des epèces ?
auteur : ***CamilleAstrid***

Moins d'espèces A ou plus d'espèces B en zones urbaines que rurales...

### *Datasets* utilisés
* *habitat* : urbanisation
* *communautés* : répartition des espèces

### ANALYSE
* chi² entre commu et habitat$bati
* ACP(commu[,2:length(commu[1,])]~habitat$bati)
* conclure : certaines espèces fuient les milieux urbains quand d'autres si refugent

## QUESTION 4 : Quel est l'impact de l'urbanisation sur la taille des oiseaux ?
auteur : ***AMOUROUX J.***

Exemple : diminution de la taille pour se cacher de l'Homme ?

### *Datasets* utilisés
* *habitat* : urbanisation
* *espèces* : taille

### ANALYSE :
* chi² entre espece$taille et habitat$bati
* modèle linéaire
* conclure :
  * l'urbanisation diminiue la taille : moins de nourriture naturelle accessible, prédation par l'Homme et les chats
  * l'urbanisation augmente la taille : plus de nourriture humaine accessible (gras, sucré...), moins de prédation globale (pas de serpent, pas de chats sauvages, pas d'aigles...)

## QUESTION 5 : Quel est la répartition des espèces protégées face à l'urbanisation ?
auteur : ***AMOUROUX J.***

Est-ce que les oiseaux protégés sont davantages présents dans les milieux urbains : protection intense par l'Homme, abondance de nourriture, absence de prédateurs, habitats cachés et sécuritaires...

### *Datasets* utilisés
* *habitat* : urbanisation
* *espèces* : protégée ou non ?

### ANALYSE
* chi² entre habitat$bati et especes$IUCN
* ACM
* conclure :
  * les oiseaux protégés sont davantages présents dans les milieux urbains :
    * protection intense par l'Homme, abondance de nourriture, absence de prédateurs, habitats cachés et sécuritaires...
  * les oiseaux protégés sont très peu présents dans les milieux urbains
    * prédaction par les chats domestiques, accidents avec les véhicules, pollution, peu d'alimentation naturelle, peu d'habitats naturels...
