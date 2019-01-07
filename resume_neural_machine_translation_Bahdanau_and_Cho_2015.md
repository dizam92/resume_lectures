Très bonne introduction et utilisation au **BRNN**.
L'article introduit bien comment l'état de l'art fonctionne dans le cadre de la traduction des phrases, 
i.e que l'encodeur transforme la phrase de la lanque première en un un vecteur de taille fixe, quelque soit la longueur de la phrase. 
Puis le décodeur s'occupe de décoder dans la langue cible.
Ici, ils présentent une structure basée sur le meme principe mais au lieu de compresser toutes les phrases en un vecteur de taille fixe, 
ce vecteur est appris par le RN pour chaque phrase. Il est constitué par une fonction qui utilise les mecanismes d'attention afin de 
souligner les mots les plus intereliés dans la phrase source afin d'assurer une meilleur traducion par le décodeur. 