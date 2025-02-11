# Challenge Data Science - Optimisation du Contrôle du Stationnement

Bienvenue dans le répertoire du challenge de data science pour l'optimisation du contrôle du stationnement, développé en collaboration avec Egis et Datacraft. Ce projet a pour objectif d'analyser et d'optimiser l'exploitation des contrôles de stationnement sur voirie dans plusieurs villes, en France et à l'international.

Voici le lien de la compétition : https://challengedata.ens.fr/challenges/163

## Contexte

Egis est un groupe international de conseil, d'ingénierie et d'exploitation, présent dans plus de 100 pays, intervenant dans divers secteurs tels que les infrastructures de transport, le bâtiment, l'eau, l'environnement et l'énergie.

Dans le cadre de ce projet, nous avons travaillé sur des données relatives au contrôle du stationnement sur voirie, récoltées par des véhicules équipés de caméras. Ces véhicules capturent des images des plaques d'immatriculation des voitures stationnées et, avec les données de géolocalisation et d'horodatage, le système vérifie la validité du stationnement.

### Objectif du Challenge

L'objectif principal du challenge est de :
1. Analyser les données de stationnement afin d'identifier les zones et horaires avec le plus grand nombre d'infractions.
2. Optimiser les trajets des véhicules de contrôle du stationnement en fonction des zones à forte densité d'infractions.
3. Prévoir les taux d'infractions en tenant compte de l'historique et des conditions externes comme la météo.

### Métrique

La performance des modèles sera mesurée à l'aide de la **corrélation de Spearman**, car la priorité métier est de déterminer les zones les plus susceptibles de présenter des infractions, afin de mieux planifier les contrôles.

## Structure du Projet

### 1. **Données**
Les données utilisées dans ce challenge comprennent :
- **Latitude et Longitude** des zones géographiques où les contrôles ont eu lieu.
- **Horodatage** des contrôles.
- **Taux d'infraction** observé entre l'horodatage actuel et le suivant.

Des données externes, comme les **conditions météorologiques** (provenant de Météo France), ont également été intégrées pour enrichir l'analyse et la prédiction des infractions.

### 2. **Traitement des Données**
Les données ont été traitées pour :
- Supprimer les points de données trop éloignés de Paris afin d'éviter que des points aberrants n'influencent les résultats (par exemple, à l'aide de la formule de distance haversine).
- Normaliser les données de géolocalisation pour les adapter à une échelle de calcul commune.
- Manipuler et prétraiter les données pour en extraire les caractéristiques pertinentes à la modélisation.

### 3. **Modélisation**
Des modèles de machine learning ont été utilisés pour prédire les taux d'infractions en fonction des variables d'entrée, y compris les conditions météorologiques. Le modèle de **RandomForest** a été utilisé comme base pour le benchmark, avec un objectif d'amélioration de la corrélation de Spearman.

### 4. **Optimisation des Trajets**
En plus de la prédiction des zones à risque, une approche a été mise en place pour optimiser les trajets des véhicules de contrôle du stationnement en fonction des résultats de prédiction.

## Installation

1. Clonez ce repository :
   ```bash
   git clone https://github.com/votre-utilisateur/optimisation-stationnement.git
