Resumé de [https://arxiv.org/pdf/1610.09045.pdf]
------------------------------------------------
En gros ils appliquent la réflexion de **LIME** à un problème de précision médecine. 
Leur prédicteur complexe est le **Random Forest**. Un peu ce que je faisais mais là **LIME** va esayer d'expliquer pour **1 patient x** à la fois. 
Ainsi on génère de faux exemples autour de x puis on analyse les prédictions de RF sur eux et par rapport à x. Leur évaluation du test set je ne maitrise pas bien (c'est pas clair: il y a t-il un test set dans le training de RF?)
Très bonne application.