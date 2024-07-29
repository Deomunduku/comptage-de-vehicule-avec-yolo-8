## Description

Ce projet implémente le suivi en ligne et en temps réel (SORT) en utilisant des filtres de Kalman pour le suivi des objets détectés (personnes et véhicules) dans une séquence d'images. Il associe des détections d'objets entre des trames consécutives en utilisant le calcul de l'Intersection sur l'Union (IoU) et l'affectation linéaire.
Caractéristiques

   ##  Utilisation de filtres de Kalman pour le suivi des objets
   ##  Association des détections avec les objets suivis via le calcul de l'IoU
   ## Possibilité d'afficher les résultats de suivi en temps réel
   ## Paramètres configurables pour l'âge maximal des pistes, le nombre minimal de coups, et le seuil de l'IoU

### Prérequis

   #### Python 3.x
   #### Numpy
   #### Matplotlib
   #### Scikit-image
   #### FilterPy
   ##### Scipy

##Installation

####Clonez ce dépôt et installez les dépendances requises :
###git clone https://github.com/votre-utilisateur/sort.git
###cd sort
####pip install -r requirements.txt

##Utilisation

Vous pouvez utiliser ce script pour suivre des objets dans des séquences d'images.
Arguments

   ## --display: Affiche les résultats du suivi en ligne (lent) [False]
   ## --seq_path: Chemin vers les détections (défaut: 'data')
  ##  --phase: Sous-répertoire dans seq_path (défaut: 'train')
  ##  --max_age: Nombre maximum de trames pour garder une piste sans détections associées (défaut: 1)
  ##  --min_hits: Nombre minimum de détections associées avant l'initialisation de la piste (défaut: 3)
   ## --iou_threshold: Seuil minimum d'IoU pour l'appariement (défaut: 0.3)

## Illustration des résultats
Exemple de suivi

L'image ci-dessous montre un exemple de suivi d'objets dans une séquence d'images. Les boîtes englobantes colorées représentent les objets détectés et suivis, avec des identifiants uniques pour chaque objet.

![ảnh](https://github.com/user-attachments/assets/1191032b-4dc3-4a47-87d5-ee117f2776b8)

## Visualisation en temps réel

## Si vous utilisez l'option --display, vous pouvez voir une visualisation en temps réel du suivi d'objets. Voici un exemple de ce à quoi cela ressemble :

## Ces visualisations permettent de comprendre comment les objets sont détectés, suivis et comment les trajectoires sont mises à jour dans chaque trame de la séquence vidéo.

##  Fonctionnement

##    Le script charge les détections à partir du chemin spécifié.
##    Il initialise le suivi d'objets en utilisant le filtre de Kalman.
##    Pour chaque trame, il met à jour les positions des objets suivis et crée de nouveaux trackers pour les détections non appariées.
 ##   Les résultats sont sauvegardés dans le dossier output
