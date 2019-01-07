Resume de [http://papers.nips.cc/paper/8003-towards-robust-interpretability-with-self-explaining-neural-networks.pdf]
-------
1. Intepretabilité a 3 propriété intrinsèque:
    1. Explicitness (explicité?)
    2. Faithfulness 
    3. Stability

2. Définition 3.1: **difference bounded**:  ||f(x) - f(y)|| <= L||h(x) -h(y)||

3. Définition 3.2: **locally difference bounded** by h: if for every x_0, there exist delta > 0 and L \in R such that ||x - x_0|| < delta implies ||f(x) - f(x_0)|| <= L||h(x) - h(x_0)||

3. Définition 3.3: f: X --> Y is **self explaining prediction model** if it has the form: f(x) = g(theta_1(x)h_1(x), ..., theta_k(x)h_k(x))
    1. g is monotone and completely additively separable
    2. for every z_i := theta_i(x)h_i(x), g satisfies g'/z_i >= 0
    3. theta is locally difference bounded by h
    4. h_i(x) is an interpretable representation of x
    5. k is small
    
4. If you want to use basis concepts (high level concepts) for interpretability we must have those sets:
    1. **Fidelity**: the representation of x on terms of concepts should preserve relevant information
    2. **Diversity**: inputs should be representable with few non-overlapping concepts
    3. **Grounding**: concepts should have an immediate human-understanble interpretation
    
5. A **senn**:Figure 1
    1. concept encoder
    2. input-dependent parametrizer
    3. aggregation function
    