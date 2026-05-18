# Coût de l'acier importé et prix des véhicules neufs aux États-Unis (1981 - 2024)

Ce dépôt contient le projet d'analyse macroéconométrique et de modélisation de séries temporelles réalisé dans le cadre du Master d'Économie Appliquée. L'étude explore la dynamique de transmission des coûts des matières premières importées (l'acier) sur les prix à la consommation d'un secteur industriel clé aux États-Unis (l'automobile).

## Présentation du Projet
L'objectif est d'évaluer empiriquement l'impact d'un renchérissement de l'acier importé sur l'Indice des Prix à la Consommation (IPC) des véhicules neufs aux USA sur une période de plus de 40 ans, caractérisée par d'importantes mutations industrielles et des cycles de tensions commerciales.

### Données & Variables
Les données proviennent principalement de la **FRED (Federal Reserve Bank of St. Louis)** et du **U.S. Bureau of Labor Statistics (BLS)** à fréquence mensuelle de 1981 à 2024 :
* **IPC (Consumer Price Index) :** Prix des véhicules particuliers neufs aux États-Unis.
* **IPI (Import Price Index) :** Prix des importations américaines de fer et d'acier.

## Méthodologie Économétrique
Le projet met en œuvre une démarche rigoureuse de modélisation Box-Jenkins, d'analyse de co-intégration et de modèles multivariés :

1. **Analyse de stationnarité :** * Représentation graphique et étude des fonctions d'autocorrélation (ACF/PACF).
   * Tests de racine unitaire (**ADF** - Augmented Dickey-Fuller, **PP** - Phillips-Perron et **KPSS**).
   * Différenciation et méthodes de stationnarisation des processus non stationnaires.
2. **Modélisation Univariée (ARMA) :**
   * Identification des retards optimaux ($p, q$) pour l'IPC des véhicules.
   * Estimation des coefficients, analyse des racines inversibles et tests de blancheur des résidus (Test de Ljung-Box, ARCH).
3. **Prévisions & Recoloration :**
   * Prévisions hors-échantillon du processus filtré et recoloration pour revenir à la série initiale (IPI Acier).
4. **Modélisation Multivariée (VAR) & Analyse de Causalité :**
   * Estimation d'un modèle Vectoriel Autorégressif (**VAR**).
   * **Test de causalité au sens de Granger** pour valider l'impact prédictif du prix de l'acier sur l'automobile.
   * Fonctions de réponse impulsionnelle (**IRF**) et projections locales pour mesurer le délai de diffusion du choc d'offre.

## Outils & Technologies
* **Langage :** R / RStudio
* **Librairies R clés :** `urca` (tests de racine unitaire), `tseries`, `vars` (modèles VAR et causalité), `forecast` (modélisation ARMA et prévisions), `ggplot2` (visualisation des séries et des IRF).

## Principaux Résultats
* **Absence d'instantanéité :** Les tests de causalité de Granger et les fonctions d'impulsion-réponse corroborent l'existence d'une transmission du prix de l'acier importé vers le prix des véhicules neufs, mais mettent en évidence un **délai de diffusion** (effet non immédiat).
* **Perspectives macro-commerciales :** L'étude pose les bases méthodologiques pour analyser à l'avenir les chocs tarifaires récents et les barrières douanières sur les métaux.
