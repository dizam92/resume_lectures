https://www.nature.com/articles/s41467-017-02465-5.pdf
Données
-------
Multiomiques: SNP, expression hubness, rôle du gène (régulatoire ou pas), CNV, methylation et drugs (medicament) Figure 1B

Objectifs principaux
--------------------
Le rôle de l'algorithme est d'identifier des marqueurs (ou targets) pour des drugs spécifiques. Du coup ils ont un énorme dataset multiomique (mais 30 patients) avec des drugs compounds.
Ils apprennent un score (information à priori) sur l'importance des features entre eux puis ils combinent ce score avec les drugs pour apprendre à découvrir des cibles potentielles.

MERGE ALGORITHM
---------------
1. Inputs
    1. Expression data matrix **X (p genes x n patients)**
    2. Drug response matrix **Y (q drugs x n patients)**
    3. Driver feature matrix **D (p genes x 5 driver features)** Driver features here: expression hubness, candidate regulators, mutation, CNV, Methylation

2. Apprentissage
    1. Apprends un score pour chaque gène (marker potential) modéliser comme une combinaison pondérées des 5 drivers features.
    Ces poids proviennet des données et sont appris par MERGE. Ces poids sont appris de facon à ce que les score obtenus soient les plus explicatifs des associations gènes-drugs: les gènes avec des scores très élevés ont plus tendance à être associés à plusieurs drogues que les gènes avec de faibles scores
    2. Apprentissage des scores: 
            minimize(w_i,j) sum_n (y_j^n - w_i,j * x_i^n)^2 avec **w_i,j** le sine de l'impact du gène i sur la drogue j, **x_i**, les données d'expressions du gène i et **y_i** la mesure de la réponse (AUC) à la drogue j. n patients.

3. Détails dans les figures
![Notes](image1.png)
![Notes](image2.png)