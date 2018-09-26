Résumé de [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5759031/pdf/pr7b00595.pdf]
------------------------

1. Bonne introduction et référence à l'état de l'art. Ils mentionnent les articles suivant qui sont importants à lire je pense:
    1. [https://genome.cshlp.org/content/early/2016/06/10/gr.200535.115.abstract]
    2. [https://academic.oup.com/bioinformatics/article/32/12/1832/1743989]
    3. [https://www.worldscientific.com/doi/abs/10.1142/9789814644730_0014]
    4. [http://clincancerres.aacrjournals.org/content/early/2017/10/05/1078-0432.CCR-17-0853]
    
2. Datasets (disponibles): 
    1. **271 breast cancer samples (204 ER+ and 67 ER−)** provenant de: [https://www-sciencedirect-com.acces.bibl.ulaval.ca/science/article/pii/S1874391913005113#s0010] Ref 19 in this article
        1. Les supplémentary data de cet article nous donne les détails (peut meme etre réutilisé pour du TN car les labels sont availables)
        2. **162 metabolites** with known chemical structure were measured using gas chromatography
    2. **154 samples 122 ER+ and 32 ER− genes expression**, a subset of the 271 samplesGSE59198 (code d'accès GEO). A total of **15 927 genes** were detected (p < 0.01) in at least 10% of the samples after applying spline normalization
    3. Data Preprocessing: KNN hod to impute missing metabolomics data. And QUantile normalization x_chap_ij = (log_2(x_ij) - x_moy_i)/ s
    
    
3. Model:
    1. Preprocessing
    2. Autoencoder Pretraining (on all the data)
    3. Training and testing
    4. Performance Comparison
    
4. Features extraction and compararison between the metabolite and the gene. A noté qu'ils ont pas utilisé les genes d'expression pour apprendre. C'est juste ppour faire l'inférence biologique et les pathways et utiliser les outils biologiques qu'ils sont utilisés.

5. Résultats: Trouve des biomarqueurs déjà correlés au BRCA. Un nouvel mécanisme (pathway) entre _ beta-alanine_ et _ FOXM1 transcription factor network pathway_

