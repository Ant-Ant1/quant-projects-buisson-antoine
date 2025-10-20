OPTION PRICING PROJECT — BLACK–SCHOLES & MONTE CARLO

OBJECTIF DU PROJET

Construire un pipeline complet de pricing d’options européennes (call/put) sous hypothèse de mouvement brownien géométrique (GBM).
Comparer deux approches :

Modèle analytique de Black–Scholes

Simulation Monte Carlo sous mesure risque-neutre

Objectifs principaux :

Vérifier la convergence Monte Carlo → Black–Scholes (loi 1/√N)

Étudier la sensibilité à la volatilité, à la maturité et au moneyness

Calculer et interpréter les Greeks (Δ, ν, Θ)

Tester la robustesse, la reproductibilité et la performance du pricer

STRUCTURE DU PROJET

1_INTRODUCTION_&CONTEXT.ipynb : Contexte et objectifs du projet
2_THEORY&_MODEL.ipynb : Modèle GBM et formules Black–Scholes
3_PRICER_SPECIFICATION.ipynb : Spécification fonctionnelle des pricers
4_IMPLEMENTATION_MONTE_CARLO.ipynb : Implémentation BS & MC, campagnes de convergence
5_GREEKS_BLACK_SCHOLES.ipynb : Calcul et visualisation des Greeks
6_COMPARISON_BS_MC.ipynb : Comparaison BS vs MC (prix, erreurs, IC95, moneyness)
7_VALIDATION_QUALITY_REPRODUCIBILITY.ipynb : Tests analytiques, stabilité, multi-seed

Répertoire “figures” : contient toutes les figures générées (F1 à F8)
Répertoire “data” (optionnel) : stockage temporaire des résultats

PRINCIPAUX RÉSULTATS

Convergence Monte Carlo → Black–Scholes vérifiée
Erreur relative suit bien une loi en 1/√N (pente ≈ -0.5 en log–log)

Les erreurs augmentent avec la volatilité et la maturité (σ, T)

Les options ATM présentent les erreurs les plus faibles

Les Greeks respectent les comportements théoriques :
Δ call croît de 0 à 1 ; ν atteint un maximum à la monnaie ; Θ négatif (décroissance temporelle)

La variance du MC reste maîtrisée, IC95 corrects

Tests multi-seed stables (écart < 0.3 %)

Temps d’exécution croît linéairement avec N (bon compromis performance / précision)

FIGURES PRINCIPALES

F1 : Convergence prix_MC → prix_BS (échelle log)
F2 : Erreur relative vs N (pente ~ -0.5)
F3 : Heatmap σ×T des erreurs relatives (ATM)
F4 : Heatmap σ×T des IC95 (ATM)
F5 : Effet du moneyness sur l’erreur relative
F6 : Δ(S) — call et put
F7 : ν(σ) — courbe en cloche
F8 : Θ(T) — décroissance de la valeur temps

CONDITIONS D’EXÉCUTION

Langage : Python 3.12
Librairies : numpy, pandas, scipy, matplotlib, seaborn

Ordre d’exécution recommandé :
1 → 7 (chaque notebook dépend du précédent)
Toutes les figures sont affichées inline, sans écriture automatique sur disque.

Pour relancer le projet :

Activer l’environnement virtuel (.venv)

Installer les dépendances :
pip install numpy==1.26.4 scipy==1.13.1 matplotlib==3.9.2 seaborn==0.13.2 pandas==2.2.3

Exécuter les notebooks dans l’ordre

RÉSUMÉ RAPIDE

Le projet démontre que la méthode Monte Carlo converge efficacement vers les prix de Black–Scholes, tout en illustrant les effets de la volatilité, de la maturité et du moneyness.
Les Greeks confirment la cohérence du modèle théorique, et les tests de validation montrent une excellente stabilité numérique et reproductibilité du pricer.