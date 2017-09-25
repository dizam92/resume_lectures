Résumé de [http://colah.github.io/posts/2014-07-NLP-RNNs-Representations/]
--------------------------------------------------------------------------
------------------------------------------------------------------------

Word Embedding
--------------
Calcule une représentation vectoriel des mots et permets par exemple dans le cadre des n-grams de calculer la **perplexité** d'une phrase; de prédire le mot suivant, etc... 
Extrement puissants et marchent très bien.


Shared Representations
----------------------
Ici le but est d'entrainer à **2** tâches différentes et de mapper par la suite dans un espace commun. 
1. Le 1er exemple donner ici: est de faire un **W_en** et un **W_ch** puis de les mapper dans le meme espace de mots. 
On se rend compte que les mots ayant la meme signification (traduction?) dans les 2 langues sont mappés ensemble et par conséquent leur synonyme aussi. 
2. Le 2eme exemple consiste à apprendre à classifier les images à l'aide des textes: i.e associer le mot 'chien' aux images de chien, etc... Ainsi pour une classe inconnue, on veut prédire c'est quoi les images. On remarque que ce modèle à tendance à rapprocher les vecteurs de mots vers des images plus similaires. Par exemple le vecteur du mot 'chat' se retrouvera plus proche dans l'espace des images de 'chien' que des images de voiture ou autre.


Recursive Neuronal Network
--------------------------
Le principe d'encodeur-décodeur pour la traduction est basé largement dessus. 
Le principe ici est de mapper des bouts de séquences progressivement dans une partie du module qui est ensuite mappé dans le meme module.


Résumé de [http://colah.github.io/posts/2015-08-Understanding-LSTMs/]
---------------------------------------------------------------------
---------------------------------------------------------------------

Recurrent Neural Networks
-------------------------
Ce sont des réseaux avec des loops à l'intérieur d'eux meme permettant ainsi la persitance de l'information. 
En gros, il faut penser à la notion de recurrence appliquer à un RN; tout simplement ici. 
Le principal défaut est la mémoire à long terme que les LSTMS viennent combler.


LSTM Networks
-------------
D'habitude les RNN simples auront juste une seule couche (single neural network layer) généralement une seule couche tanh. 
Mais les LSTMs ont une structure particulière qui est constituer de 4 single neural network: **3 gates** et **1 cell state**.

1. **Cell state**: C'est juste un vecteur qui permet à l'information de circuler. Il a 2 interactions spécifiques:
    * Multipliication: Avec le forget gate
    * Addition: Avec le input gate layer

2. **Forget fate layer**: Permet de décider quelle information on jete. Prends h_(t-1) et x_t puis applique une **sigmoid** pour sortir un nombre entre 0 et 1 pour chaque nombre dans la cellule C_(t-1)
    * **f_t = sigma(W_f . [h_(t-1), x_t] = b_f)**
    
3. **input gate layer**: Constituer de 2 parties: 
    * Une sigmoid qui permet de décider quelle valeurs il faut mettre à jour: **i_t = sigma(W_i . [h_(t-1), x_t] + b_i)**
    * Une tanh qui créé le vecteurs des nouvelles valeurs candidates à ajouter à la state cell: **Ĉ_t = tanh(W_C . [h_(t-1), x_t] + b_C)**

4. Il faut par la suite réellement procéder à l'update: **C_t = f_t * C_(t-1) + i_t * Ĉ_t**

5. **Output**: Se fait en 2 étapes également:
    * Sigmoid pour décider quelles parties de C_t on laisse passer: **o_t = sigma(W_o . [h_(t-1), x_t] + b_o))**
    * Tanh pour mettre les valeurs entre -1 et 1: **h_t = o_t * tanh(C_t)**
    
    
GRU(Gated Recurrent Unit)
-------------------------
Il existe plusieurs variantes des LSTMs dont l'une des plus populaires actuellement est le GRU. 

1. Ils combinent l'input et le forget gate en une seule gate **update gate**. 
2. Ils mergent le cell state et le hidden state également.
Ca simplifie les LSTms. 
    

Résumé de [http://colah.github.io/posts/2015-08-Backprop/]
----------------------------------------------------------
----------------------------------------------------------

1. Les réseaux de Neurones peuvent être considérer comme un graphe computationel
2. L'objectif de la descente de la backpropagation est techniquement juste de calculer des dérivées et mettre à jour les poids
3. **Dérivées Partielles**: On Veut savoir à quel point une variable influence le résultat. Si v1 cahnge un peu, à quel point v2 cahnge? 
4. **Forward-mode differentiation** ou **forward propagation** permet de calculer comment une **entrée** (input) affecte chaque noeud
5. **Reverse-mode differentiation** ou **back-propagation** permet d'étudier comment chaque noeud affecte la **sortie**
    * L'avantage de celà est surtout qu'en un coup on a les dérivées partielles par rapport à **tous** les paramètres contrairement à la forward propagation
    

Résumé de [http://colah.github.io/posts/2015-09-NN-Types-FP/]
-------------------------------------------------------------
-------------------------------------------------------------
C'est un article résumé global. Il donne quelques insights particuliers que l'on peut noter comme suit:

1. **Encoding Recurrent Neural Networks**: Ce sont juste des folds (contenants?) qui permettent généralement au réseau de neurones de prendre en entrée des objets de longueurs différentes. Ex: Les phrases
2. **Generating Recurrent Neural Networks**: Ce sont des décodeurs généralement. Beaucoup plus focus sur la sortie. Permettent au réseau de produire une liste en sortie. Ex: produire des mots d'une phrase.
3. **General Recurrent Neural Networks**: On peut voir ca comme un mix des *Encodings* et  *Genereting*. On les utilise souvent pour faire une prédiction dans une séquence. Ex: Dans le voice recognition, on veut pouvoir prédire un phénome à chaque fois qu'il y a un input audio en se basant sur le contexte. 
4. **Bidirectional Recursive Neural Networks**: Voir l'article *NEURAL MACHINE TRANSLATION BY JOINTLY LEARNING TO ALIGN AND TRANSLATE* [https://arxiv.org/pdf/1409.0473.pdf] pour plus de détails. Mais en bref, c'est un GRNN dans les 2 sens permettant de tenir compte du contexte passé et du futur.
5. **Convolutional Neural Networks**: Le principe est d'appliquer une fonction à un ensemble d'éléments dans une fenêtre: on parle de mapping to the neighboring elements. Ceci donne un encoding généralement appelé embedding? Ca marche beaucoup en computer vision. 
6. **Recursive Neural Networks (“TreeNets”)**: une généralisation des folds. Surtout utilisé en NLP, par exemple en analyse syntaxique pour permettre de construire les arbre à partir des mots. Structure bottom up.
