https://www.nature.com/articles/modpathol2010200
Définition de Basal-like
------------------------
2 principales familles d'idées: 1) Détection à partir des expressions (microarray) de certains gènes et 2) Détection à partir des marqueurs immunohistochimiques (ER, PR, HER)
Les marqueurs immunohistochimiques considérés pour déterminés les basal like sont:
1. lack of ER, PR, and HER2 expression (‘triple-negative’ immunophenotype)
2. expression of one or more high-molecular-weight/basal cytokeratins (CK5/6, CK14, and CK17)
3. lack of expression of ER and HER2 in conjunction with expression of CK5/6 and/or epidermal growth factor receptor (EGFR)
4. lack of expression of ER, PR, and HER2 in conjunction with expression of CK5/6 and/or EGFR

Malgré l'absence de conscensus sur leur détermination, il n'en demeurre pas que les patients de ce type présentent un comportement similaire un point de vue clinique.
En gros: les tumeurs basal-like sont un groupe hétérogènes qui représente environ 15% de tous les types de cancers du seins, affecte les patients jeunes, est plus accru dans les populations noires-américaines et est très souvent récurent (interval cancers)


Définition de TNBC
------------------
Ici il n'y a pas de controverse: tout le monde s'accorde à dire que TNBC= Er- & Pr- & Her2-
10-17 % de tous les breast carcinomas. Le gros intérêt pour ce type relève de l'absence de thérapies ciblées pour ce groupe de patients et du fait qu'ils s'overlappent avec les types basal-like. 
Ils présentent des caractéristiques similaires aux types basal-like: patients jeunes(<50ans), population noire-américaine plus à risque, cancer très aggressif: majorité des décès dans les 5 premières années suite à la thérapie.


Synonymes: BL et TNBC
---------------------
NON en gros il ne sont pas similaires meme si: la majeure partie des TNBC ont un phénotype BL et vice versa: la majeure partie des BL sont TNBC. Mot clé ici: majeure partie.
For example, [Bertucci et al](http://onlinelibrary.wiley.com.acces.bibl.ulaval.ca/doi/10.1002/ijc.23518/abstract) showed that only **71% of triple-negative cancers were of basal-like subtype by gene expression profiling** and that only **77% of molecular basal-like tumors were triple-negative**. 
Similar results were observed by de [Ronde et al](https://link-springer-com.acces.bibl.ulaval.ca/article/10.1007%2Fs10549-009-0499-6) and Parker et al (Supplementary Table 1 of [Parker et al](http://ascopubs.org.acces.bibl.ulaval.ca/doi/10.1200/JCO.2008.18.1370)), where **8–29% of triple-negative cancers did not show a basal-like subtype by expression array analysis** and **18–40% of basal-like breast cancers defined by gene expression profiling did not harbor a triple-negative phenotype**. 


Relation entre Basal-Like et BRCA1 mutation
-------------------------------------------
En gros on peut dire que BRCA1-mutation == BL car ils présentent un phénotype BL tel que défini par le IHC.
Importantly, recent studies have demonstrated that BRCA1 gene silencing leads to [downregulation of ER](https://www.ncbi.nlm.nih.gov/pubmed/18000219?dopt=Abstract&holding=npg) and [upregulation of genes considered to be markers of basal-like cancers](https://www.ncbi.nlm.nih.gov/pubmed/19882246?dopt=Abstract&holding=npg) including CK5, CK17, and P-cadherin. 
In contrast, reconstitution of BRCA1 in ER−BRCA1 mutant cell lines has been shown to lead to upregulation of ER and downregulation of CK5, CK17, and P-cadherin.
Taken together, BRCA1 dysfunction appears to be **one of the drivers** of basal-like breast cancers and of a subgroup of triple-negative tumors.

Notes Importantes
-----------------
Les problèmes d'indécisions au niveau du type de cancer sont légions à tous les niveaux:
1. [Up to 25%](https://www.ncbi.nlm.nih.gov/pubmed/19204204?dopt=Abstract&holding=npg) of clinically ER+ tumors are classified as of nonluminal subtype by gene expression methods.
2. Similarly, [nearly a third of the clinically](https://www.ncbi.nlm.nih.gov/pubmed/19204204?dopt=Abstract&holding=npg) HER2+ (FISH and/or IHC) are not classified as belonging to HER2-enriched category.

Conclusions Personnelles et Idées
---------------------------------
Il y aura toujours une marge d'erreurs du au fait que la labelisation n'est pas nécessairement un 'ground truth'. On aura toujours envire *30%* de misclassification naturelle des types de cancer déjà présents dans le dataset. Vu que nos données viennent de la distribution réelle et qu'elles sont déjà biaisées un peu, notre analyse de nos algorithmes doit tenir compte de ces facteurs.
On peut procéder à ceci comme expériences:
1. Après l'analyse de nos résultats, on prend les **FP** et **FN** et on procéde à l'investigation au niveau des gènes ou autres informations complémentaires qu'on peut trouver sur ces patients pour essayer de faire la différence du genre: est-ce vraiment un TNBC ou c'est BL? 
2. Peut on faire cette expérience, combiner le dataset (labelisation) de DIABLO et notre labelisation TNBC, mais etudier la classification des 3 classes? Ou meme juste Basal vs the other et voir parmi les BL quels sont les TNBC bien classifié ou pas? Ca as-tu de l'allure? 
3. Une idée serait aussi de construire un classificateur, pour déterminer qui est BL ou TNBC. Ca aiderait la communauté car vraiment c'est encore compliqué. Ca je pense ca sera une bonne contribution. 

