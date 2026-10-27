# faster-whisper models

Copies of two [faster-whisper](https://github.com/SYSTRAN/faster-whisper) models for environments where
Hugging Face is not reachable but GitHub is.

| Folder | Source | Size |
| --- | --- | --- |
| `large-v3-turbo` | [deepdml/faster-whisper-large-v3-turbo-ct2](https://huggingface.co/deepdml/faster-whisper-large-v3-turbo-ct2) | 1.6 GB |
| `small` | [Systran/faster-whisper-small](https://huggingface.co/Systran/faster-whisper-small) | 0.5 GB |

`model.bin` is split into parts. Join them in order and compare the hash with `manifest.json`:

```sh
cat large-v3-turbo/model.bin.part-* > large-v3-turbo/model.bin
sha256sum large-v3-turbo/model.bin
```

Then load the folder with `WhisperModel("large-v3-turbo", device="cpu", compute_type="int8")`.

## License

Whisper by OpenAI, MIT License (see `LICENSE`). CTranslate2 conversions by Systran and deepdml, MIT License.
