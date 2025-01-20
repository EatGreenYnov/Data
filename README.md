# README - Partie Data

Ce projet vise à analyser et prédire les émissions de carbone liées aux achats alimentaires en utilisant des données de tickets de caisse. Cette section décrit les étapes de traitement et d'analyse des données, ainsi que les scénarios simulés pour réduire l'impact environnemental.

## Structure des Données
Le fichier de données principal est :
- **`tickets_caisse_dated_30_articles.csv`** : Contient les détails des tickets de caisse, avec les colonnes suivantes :
  - `Date` : La date de l'achat.
  - `Produit` : Le nom de l'article acheté.
  - `Quantité (kg)` : La quantité achetée en kilogrammes.
  - `Prix au kg (€)` : Le prix unitaire par kilogramme.
  - `Total_CO2` : Les émissions de carbone associées au produit (g CO₂/kg).

## Étapes de Traitement des Données
1. **Chargement et exploration des données** :
   - Les données sont chargées avec pandas, et un aperçu des colonnes est fourni pour vérifier la structure.

2. **Agrégation des émissions carbone par jour** :
   - Les émissions totales quotidiennes sont calculées en sommant les émissions de chaque produit par date.
   - Résultat : Une table agrégée avec les colonnes `ds` (date) et `y` (émissions totales).

3. **Visualisation initiale** :
   - Un graphique est tracé pour observer l'évolution des émissions carbone quotidiennes au fil du temps.

## Modélisation avec Prophet
### Scénario 1 : Habitudes actuelles
- Le modèle Prophet est utilisé pour prédire les émissions carbone sur une période de 90 jours en extrapolant les tendances actuelles.

### Scénario 2 : Réduction de 20 % des achats de viande
- Les produits carnés (`Bœuf`, `Porc`, `Poulet`, `Agneau`) voient leurs quantités réduites de 20 %.
- Une nouvelle table est calculée pour simuler cette réduction, et un modèle Prophet est entraîné sur ces données modifiées.

## Visualisations et Comparaisons
1. **Prévisions des scénarios** :
   - Graphiques distincts montrent les émissions prévues pour chaque scénario (habitudes actuelles et réduction de viande).
2. **Comparaison interactive** :
   - Un graphique juxtapose les deux scénarios pour mettre en évidence les différences.

## Résultats et Exportation
- Les prévisions sont enregistrées dans deux fichiers CSV :
  - `predictions_habitudes_actuelles.csv`
  - `predictions_reduction_viandes.csv`
- Ces fichiers contiennent les colonnes :
  - `ds` : La date.
  - `yhat` : Les émissions carbone prévues.
  - `Scenario` : Le scénario correspondant.

## Dépendances
- **Python** : Version 3.7+
- Librairies :
  - `pandas`
  - `matplotlib`
  - `prophet`

---
Pour exécuter les scripts, assurez-vous que les dépendances sont installées et que le fichier de données est présent dans le répertoire racine du projet.

