1. They use the Variational autoencoder (VAE) framework. 
    1. Let **G = (A, E, F)** be a graph specified with its _adjacency matrix A_, _edge attribute tensor E_, and _node attribute matrix F_.
    2. The encoder is defined by a variational posterior q_phi(**z**|G)
    3. The decoder is defined by a generative distribution p_theta(G|**z**)
    4. phi and theta are learned parameters.
    5.  Furthermore, there is a prior distribution p(**z**) imposed on the latent code representation as a regularization: p(**z**) = N(0, I)
    6. Fig 1
2.  The decoder part: A bigger assumption they fixed a number of nodes k in the order of the tens.
    1.  We propose to make the decoder output a probabilistic fully-connected graph G~ = (A~, E~, F~) on k nodes at once. 
    2. The decoder itself is deterministic. Its architecture is a **simple multi-layer perceptron (MLP)** with three outputs in its last layer
    3. _Sigmoid activation function_ is used to compute A~, whereas _edge- and node-wise softmax_ is applied to obtain E~ and F~, respectively
    4. At test time, we are often interested in a (discrete) point estimate of G~, which can be obtained by taking _edge- and node-wise argmax_ in A~, E~, and F~.
    5. Prudencio got the good hypothesis to output 3 things: the number of nodes; the string characters and the adjacency matrix. 
    Here they output 3 things too: the adjacency matrix; the edges matrix and the node attribute matrix. But they output them with a probability score (more likely how it can happen). 