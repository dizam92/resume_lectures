Résumé de [https://www.biorxiv.org/content/biorxiv/early/2018/04/02/259911.full.pdf]
---------------------

1. Datasets: 
    1. 400 hematoxylin and eosin (H&E) images (2048 X 1536 pixels)
    2. 4 labels: normal, benign, in situ carcinoma, and invasive carcinoma
    3. For each image, we perform 50 random color augmentations.
    4. Preprocessing pipeline (Fig 2);
        1. Original image
        2. Staining normalization 
        3. Augmented crops
        4. Deep CNN descriptors
        5. 3-norm pooling
        6. Building multiple datasets based on number of scales, crop sizes, encoders
        
2. Résultats:
To increase the robustness of the classifier
we use strong data augmentation and deep convolutional features extracted at
different scales with publicly available CNNs pretrained on ImageNet. On top of it,
we apply highly accurate and prone to overfitting implementation of the gradient
boosting algorithm. Unlike some previous works, we purposely avoid training
neural networks on this amount of data to prevent suboptimal generalization.