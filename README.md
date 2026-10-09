# indrajala-datasets-tinyshakespeare

Tiny Shakespeare, the character-level corpus of Andrej Karpathy's
[char-rnn](https://github.com/karpathy/char-rnn), for use by
[`indrajala-ml`](https://github.com/davidbarkhuizen/indrajala-ml) and other consumers that want a
pinned, checksum-verified source rather than a manually-supplied local copy.

This repo is a documented *source*, not a preprocessed cache: the text is stored exactly as
published, unchanged, and unsplit.

## contents

```
metadata.json                          - repo-level metadata (provenance, format, file list)
data/
  tinyshakespeare.txt                  - 1,115,394 characters, 40,000 lines
  tinyshakespeare.txt.metadata.json    - checksum, counts, vocabulary
```

The text is ASCII, 65 distinct characters (newline, space, punctuation, `3`, and the letters).
There is no train/test split: consumers make their own (`indrajala-ml` holds out the last 10%).

## quick start

```python
text = open("data/tinyshakespeare.txt", encoding="ascii").read()
vocabulary = sorted(set(text))
```

## provenance

See `metadata.json`'s `source` field: char-rnn's `data/tinyshakespeare/input.txt`, a subset of
Shakespeare's plays. The plays are in the public domain; char-rnn is MIT-licensed (stated in its
README).

## versioning

Consumers should pin to a specific tag or commit, not `main` - see `metadata.json`'s `version`
field for this repo's own packaging version.

## license

This repo's own packaging (this README, `metadata.json`, directory layout) is MIT-licensed - see
`LICENSE`. The text itself is in the public domain; see "provenance" above.
