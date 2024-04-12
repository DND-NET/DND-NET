# KDD - 2024 Submission

## Additional Results for Rebuttal

We sincerely appreciate all reviewers for their valuable comments. Based on the comments, we have conducted additional experiments and the results are reported as follows.

### P1. Non-decoupled GNN with NPA and PL (Reviewer 1tLR Q2)

Additional results on replacing our label noise-robust GNN with non-decoupled GCN as the backbone are as follows:

| Dataset     | Methods                 | Clean Labels      | **Uniform Noise 20%** |   **Uniform Noise 40%**                 | **Uniform Noise 60%**                   | **Pair Noise 20%**    |     **Pair Noise 30%**                  |    **Pair Noise 40%**                   |            **Pair Noise 50%**           |
|-------------|-------------------------|:-----------------:|:-----------------:|:-----------------:|:-----------------:|:-----------------:|:-----------------:|:-----------------:|:-----------------:|
| **Cora-ML** | **(GCN+NPA+PL)**        | 84.96±1.12        | 77.11±3.56        | 74.94±2.95        | 52.42±5.32        | 82.69±1.62        | 76.43±2.60        | 68.05±2.83        | 43.99±3.51        |
|             | **(DnD-NeT)**   | **85.58±0.96**    | **83.88±1.87**    | **79.14±2.54**    | **63.56±6.15**    | **84.72±1.29**    | **80.47±2.03**    | **75.18±3.95**    | **49.79±7.99**    |
| **CiteSeer**| **(GCN+NPA+PL)**        | 73.24±1.23        | 69.31±2.29        | 61.69±6.90        | 42.74±6.14        | 67.56±3.26        | 63.93±4.54        | 61.64±4.68        | 37.39±5.54        |
|             | **(DnD-NeT)**   | **75.57±1.14**    | **74.30±1.20**    | **70.85±2.17**    | **58.35±5.37**    | **73.98±1.22**    | **71.36±2.31**    | **70.26±2.82**    | **46.33±3.06**    |
| **PubMed**  | **(GCN+NPA+PL)**        | 82.74±0.47        | 81.55±1.11        | 72.16±8.59        | 43.62±2.67        | 79.94±1.48        | 76.51±2.81        | 70.58±3.03        | 60.17±2.80        |
|             | **(DnD-NeT)**   | **84.02±0.44**    | **84.26±0.45**    | **80.73±1.34**    | **65.63±5.12**    | **82.33±0.56**    | **79.29±1.13**    | **78.45±2.39**    | **60.74±3.74**    |
| **Coauthor CS** | **(GCN+NPA+PL)**    | 92.54±0.16        | 91.62±0.23        | 90.03±0.51        | 89.29±0.74        | 90.91±0.41        | 88.25±0.93        | 79.34±3.1         | 49.06±10.8        |
|             | **(DnD-NeT)**   | **92.71±0.25**    | **92.14±0.27**    | **90.94±0.52**    | **90.00±0.63**    | **91.99±0.47**    | **88.44±1.13**    | **80.97±1.32**    | **65.38±4.97**    |

The results demonstrate that conventional non-decoupled GNN with NPA and PL performs behind DnD-NET, which shows the importance of our decoupled architecture.

### P2. Experiments on high label noise ratio (Reviewer 7B64 Q1&Q2)

The experiment results of all methods on five datasets with 50% pair noise are reported as follows:

#### Results on ogbn-arxiv
| Method      | **Uniform Noise 20%** | **Uniform Noise 40%** | **Uniform Noise 60%** | **Pair Noise 20%** | **Pair Noise 30%** | **Pair Noise 40%** | **Pair Noise 50%** |
|-------------|:-------------------:|:-------------------:|:-------------------:|:----------------:|:----------------:|:----------------:|:----------------:|
| GCN         | 50.4±1.0          | 50.0±0.8          | 45.5±1.2          | 52.0±0.6       | 51.4±0.6       | 50.2±1.2       | 38.96±2.4      |
| Co-teaching | 50.9±0.7          | 50.8±0.1          | 50.0±0.6          | 50.8±0.5       | 50.1±0.4       | 46.6±0.8       | 34.42±5.8      |
| T-Revision  | 52.5±0.4          | 53.9±0.2          | 49.5±2.1          | 22.9±7.5       | 20.3±2.9       | 19.88±6.6      | 32.18±5.8      |
| Pi-GNN      | 54.6±5.8          | 53.4±4.3          | 53.1±3.8          | 51.8±2.7       | 49.2±3.2       | 48.4±6.3       | 39.38±3.5      |
| ERASE       | _67.1±1.3_        | _62.6±1.5_        | _57.1±1.9_        | _67.9±1.2_     | _65.7±1.3_     | _53.4±2.1_     | 37.01±7.6      |
| DnD-NeT   | **67.5±1.5**      | **65.9±1.1**      | **59.7±2.3**      | **68.2±1.9**   | **66.2±2.0**   | **53.8±1.5**   | **40.34±1.2**     |

As shown in the results, our approach can still achieve noticeable improvements over baselines on high label noise ratio on different datasets.


### P3. Comparison under the setting in ERASE (Reviewer H5zy Q1)

The comparison results between ERASE and our approach under the setting of ERASE are as follows:



Based on the results, we can observe that our model still outperforms ERASE under this setting. 


***

## Divide and Denoise: Empowering Simple Models for Robust Semi-Supervised Node Classification against Label Noise

DnD-NeT offers a new solution to tackle the two problems from both the model architecture and algorithm perspectives, reviving the utility of message passing and pseudo labels in the problem of semi-supervised node classification with noisy labels. Specifically, DnD-NeT involves a label-noise robust GNN equipped with a reliable graph pseudo labeling algorithm, which can attain both effectiveness and efficiency when solving the studied problem. Extensive experiments demonstrate its state-of-the-art performance in semi-supervised node classification with varying levels of label noise.



### Embedding space visulization on Cora-ML (left) and CiteSeer (right)

To run the code:
```python
python main.py
```

Run on ogbn-arxiv:
```python
python main_arix.py
```
