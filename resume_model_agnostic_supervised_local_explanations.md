resume of [http://papers.nips.cc/paper/7518-model-agnostic-supervised-local-explanations.pdf?fbclid=IwAR0w5nJ3bhUMp9ggPo5d2VK80ek25ac8qaOIqpj8DknrhVs-W8tkbqClLZQ]
-------
1. Note importante: il y a 3 types d'interpretabilité
    1. Example based: KNN types of algorithms
    2. local: sparse linear models
    3. global: Series of rules (let's say SCM?)
    
2. Interpretabilité != de Explanation

3. MAPLE (la méthode introduite) est une apporche supervised neighborhood combinant les idées de model linéaire et des arbres de décisions
    1. A chaque example du trianing set, MAPLE attribue un poids qui induit une distribution de probabilité sur l'espace d'entrée
    2. avantage d'être plus accurate que les autres
    3. Détecte des patterns globaux (à défaut d'explication globales) à partir des distributions locales créées
    4. Permet de faire la prédiction et surtout de le faire avec un minimum de justification possible
    5. Senser être meilleur que Lime
    
4. Causal Local Explanation metric: E_x,x'~p_x[loss(exp_x(x'), pred(x'))] sachant que exp_x() = expllainer de x et  pred() est le modèle qu'on veut expliquer.
    1. C'est basé sur le fait de sampler x' sur p_x et encourage les explications généré à x de prédire la valeur du modèle à x'
    
5. Global Explanation as a set of rules that generally hold true for pred() for all or a well defined subset of the input space

6. Example-based Explanation as any function that assigns weights to the training points based on how much influence they have on the predictive model or on an
individual prediction

7. Got to go back on the math side to understand it better and clear