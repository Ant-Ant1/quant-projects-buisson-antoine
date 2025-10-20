# Forecasting Market Volatility with Statistical & Deep Learning Models

## 🎯 Introduction
La volatilité est un indicateur central en finance de marché : elle influence la valorisation des options, le risk management et la construction de portefeuilles.  
L’objectif de ce projet est de prédire la volatilité du S&P 500 en comparant des modèles classiques (EWM, GARCH, HAR-RV) et des modèles avancés (LSTM), puis d’évaluer la valeur ajoutée de ces prévisions dans un backtest d’options.

---

## 📂 Structure du projet
Le projet est organisé en notebooks successifs :  

1. 1_COLLECT_DATA.ipynb – Collecte des données (SPX, SPY, VIX via Yahoo Finance).  
2. 2_PROCESS_DATA.ipynb – Prétraitement : rendements, volatilité réalisée, features.  
3. 3_GARCH_VS_EWM.ipynb – Comparaison GARCH vs Exponentially Weighted Moving.  
4. 4_EGARCH_GJR-GARCH_VS_EWM.ipynb – Tests EGARCH et GJR-GARCH.  
5. 5_DIEBOLD–MARIANO_TEST_(GARCH_VS_EWM).ipynb – Test statistique Diebold–Mariano.  
6. 6_LSTM_PREVISION.ipynb – Modèles LSTM pour prévision de volatilité.  
7. 7_HAR-RV_PREVISION.ipynb – Modèle HAR-RV (Heterogeneous AutoRegressive).  
8. 8_DIEBOLD–MARIANO_LSTM_VS_HAR_VS_EWM.ipynb – Comparaison des approches avancées.  
9. 9_BACKTEST_OPTION.ipynb – Backtest d’options (straddles ATM, delta-hedging).  

---

## 🔧 Installation & dépendances
### Prérequis
- Python >= 3.10  
- Git  

### Installation
git clone <url-du-repo>
cd <nom-du-repo>
pip install -r requirements.txt


### Librairies principales
- pandas, numpy, matplotlib, seaborn  
- yfinance (collecte données)  
- arch (GARCH, EGARCH, GJR)  
- scipy (tests statistiques)  
- torch (LSTM)  

---

## 📊 Méthodologie
1. Collecte – Données historiques SPX, SPY et VIX.  
2. Prétraitement – Calcul des rendements, volatilité réalisée (21 jours), features (lags, log-vol).  
3. Modèles statistiques – EWM, GARCH, EGARCH, GJR-GARCH, HAR-RV.  
4. Deep Learning – LSTM basique vs LSTM enrichi (features multiples).  
5. Évaluation statistique – MAE, RMSE, Diebold–Mariano tests.  
6. Backtest d’options – Straddles ATM (~21 jours), couverture delta quotidienne, PnL normalisé.  

---

## 📈 Résultats clés
- Horizon J+1 : EWM (λ=0.94) et HAR-RV restent très difficiles à battre.  
- Horizon 5 jours : LSTM enrichi et un Blend LSTM+EWM offrent des prévisions plus précises.  
- Backtest options : LSTM/Blend génèrent des PnL supérieurs sur straddles ATM, confirmant leur avantage économique.  

---

## ⚠️ Limites
- Pas de coûts de transaction intégrés au backtest.  
- Modèle Black–Scholes utilisé sans surface de volatilité implicite.  
- Risque de surapprentissage des LSTM.  

---

## 🚀 Perspectives
- Intégrer coûts de transaction et dividendes (SPY) pour un backtest plus réaliste.  
- Ajouter des features exogènes (VIX term-structure, variables macro).  
- Tester des architectures avancées (Transformers temporels).  
- Évaluer la calibration via Mincer–Zarnowitz et Model Confidence Set.  

---

## 📜 Licence
Projet open-source – Licence à définir (MIT recommandé).  


