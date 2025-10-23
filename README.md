💵 Détection de faux billets grâce au Machine Learning
🧠 Contexte du projet

La lutte contre la contrefaçon monétaire est un enjeu majeur pour la stabilité économique.
Dans ce cadre, une étude a été menée pour déterminer automatiquement si un billet est vrai ou faux à partir de mesures physiques précises : diagonale, longueurs, marges et hauteurs.

L’objectif était de concevoir un modèle de Machine Learning capable d’analyser les caractéristiques d’un billet et d’en prédire l’authenticité.

J’ai été mandaté en tant que Data Analyst pour réaliser cette étude et construire une solution automatisée fiable et explicable.

🎯 Objectifs du projet

Développer plusieurs modèles d’apprentissage supervisés et non supervisés.

Comparer leurs performances prédictives afin d’identifier le plus performant.

Mettre en place un modèle final capable de prédire, sur de nouvelles données (billets_production.csv), si un billet est vrai ou faux.

Fournir une analyse claire et documentée du processus et des résultats.

🧩 Données utilisées

Le projet s’appuie sur deux fichiers :

billets.csv : jeu d’entraînement principal contenant les caractéristiques des billets.

billets_production.csv : jeu de production envoyé pour évaluation finale du modèle.

Variables principales :
Variable	Description
diagonal	Diagonale du billet
height_left	Hauteur à gauche
height_right	Hauteur à droite
margin_low	Marge inférieure
margin_up	Marge supérieure
length	Longueur totale
is_genuine	0 = billet vrai / 1 = billet faux
🧠 Méthodologie
🔹 Préparation et analyse des données

Vérification des valeurs manquantes

Tests statistiques :

D’Agostino (normalité des résidus)

Ramsey RESET (linéarité du modèle)

Breusch–Pagan (homoscédasticité des erreurs)

Imputation des valeurs manquantes (médiane) au lieu de la suppression

Normalisation des données avant modélisation

🔹 Modélisation

Quatre algorithmes ont été testés :

Algorithme	Type	Objectif
K-Means	Non supervisé	Regrouper les billets selon leurs similarités
KNN (K-Nearest Neighbors)	Supervisé	Classer un billet selon ses plus proches voisins
Régression logistique	Supervisé	Estimer la probabilité qu’un billet soit faux
Random Forest	Supervisé	Agréger plusieurs arbres pour une meilleure précision
🔹 Validation et comparaison

Validation croisée 80/20 pour évaluer la robustesse des modèles

Comparaison selon :

Accuracy

Précision

Rappel

F1-score

AUC (aire sous la courbe ROC)

📊 Résultats et enseignements
Modèle	Accuracy	Recall (faux)	F1-score
K-Means	0.99	0.97	0.98
KNN	0.97	0.94	0.95
Régression Logistique	0.99	0.98	0.99
Random Forest	0.98	0.96	0.97

👉 La régression logistique est retenue :

Excellente performance (équilibre précision / rappel)

Interprétabilité des coefficients

Rapidité et simplicité de déploiement

🧮 Utilisation du modèle de production

Lors de la phase finale, le fichier billets_production.csv est importé dans un notebook dédié.
Le modèle de régression logistique y est réentraîné sur le jeu complet (billets.csv),
puis utilisé pour prédire l’authenticité des nouveaux billets.

📋 Le résultat final est un tableau listant chaque billet et son statut :
“Vrai” ou “Faux”, selon la probabilité prédite par le modèle.

🧰 Outils utilisés

Python

pandas, numpy (nettoyage et analyse)

matplotlib, seaborn (visualisation)

scikit-learn (modélisation et évaluation)

Jupyter Notebook pour la documentation et la reproductibilité

🧑‍💻 Compétences démontrées

Analyse exploratoire et statistique des données

Application de plusieurs algorithmes de Machine Learning

Validation croisée et évaluation de modèles

Data storytelling (interprétation claire des résultats)

Automatisation de la prédiction sur un jeu de production

📎 Livrables

Notebook Jupyter complet (analyse_faux_billets.ipynb)

Notebook de production (prediction_billets_production.ipynb)

Rapport synthétique de comparaison des modèles

README explicatif du projet

👤 Auteur

David Fernandes
Data Analyst — OpenClassrooms
