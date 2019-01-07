Resumé de [https://arxiv.org/pdf/1708.07136.pdf]
------------------------------------------------

Mise en contexte (related work)
-------------------------------
1. Lire les articles [https://bmcbioinformatics.biomedcentral.com/track/pdf/10.1186/s12859-015-0857-9] et [https://academic.oup.com/bib/article/17/4/628/2240645] pour le travail passé effectué sur l'intégration des omiques
2. Toutes les techniques d'intégration peuvent être classifiées en **4 groupes** basés sur le fait qu'ils soient **probabilistique** ou **graphes (network based)**:
    1. **Non-Probabilistic Non-Network**, Aucune assomption n'est faite sur la distribution de probabilité! N'utilise pas non plus la théoroe des  graphes pour l'intégration. On applique directement de la regression ou de l'anayse de correlation au dataset multi-omique. Exemple: Partial Least square/ Canonical Correlation Analysi. Certains cas emploient aussi des techniques d'*Expectation-
Maximization* pour apprendre les poids de chaque soucre dans l'optimization du framework.

    2. **Non-Network Probabilistic**, englobent toutes les méthodes qui utilisent une approche probalisitique contenant des variables latentes avec un prior sur la distribution. Exemples: _iCLuster_ utilisé pour le clustering des cancers en sous-types. Apprends des variables latentes par E-M puis applique le clustering sur ces variables latentes.
    
    3. **Non-Probabilistic Network**, pas de prior sur la distribution d'un set de variables latentes. Utilisent généralement les graphes d'interactions pour transmettre le signal et susionner différents graphes. Exemples: _HotNet2_ diffuse les signaux de mutations génétiques à travers les graphes d'interactions de gènes. On dérive de ces graphes des _hot spot_ de gènes causant potentiellement la maladie et _SNF_ construit des graphes de similarité entre patients en utilisant différents types de données. L'objectif est de construire un graphe de similarité faisant un conscencus entre les patients.
    
    4. **Probabilistic Network**, utilisent des approches bayésiennes qui incorporrent des variables latentes et les facteurs à travers des frameworks d'optimisation. Plusieurs sources externes telles ques les graphes d'interactions ou pathways sont utilisés pour construire le graphe. Exemples: PARADIGM 
    
Methode introduite: ANF
-----------------------
1. Ils s'inscrivent dans une vision clustering essentiellement
2. Feature engenieering
3. Distance Metrics: Coefficient de correlation de pearson
4. 