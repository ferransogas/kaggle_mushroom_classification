# Mushroom Classification
L'objectiu d'aquest projecte era desenvolupar un model predictiu capaç de classificar bolets en dues categories: comestibles (edible) o verinosos (poisonous), basant-se en les seves característiques físiques (color, forma, olor, etc.). Es va treballar amb el dataset de 8.124 mostres i 23 atributs categòrics de [Kaggle - Mushroom Classification](https://www.kaggle.com/datasets/uciml/mushroom-classification).

## Metodologia Aplicada
El flux de treball va seguir els passos següents:
- Anàlisi Exploratòria de Dades (EDA):
  - Es va verificar que el dataset estava equilibrat i sense valors nuls.
  - Es van analitzar les distribucions de les variables, destacant l'olor com un discriminant molt potent.
- Preprocessament:
  - Com que totes les dades eren categòriques, es va aplicar Label Encoding per transformar les variables en format numèric apte per als algorismes.
- Selecció de Models:
  - Es van entrenar i comparar quatre algorismes diferents: Regressió Logística, Naive Bayes, Random Forest i XGBoost.
- Optimització i Eficiència:
  - Es va comparar l'eficiència computacional entre els dos millors models (Random Forest vs XGBoost).
  - Es va realitzar un ajust d'hiperparàmetres (Tuning) sobre XGBoost utilitzant RandomizedSearchCV per reduir la complexitat del model mantenint el rendiment.
- Validació:
  - Es va aplicar Stratified K-Fold Cross-Validation (10 particions) per assegurar la robustesa dels resultats.

## Resultats
Els models basats en arbres de decisió van presentar un rendiment superior, aconseguint el 100% de precisió. La Regressió Logística va arribar al ~95%, i Naive Bayes al ~92%.

## Conclusions Clau
1. Les dades mostren que la classificació de bolets en aquest dataset segueix regles clares. No hi ha ambigüitat: el model pot aprendre a classificar-los sense error.
2. XGBoost és la millor opció. A més, després del tuning, és extremadament lleuger i ràpid.
3. Els indicadors principals per detectar toxicitat són:
    - Color de les làmines (Gill-color).
    - Olor (Odor).
    - Població (Population).
