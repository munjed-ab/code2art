# Code2art Generator
<img width="1483" height="1485" alt="sample_final_version" src="https://github.com/user-attachments/assets/ca4afd5e-83d0-43c8-8040-1e3ce00669ba" />

This project explores an unusual idea: transforming **code features into art**.
It’s an ongoing experiment in using neural networks to visualize the structure and “feel” of code as images — not for aesthetics alone, but to find patterns and relationships hidden inside code representations.

I’m building and refining this project gradually, learning as I go. It’s not perfect, and that’s exactly why it’s here — to grow.

---

## Overview

The model takes a numerical feature representation of code and generates images that reflect underlying structure and semantics.
The generator is trained to preserve **variance, similarity, and diversity** across features, and then evaluated using several clustering and correlation metrics.

<img width="1473" height="1477" alt="samples_256_20251017_1130_final" src="https://github.com/user-attachments/assets/24a91639-83bd-425d-bc4e-c4684a213cc4" />

The included evaluator (`CodeImageEvaluator`) measures:

* **Clustering Quality**: how well the generated images group by code type
* **Similarity Preservation**: how code similarity translates into image similarity
* **Diversity**: visual and statistical diversity of outputs
* **t-SNE Visualization**: 2D projection of generated images for visual inspection

Example visualization:
<img width="1227" height="1051" alt="tsne_visualization (1)" src="https://github.com/user-attachments/assets/606e1a2b-8b2c-4a7b-81c1-40b408af3472" />


---

## Try It on Hugging Face

You can try the model interactively on Hugging Face Spaces.

A simple demo lets you:

* **Input your own code**
* **Watch it generate an image instantly**
* **Explore how feature changes affect the final output**

Live Demo: [https://huggingface.co/spaces/munjed/code2art](https://huggingface.co/spaces/munjed/code2art)

---

## Current Results

```
Silhouette Score: 0.2800
Calinski-Harabasz: 1526.63
Davies-Bouldin: 1.52

Pearson Correlation: 0.92
Spearman Correlation: 0.80

Within-image Variance: 0.40
Between-image Diversity: 361.50
```

The model currently shows **strong similarity preservation**, meaning it captures relationships between code samples well, but **clustering and visual clarity still need work**.

---

## Current Problems

* **Generated images lack strong structural coherence** — they sometimes look abstract or noisy.
* **Loss stability issues** — balancing variance and reconstruction terms is tricky.
* **Feature variance preservation** can explode or vanish depending on learning rate and scaling.
* **Higher resolutions (e.g. 256x256)** increase complexity fast, sometimes degrading output quality.
* **Code Extraction** need more improvement to get the features dataset we need for different languages.
---

## Next Steps

* Stabilize training using better loss normalization and dynamic weighting.
* Experiment with pretrained visual priors or diffusion-based conditioning.
* Possibly integrate contrastive learning or VAE-like embeddings.

---

## License

MIT — feel free to use, modify, and build upon it.


<img width="1483" height="1485" alt="final_samples (7)" src="https://github.com/user-attachments/assets/76877dcb-f5f0-4283-9d5b-bd711ec42301" />

![test](https://github.com/user-attachments/assets/40c24e16-fc71-4a3e-9fea-d05a2db01a4c)


