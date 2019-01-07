Résumé de [https://arxiv.org/pdf/1606.05386.pdf]
------------------------------------------------
------------------------------------------------
1. Faire une grosse différence entre interprétabilité générale et interprétabilité globale
2. Un modèle agnostic est un modèle qui essaye d'expliquer les résultats d'un autre modèle. Ca peut se faire de 2facons suivantes:
    1. Apprendre un modèle interprétable sur les prédictions du modèle blackbox
    2. Shuffle (pertubating) les inputs et voir comment le model balckbox réagit
3. **Local Interpretable Model-agnostic Explanations (LIME)**:
    1. L'objectif de LIME est de trouver un modèle **interprétable** sur la représentation interprétable qui est **localement en accord** avec le classificateur ciblé.
    2. Soit x $\in$ R^d la représentation originale (ex: words embedding), x_prime $\in$ R^d_prime la représentation interprétable(ex: bag of words)
    3. g: R^d_prime --> R est le modèle interprétable que l'on veut apprendre $\omega(g)$ est la mesure de complexité de ce mode (ex: profondeur de l'arbre)
    4. f: R^d --> R est le modèle blackbox complexe que l'on veut expliquer
    5. $\pi_x(z)$ est la mesure de proximité (distance) entre les instance z et x
    6. L(f, g, $\pi_x(z)$) est la fonction de perte que l'on veut minimiser: à quel point g peut approximer f dans la localité définie par $\pi_x(z)$.
    7. *Equation*: argmin_(g $\in$ G) L(f, g, $\pi_x(z)$) + $\omega(g)$
    8. En pratique, on estime la perte en faisant un subsampling autour de x avec f et en évaluant avec les poids de $\pi_x(z)$
    