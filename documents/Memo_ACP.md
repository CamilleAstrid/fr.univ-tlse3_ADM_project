# ACP : Analyse en Composantes Principales

## Résumé de l’ACP
L’Analyse en Composantes Principales (ACP) est une méthode statistique utilisée pour réduire la dimensionnalité d’un ensemble de données tout en conservant un maximum d’information. Elle transforme des variables corrélées en un nouvel ensemble de variables non corrélées, appelées composantes principales. Ces composantes sont ordonnées de sorte que la première explique le plus de variance possible, la seconde le second plus grand montant de variance, etc.  

L’ACP est souvent utilisée en exploration de données, en visualisation (notamment quand on a des données multidimensionnelles), et en prétraitement pour des modèles d’apprentissage automatique.  


## Détails de l’ACP

1. **Objectif**
L’ACP cherche à résumer l’information contenue dans un grand nombre de variables en un plus petit nombre de nouvelles variables, tout en minimisant la perte d’information.  

2. **Étapes du calcul**

    1. *Standardisation des données*
       - Comme l’ACP est influencée par l’échelle des variables, on commence par centrer et réduire les données (moyenne 0 et écart-type 1 pour chaque variable).  
     
    2. *Calcul de la matrice de covariance (ou de corrélation)*
       - Cette matrice indique comment les variables sont liées entre elles.  
       - Si les variables sont sur des échelles différentes, on privilégie la matrice de corrélation plutôt que celle de covariance.  

    3. *Décomposition en valeurs propres et vecteurs propres*
       - On calcule les valeurs propres et les vecteurs propres de la matrice de covariance.  
       - Les valeurs propres mesurent la variance expliquée par chaque composante principale.  
       - Les vecteurs propres (aussi appelés composantes principales) définissent la direction des nouvelles variables.  

    4. *Sélection des composantes principales*
       - On choisit les composantes qui expliquent le plus de variance en regardant le cumul des valeurs propres.  
       - Un critère courant est de conserver assez de composantes pour expliquer 80-90% de la variance.  
       - On peut aussi utiliser le critère du coude, qui consiste à repérer un point où l'ajout d'une nouvelle composante n'apporte plus beaucoup de gain en variance.  

    5. *Projection des données sur les nouvelles composantes*
       - Les données initiales sont transformées dans ce nouvel espace formé par les composantes principales.  
       - Cela permet une visualisation en 2D ou 3D si on conserve seulement 2 ou 3 composantes.  
