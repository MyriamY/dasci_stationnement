# dasci_stationnement

Résumé et explication détaillée de la compétition data
Contexte+
Cette compétition est organisée par Egis, un groupe international spécialisé dans le conseil, l’ingénierie et l’exploitation, intervenant dans divers domaines tels que les infrastructures, l’énergie, et l’environnement. En collaboration avec datacraft, une communauté de data scientists et data ingénieurs, l’objectif de cette compétition est d’utiliser des techniques de Machine Learning pour optimiser le contrôle du stationnement sur voirie.
Objectif de la compétition
Egis exploite un système de contrôle du stationnement basé sur des véhicules équipés de caméras, qui prennent des photos des véhicules en stationnement. À partir des informations recueillies (plaque d’immatriculation, localisation, horodatage), un processus de vérification est initié pour détecter d’éventuelles infractions et, si nécessaire, émettre un forfait post-stationnement (FPS).
L’enjeu est de :
Prédire les zones et horaires où le taux d’infraction est le plus élevé pour optimiser le positionnement des véhicules de contrôle (scan cars).
Optimiser le déploiement des véhicules de contrôle afin de mieux répartir les ressources et améliorer l’efficacité du système.
Réduire le taux d’infraction constaté, en améliorant la couverture des contrôles.
En France, chaque place de stationnement payant doit être contrôlée en moyenne deux fois par jour, ce qui souligne l'importance d'une planification efficace.
Description des données
Les données disponibles comprennent :	
Latitude et longitude : Indiquant la position de la zone contrôlée.
Horodatage : Échantillonné à l’heure, indiquant le moment du contrôle.
Taux d’infraction constaté : Mesurant le pourcentage de véhicules en infraction dans la zone concernée sur une période donnée.
Données externes : Conditions météorologiques (issues de Météo France, en open data), qui peuvent influencer le taux d’infraction (ex. : une forte pluie peut réduire les contrôles ou modifier les habitudes de stationnement).
Approche et méthodologie
Le problème est traité comme une tâche de régression, où l’objectif est de prédire le taux d’infraction futur en fonction des données historiques et des facteurs externes.
Critère d’évaluation : la corrélation de Spearman
Cette métrique permet de mesurer la relation entre les prédictions du modèle et la réalité.
L’intérêt principal est de classer correctement les zones en fonction de leur taux d’infraction, pour que les véhicules de contrôle puissent être dirigés vers les zones les plus problématiques.
Benchmark et défis du challenge
Un modèle Random Forest a été utilisé comme benchmark.
Entraîné sur des zones avec au moins 45 véhicules stationnés pour éviter les biais dus aux petits échantillons.
Il atteint une corrélation de Spearman de 0.197, ce qui laisse une marge d’amélioration importante.
Un des défis majeurs est de regrouper ou filtrer les zones intelligemment pour améliorer la pertinence des mesures et réduire la taille des données à traiter.
Conclusion
Cette compétition permet aux participants de proposer des modèles de Machine Learning innovants pour améliorer l’efficacité du contrôle du stationnement. En optimisant les trajets des véhicules de contrôle, on peut réduire le nombre d’infractions et améliorer la gestion du stationnement en ville. Les défis principaux résident dans la gestion des volumes de données, la sélection des features pertinentes et l’amélioration de la corrélation du modèle.
