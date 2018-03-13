Resume of [http://papers.nips.cc/paper/7062-a-unified-approach-to-interpreting-model-predictions.pdf]
----------------------
Definition: Additive feature attribution
----------
Le modele explicatif est une fonction linéaire dépendante de variables binaires:
g(z_prime) = phi_0 + sum_i=1^M phi_i * z_prime_i avec z_prime \in {0,1}^M, M la taille de la dimension interpretable (input features) et phi_i \in R.

Différentes méthodes
--------------------
Lime/ DeepLIFT/ Classic Shapley Value Estimation

Propriétés uniques des modeèls agnostic
----
1. Accuracy locale: f(x) = g(x_prime)
2. L'absence: Si l'espace d'entrée représente la présence d'un feature donc l'absence  du feature dans l'espace original des inputs ne doit avoir aucun impact: x_prime_i = 0 ==> phi_i = 0
3. Consistance: Qelque soit le modele l'importance du feature ne devrait pas changer

SHAP
----
**To be completed**