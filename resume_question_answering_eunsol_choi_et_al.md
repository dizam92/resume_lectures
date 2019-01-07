Généralités
-----------
Très bon article sur le Question-Answering. 
Ils développent une méthode qu'il dénomme **Hierarchical QA** dans le sens que le modèle prend:
1. Les **Query** et le **document**
2. Fait une sélection de phrase à partir de laquelle un **document summary** est fait
3. Les **Query** et **Résumé** sont passés dans un **RNN** pour générer la réponse **y**

Description mathématique du framework
-------------------------------------
Soit **s**, une phrase, **x** une question et **d** un document. 
Partie 1: Sélection de phrases
------------------------------
Objectif: p(s | x, d)
Un feedforward neuronal network a été construit pour ca. 
Ils considèrent 3 représentations principales des phrases: 

1. **Bag of Words (BOW)**: Mecanisme d'attention standar utilisé, le tric ici est de combiner le **BoW(s)** et le **BoW(x)**.
    * h_l = [BoW(x), BoW(sl)]
    * v_l = v^T RELU(Whl)
    * p(s = s_l | x, d) = softmax(v_l)

2. **Chunking model**: Meme modèle que le précédent juste que chaque phrase est décomposé en un nombre fixe de chunk (ou section) ==7 ici.
La probabilité est donc apprise sur les chunk maintenant.

3. **Convolutional model (Parallelizable)**: Après avoir concaténé les embeddings des questions et phrases, appliquer un filtre de convolution avec F features et une largeur w.

Partie 2: Construction du résumé
--------------------------------
Deux facons de faire: 
1. **Hard Attention**: classic 
2. **Soft Attention**: encore un peu flou pour moi

Partie 3: Générer les réponses
------------------------------
Utilise le modèle généré par Hewlett et al (2016) qui est basé sur un **Encodeur GRU** qui encode les questions et le document , et un **Décodeur GRU** qui s'occupe d'inférer le **p(y | x, d)**.

