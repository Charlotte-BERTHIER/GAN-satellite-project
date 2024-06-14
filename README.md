![petit_gif_pour_le_fun](image_readme/entrainement.gif)

# __Discrimination par un classifieur YOLO de fausses images satellites générées par un cGAN pix2pix__

GitHub contenant les données, notebooks et le rapport associés au projet 1 : GAN image, réalisé dans le cadre du cours Python (enseignant [Chahan Vidal-Gorène ](http://cv.hal.science/chahan-vidal-gorene)) du [Master Humanités Numériques de l'ENC ](https://www.chartes.psl.eu/fr/rubrique-admissions/master-humanites-numeriques).


# __Pipeline du projet__

Chaîne de traitement (ou _pipeline_) implémentée au cours du projet.

![pipeline_projet](image_readme/pipeline.png)


# __Résumé__

Notre projet portait sur la génération d’images, ainsi que sur la classification des images. Il questionnait les éléments sur lesquels se concentre un réseau de neurones pour réaliser une classification d’images.

Dans ce cadre, nous avons mis à l’épreuve un réseau de neurones YOLO en lui soumettant de vraies images satellites et de fausses images satellites, générées avec le réseau antagoniste génératif sous contrainte (cGAN) Pix2Pix. Nous avons ensuite extrait et analysé les features du réseau, pour comprendre ce sur quoi la convolution s’appuie pour distinguer le vrai du faux.



# Contenu du dépôt
- `scripts/` : dossier contenant les notebooks utilisés pour mener à bien le projet
  - `preprocessing.ipynb`: notebook contenant les étapes de pré-traitement (découpage et nettoyage) des données IGN. Les données brutes de l'IGN étaient trop lourdes pour être sur le GitHub, le dataset disponible ici a été produit en utilisant ce notebook en local.
  - `Pix2pix_data_satellite.ipynb`: notebook contenant la préparation du corpus pour le GAN ainsi que l'entraînement de pix2pix.
  - `classification_supervisee_YOLO.ipynb`: notebook contenant la classification par YOLO des images vraies et fausses ainsi que les méthodes de compréhension des _features_. 
  
- `data/` : dossier contenant les données du projet
  - `dataset_double/`: dossier contenant le corpus pré-traité
  - `GAN/`: dossier contenant les données utiles pour la réalisation du GAN
    - `log/`: dossier contenant les résultats du dernier entraînement, utilisé pour l'analyse.
    - `predicted_images_106_val/` : dossier contenant les images générées à partir des masques des images de validation du GAN.
    - `predicted_images_106_test/` : dossier contenant les images générées à partir des masques des images de test du GAN.
  - `yolo/` : dossier contenant les données nécessaire à la réalisation de la classification.
    - `vrai/` : dossier contenant les images vraies.
    - `faux/` : dossier contenant les images fausses.
    - `occlusion/`: dossier contenant des images produites avec la méthode de l'occlusion pour essayer de voir les zones discriminantes des images.
  - `runs/`: dossier contenant les résultats des entraînements YOLO.

- `image_readme/` : images utilisées dans le README.md
- `rapport.pdf` : Rendu contenant les explications sur la méthode utilisée et les résultats.


# Auteurs
Ce projet a été réalisé par :

- Lise Bernard
- Charlotte Berthier
- Axelle Salvador
- Albina Toumarkine
