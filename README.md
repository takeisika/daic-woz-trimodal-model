# DAIC‑WOZ Trimodal Model
A reproducible pipeline for depression detection that fuses speech acoustics (wav2vec 2.0), facial dynamics (OpenFace CLNF), and LLM‑based binary classification on transcripts (OpenAI o1 pro) on the DAIC‑WOZ dataset.

## Repository contents
| Path | Purpose |
|------|---------|
| `preprocessing.ipynb` | Downloads DAIC‑WOZ, extracts participant utterances, merges every 5 utterances with a one‑utterance overlap, and writes pairs of audio WAV files and video-feature CSVs. |
| `trimodal_model.ipynb` | Trains & evaluates the tri‑modal fusion network (audio+vision+text). |
| `huang2024_vocal_only_leakage_check.ipynb` | Replicates Huang et al. (2024) with and without speaker‑level data leakage and demonstrates the accuracy collapse from 96–100% to ≈60%. |
| `requirements.txt` | Lists dependencies. |
| `LICENSE` | MIT License (free academic & commercial use, no warranty). |
