<h1 style="margin: 0 0 0.35rem 0; line-height: 1.1;">MixFlow</h1>

[![Code License: MIT](https://img.shields.io/badge/Code%20License-MIT-green.svg)](./LICENSE)
[![arXiv](https://img.shields.io/badge/arXiv-2601.11827v2-b31b1b.svg)](https://arxiv.org/abs/2601.11827)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](#)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.x-EE4C2C.svg)](#)
[![Project status](https://img.shields.io/badge/Status-Research%20code-informational.svg)](#)
[![Docs](https://img.shields.io/badge/Docs-local-blueviolet.svg)](./docs/index.md)

**Shortest-Path Flow Matching with Mixture-Conditioned Bases for OOD Generalization to Unseen Conditions.**

---

<table>
<tr>
<td align="center">
<img src="./docs/figs/manif_vanila_B.png" width="100%">
<br>
<b>(A)</b> Vanilla CFM
</td>
<td align="center">
<img src="./docs/figs/manif_ptflow_B.png" width="100%">
<br>
<b>(B)</b> SP-FM
</td>
</tr>
</table>

## Overview

This repository contains research code for **shortest-path flow matching** with **descriptor-conditioned mixture bases** for descriptor-controlled generation.

Instead of relying on a single Gaussian base distribution, the method learns a **condition-dependent mixture base** jointly with a **descriptor-conditioned flow field**, trained via shortest-path (optimal transport) flow matching. Conditioning the base enables the model to adapt its starting distribution across conditions, improving **out-of-distribution (OOD) generalization** to unseen conditions.

## Publication

This repository accompanies the arXiv manuscript:

- **Title:** *Shortest-Path Flow Matching with Mixture-Conditioned Bases for OOD Generalization to Unseen Conditions*
- **arXiv:** 2601.11827v2 \[cs.LG\] (11 Feb 2026)
- **Paper link:** https://arxiv.org/html/2601.11827v2

## Datasets

### Synthetic Data

We construct a synthetic benchmark of letter populations, where each condition corresponds to a letter and a specific rotation. Each descriptor encodes the letter identity and rotation, and the model learns a mixture base distribution per condition. This setup allows us to test extrapolation to unseen letters and rotation angles.

### Morphological Perturbations

We evaluate on high-content imaging data in feature space. Cells (from BBBC021 and RxRx1) are embedded with a vision backbone, and the model is trained to generate unseen phenotypic responses from compound descriptors alone.

### Perturbation Datasets

For transcriptomic perturbations, we use Chemical- or CRISPR-based single-cell datasets (Norman, ComboSciPlex, Replogle and iAstrocytes). Conditions correspond to perturbation embeddings from pretrained models, and the model is trained to model the distribution of perturbed cells.

## Documentation

Check the <a href="./docs/index.md">documentation</a> for more information about how to use the model and get the data.

## License

This work is released with the MIT license, please see <a href="./LICENSE">the license file</a> for more information.
