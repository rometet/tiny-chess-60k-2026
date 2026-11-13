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

## Experimental 60k-node variant

- This is a newly added test candidate, not the previously released version.
- The search budget is 60,000 nodes, increased from the earlier 24,000-node setting.
- Greater search depth may improve move quality in some positions.
- Longer searches may also increase response time or cause timing issues.
- In three local practice games, this variant scored 3 wins and 0 losses against depth-2 through depth-4 opponents.
- The official grading has not yet been completed; see the local eight-game results below.
- The program is still under the 4,096-byte size limit.
- No prize or specific competitive result is guaranteed.

## Eight-game practice

- A complete local eight-game comparison has now been run between the two engines.
- The original 24,000-node engine finished with 1 win, 3 draws, and 4 losses.
- The experimental 60,000-node variant finished with 3 wins, 2 draws, and 3 losses.
- Applying the published practice-Elo formula to these games gives local estimates of about 1,173 for the original engine and 1,396 for the 60,000-node variant.
- These figures are local estimates only, not the official practice score.
- They do not guarantee a prize or any official result.
- Local matches can vary with hardware, time controls, and opponent behavior.
- The eight-game sample is small, so treat these numbers as a rough indication only.

## Limitations

- Not validated in tournament play or against rated engines.
- Move timing was measured on one local machine and may vary elsewhere.
- The compressed engine block is opaque; edit it only with care.
- The agent is intentionally small, so search depth and strength are limited.
