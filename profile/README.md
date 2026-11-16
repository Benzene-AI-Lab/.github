<div align="center">

<img src="profile/benzene-icon.png" width="120">

# Benzene

**Models built from scratch.**

Not fine-tuned. Not distilled. No borrowed foundation model —
every generation starts from random initialization.

</div>

---

## Series

### 0.1 · Chinese language models

| Version | Params | Architecture | Status |
|---|---|---|---|
| [Benzene-0.1-Preview](https://github.com/CollinsLiu615/Benzene-0.1-Stand) | 35.0M | 8 layers × 576 dim, ctx 256, char-level vocab | Archived |
| [Benzene-0.1-Stand](https://github.com/CollinsLiu615/Benzene-0.1-Stand) | 97.64M | 12 layers × 768 dim, ctx 512, 16K BPE | Archived |

2.1 B tokens pretraining + SFT. Pretraining validation loss 0.8087 (ppl 2.24).

### 0.2 · Chess

Named after chemical molecules — each molecule is an independent variant with
its own playing personality.

| Variant | Chemistry | Role | Params | Status |
|---|---|---|---|---|
| [Alkane](https://github.com/CollinsLiu615/Benzene-0.2-Alkane) | Saturated single bonds | Stable baseline | 6.85M | ✅ |
| Alkene | Reactive double bonds | Deep search | 132.82M | Awaiting data |
| Alkyne | High-energy triple bonds | Aggressive | derived | Planned |
| Phenol | Aromatic parent | Strongest | 15.72M | Training |

AlphaZero-style: 19×8×8 board features → ResNet → 4,672-way policy head plus a
value head, paired with MCTS.

Speaks **UCI**, so it runs in CuteChess, Arena, Lichess (via lichess-bot),
Fritz, ChessBase and any other UCI front end:

```bash
python src/uci.py --ckpt weights/benzene-0.2-alkane.pt --sims 800
```

---

## Why train from scratch

Off-the-shelf models can do a lot, but they hide the path from zero to one.

Every release here publishes the training code, the data sources and the
known defects — including the parts that did not work.

---

## License

**CC BY-NC 4.0** — free for research, education and evaluation.
**Commercial use is not permitted.**

The 0.1 corpus contains third-party copyrighted material (the *Arknights*
script is used under a license from Hypergryph, research only). 0.2 training
data comes from Stockfish self-play and public game records. One
non-commercial license keeps the whole series consistent.

---

<div align="center">

**[Benzene-0.2-Alkane](https://github.com/CollinsLiu615/Benzene-0.2-Alkane)** ·
[Benzene-0.1-Stand](https://github.com/CollinsLiu615/Benzene-0.1-Stand)

</div>
