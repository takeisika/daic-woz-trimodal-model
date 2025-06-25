# DAIC‑WOZ Trimodal Model
A reproducible pipeline for **depression‐risk screening** that fuses  
*speech acoustics* (wav2vec 2.0), *facial dynamics* (OpenFace CLNF), and  
*LLM‑based text inference* (OpenAI o1 pro) on the **DAIC‑WOZ** benchmark.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15739862.svg)](https://doi.org/10.5281/zenodo.15739862)

## Repository contents
| Path | Purpose |
|------|---------|
| `preprocessing.ipynb` | End‑to‑end notebook that downloads DAIC‑WOZ, extracts participant utterances, merges every 5 utterances with a one‑utterance overlap, and writes audio WAV and video-feature CSV pairs. |
| `trimodal_model.ipynb` | Training & evaluation of the **tri‑modal fusion network**<br> (audio+vision+text). |
| `huang2024_vocal_only_leakage_check.ipynb` | Replication of Huang *et al.* (2024) with and without speaker‑level data leakage; demonstrates the accuracy collapse from 96–100 % to ≈60 %. |
| `requirements.txt` | Frozen Python dependencies tested on Google Colab (CUDA 12.1). |
| `LICENSE` | MIT License (free academic & commercial use, no warranty). |

## Quick start (Google Colab)

```bash
# 1 — Clone and install
!git clone https://github.com/takeisika/daic-woz-trimodal-model.git
%cd daic-woz-trimodal-model
!pip install -r requirements.txt

# 2 — Run preprocessing
!jupyter nbconvert --to notebook --execute preprocessing.ipynb

# 3 — Train the trimodal network
!jupyter nbconvert --to notebook --execute trimodal_model.ipynb

