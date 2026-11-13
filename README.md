# Chess Agent (4 KB Python)

A small, single-file Python chess agent. The engine is embedded in `main.py` as
Base85-encoded, LZMA-compressed data, keeping the source compact. It uses only
the Python standard library, so there is nothing to install.

## Run

```sh
python main.py
```

Python 3 is required. No third-party packages are needed.

The contest entrypoint needs the contest runner environment to execute; the
plain `python main.py` command above is not sufficient for a full game.

## Local verification

- Three smoke positions were tested; each returned a legal move.
- A 24-half-move self-play run completed with legal moves throughout.
- The latest run recorded a maximum of 1.052 seconds per move.
- The enforced per-move limit is 10 seconds.
- These local smoke checks are separate from running the contest program; they do not exercise the contest entry point.

## Scope

These are local smoke tests only. They are not an official tournament match,
and they do not establish playing strength. No claim is made about beating the
Sunfish benchmark.

## Limitations

- Not validated in tournament play or against rated engines.
- Move timing was measured on one local machine and may vary elsewhere.
- The compressed engine block is opaque; edit it only with care.
- The agent is intentionally small, so search depth and strength are limited.
