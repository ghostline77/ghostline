# Voice references

`voices.json` selects the full references for Patch, Iris and Cinder.

Each `selected/` directory contains:

- `reference.wav`: the conditioning recording.
- `reference.safetensors`: the speaker embedding and audio codec tokens.
- `reference.json`: the exact transcript, tensor dimensions and file hashes.

Pass the complete library to the audio tools. Patch and Cinder's recordings are
reviewed dialogue takes. Iris retains her original designed recording and its
unreviewed status. V's male and female references belong to the sibling audio
library.
