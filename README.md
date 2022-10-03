# Réponses aux question

Les réponses aux question ont été traitées dans le noteboost présent dans le dossier GitHub
Voir [Notebook](https://github.com/jmounal83/Project_equancy/blob/main/Notebook.ipynb)

# Bonus ++ 

Il faut définir les différentes étapes pour mener à bien un projet concernant l'assignation d'un métier à partir d'un CV. 
Le CV est présenté sous différentes mise en page mais sous un format commun à savoir PDF.

# Première étape : Prépartion des données issues des CV 

### Méthode 

Pour traiter un CV reçu il faut le mettre sous la bonne forme.
C'est à dire pouvoir en extraire le texte ainsi que les informations pertinentes afin de créer une observation avec les différents attributs de notre base de données de CV. 
Dans ce cas précis il faut pouvoir identier : 
• L'entreprise actuelle du candidat ou sinon laisser le champs vide
• Le métier du candidat ou laisser le champs vide
• Les technologies maîtriser par le candidat
• Le diplome du candidat
• L'expérience du candidat
• La ville du candidat

### Pistes possibles 

Afin d'extraire le texte du pdf il est possible d'utiliser le module pdftotext.
Il faut après créer différentes fonction afin d'enrichir la dernière entreprise, le métier, le dernier diplôme et la ville du candidat.
Concernant l'expérience il faut voir si nous comptons exclusivement l'expérience pour un métier donné ou l'expérience total. Dans tous les cas il faudra créer une fonction afin de calculer celle-ci
Pour les technologies maitrisé par le candidat, il est nécessaire d'avoir une base des technologies afin de venir vérifier ou non leur présence. Il s'agirait de la méthode la plus simple pour identifier les compétences d'un candidat.

### Points critiques

Il faudrait veiller à prendre en compte le fait que la mise en page est aléatoire, et porter une attention particulière sur les tests. 
Attention aux nombre de technologie que l'on souhaite avoir, un candidat pourrait faire apparaître un grand nombre de technologie. Il faudrait peut-être mettre en place un algorithme plus complexe. 
Ne pas oublier de mettre en place des règles pour venir compléter certaines données manquantes comme les exemples que nous avons vu dans le test.

## Seconde étape : Exploration des données 

### Méthode 

Dans cette phase il s'agit de venir explorer les données, de la même manière que nous l'avons fait à travers les premières questions du test. 
Il faut bien comprendre la nature du problème ainsi que le scope associé. 
Réalisation de graphique pour comprendre la distribution de certaines variables pouvant être utiles pour la sélection des modèles mais aussi pour garder un lien avec le métier sur l'explication des solutions proposées. 

### Pistes possibles 

Utilisation des modules matplotlib et seaborn de python afin de produire des graphes pertinents comme des histogrammes, des boxplots par exemple. 
Identifier les outliers dans les jeux de données et les traiter le cas échéant. 
Regarder le poids des différentes features : matrice de covariance par exemple.
Utiliser des algorithmes de réduction de dimensions peut-être utile pour avoir une meilleur visualisation : PCA par exemple
Réalisation d'encodage pour les variables catégorielles (ex : les métiers dans le cas étudier)

### Points critiques

Comprendre les liens entre les données sans oublier que ces données proviennent de véritables observations. 
Traitement des outliers.
Attention particulière lors des réductions de dimensions si une interprétation est possible ou pas. 


## Troisième étape : Réalisation d'un modèle de machine learning 

### Méthode 

Identifier clairement la problématique ainsi que les objectifs associés. 
S'assurer que la préparation des données à correctement été faite en fonction des algorithmes que l'on va utiliser par la suite. 
Regarder ce qui se fait déjà pour avoir une idée des algorithmes pouvant être utilisé. 
Définir une metric pour pouvoir interpréter le résultat des algorithmes. 

### Pistes possibles 

Créer un set d'entraitement et de test voire une cross validation pour plus de robustesse
Tester différents algorithmes et comparer les résultats.
Jouer sur les hyperparamètres pour améliorer le modèles.
Regarder l'accuracy du modèle afin d'évaluer les performances. 
Réalisation de la courbe ROC et calcul de l'AUC. 

### Points critiques

Attention aux risque d'underfitting et d'overfitting des modèles.
S'assurer que le niveau de complexité ne soit pas trop important si le métier souhaite pouvoir une bonne vision de ce qui est fait. 

## Quatrième étape : Phase de test 

### Méthode 

Dans ce cas la réalisation de test est induite par l'algorithme. 

### Pistes possibles 



### Points critiques



## Cinquième étape : Mise en production 

### Méthode 

Réaliser la mise en production de l'outil crée.
Il faut définir avec le métier comment il souhaite pouvoir y avoir accès. 
Mettre au propre le code afin qu'une autre personne puisse facilement intervenir dessus en cas de problème ou de souhait de faire un v2. 
Création de toute la documentation associé au projet à la fois technique mais aussi fonctionnelle. 

### Pistes possibles 

Un moyen simple serait de créer une API Flask.
L'API pourrait être déployée au sein de Kubernetes.
Créer les bases de données de ce projet via Big Query par exemple.
Assurer la disponibilité du modèle via Google Storage par exemple.


### Points critiques

Le code pourrait être difficillement relu par une personne n'ayant pas participé au projet.
La documentation pourrait ne pas être claire.
L'application ne doit pas consommer trop de ressources pour fonctionner.
