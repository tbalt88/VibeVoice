# kaitona branch: VibeVoice TTS on Colab

This branch adds one thing to the fork: a Colab notebook that runs VibeVoice's multi-speaker, voice-cloning TTS. `main` keeps mirroring `microsoft/VibeVoice` untouched.

Microsoft removed the TTS code from its repo in September 2025. It doesn't need restoring: Hugging Face Transformers has included VibeVoice since 5.17, and the notebook uses that with the original 1.5B weights (`vibevoice/VibeVoice-1.5B-hf`, pinned revision `d4cd82e`).

## Run it

[Open in Colab](https://colab.research.google.com/github/tbalt88/VibeVoice/blob/kaitona/kaitona/vibevoice_kaitona.ipynb), pick **Runtime > Change runtime type > T4 GPU**, and run the cells in order. A free Colab account is enough.

- **Part A** generates one line with a public sample voice. Listen before going further.
- **Part B** takes an uploaded zip with reference voices and a `lines.json`, generates every line with several seeds, and scores each take's voiced length against a target window (within 10% is a fit).
- The last cell downloads everything as a zip.

The bundle format is described in the notebook. Reference voices stay out of this public repo; you upload them per session.

## Files

| File | What it is |
|---|---|
| `vibevoice_kaitona.ipynb` | The notebook |
| `requirements.txt` | Pinned packages: transformers 5.22.2, diffusers 0.35.2, accelerate 1.15.0, soundfile 0.14.0 |

## Terms

Code and weights are MIT. Microsoft recommends research use, says outputs should be disclosed as AI, and rules out cloning a real person's voice without recorded consent. The open code adds no watermark, so disclosure is on the user.
