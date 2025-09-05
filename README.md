# Machine-learning-project

### Home Credit Default Risk

Autori:

Srećko Tasić 2021/0043

Aleksa Rodić 2023/1086

Emir Saračević 2021/0056

# Uvod

Finansijski sektor se suočava sa izazovima procene kreditnog rizika i prepoznavanja klijenata koji verovatno neće otplatiti obaveze. Neredovna otplata ima ozbiljne posledice po banke i tržište, pa je cilj projekta bio razvoj algoritma mašinskog učenja koji na osnovu finansijskih i demografskih podataka predviđa verovatnoću default-a.

Korišćen je Home Credit Default Risk dataset (Kaggle, 2018) sa preko 300.000 aplikacija i velikim brojem numeričkih i kategorijalnih atributa. Poseban izazov je bio problem nebalansiranih klasa (≈8% default).

# Metodologija

Algoritmi:

Logistic Regression

Random Forest

XGBoost

# Tehnike balansiranja:

class_weight=balanced

SMOTE (Synthetic Minority Oversampling)

# Evaluacija: Accuracy, Precision, Recall, F1, ROC-AUC + cost-sensitive funkcija (FN = 100k RSD, FP = 10k RSD).

# Feature engineering: uklanjanje kolona sa >30% nedostajućih vrednosti, eliminacija multikolinearnosti, izdvajanje ~26 ključnih atributa.

# Rezultati

XGBoost (balanced): najniži trošak ≈ 343M RSD na pragu ~0.09 (Recall ≈ 0.60, Precision ≈ 0.17).

Random Forest (balanced): nešto veći trošak (≈348M RSD) ali bolji recall (~0.64).

Logistic Regression: slabija cost-sensitive performansa i manja robusnost.

SMOTE u ovom setup-u povećavao FP i ukupni trošak.

Ukupno, pravilnim tretiranjem nebalansiranosti i optimizacijom praga postignuto je ~30% smanjenje troška u odnosu na primenu algoritama pri neabalnsiranim klasama.

# Zaključak

Ansambl metode (Random Forest, XGBoost) pokazale su se stabilnijim i efikasnijim od linearnih modela za predviđanje kreditnog rizika. Najveće uštede u praksi dolaze od:

tretiranja nebalansiranosti,

optimizacije decision threshold-a prema cost funkciji.
