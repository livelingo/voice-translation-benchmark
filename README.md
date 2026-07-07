# LiveLingo Voice Translation Benchmarks (2026)

Open benchmark data for **real-time voice translation quality**: speech in, translation out, scored for comprehension fidelity by three independent LLM judges (GPT-4o, Gemini 2.5 Flash, Claude). Published by [LiveLingo Research](https://www.livelingo.io/research). All data is **CC-BY 4.0** — reuse it freely with attribution.

Live leaderboards: [16-corridor benchmark](https://www.livelingo.io/research/voice-corridor-benchmark-2026) · [latency + comprehension benchmark](https://www.livelingo.io/research/benchmark-2026)

## Voice-corridor benchmark — 16 language pairs

Real-time voice translation accuracy across 16 migrant-worker language corridors. LiveLingo ranked #1 on all 16 pairs. Evaluated 2026-07-06.

### Overall ranking

| System | Comprehension (0–5) |
|---|---|
| **LiveLingo** | **4.330** |
| Google | 3.947 |
| Azure | 3.466 |
| Whisper + GPT-4o-mini | 3.196 |

### Per-corridor results

| Corridor | n | LiveLingo | Azure | Whisper + GPT-4o-mini | Google | Lead |
|---|---|---|---|---|---|---|
| Turkish→German | 59 | **4.27** | 3.80 | 3.63 | 3.97 | +0.30 |
| Arabic→German | 60 | **4.24** | 2.93 | 2.35 | 3.89 | +0.35 |
| Arabic→French | 60 | **4.28** | 3.07 | 2.46 | 3.93 | +0.34 |
| Arabic→Spanish | 20 | **3.53** | 3.03 | 2.15 | 3.38 | +0.15 |
| Indonesian→Japanese | 30 | **4.46** | 3.14 | 3.92 | 3.96 | +0.50 |
| Indonesian→Korean | 30 | **4.23** | 3.14 | 3.40 | 3.93 | +0.30 |
| Indonesian→Chinese | 30 | **4.49** | 3.11 | 3.58 | 4.04 | +0.45 |
| Vietnamese→Korean | 30 | **4.44** | 3.96 | 2.72 | 4.19 | +0.26 |
| Vietnamese→Japanese | 30 | **4.48** | 3.73 | 2.57 | 4.28 | +0.20 |
| Portuguese→German | 30 | **4.61** | 4.12 | 3.59 | 4.50 | +0.11 |
| Portuguese→French | 30 | **4.34** | 4.07 | 3.94 | 4.31 | +0.03 |
| Polish→German | 20 | **3.83** | 3.37 | 3.30 | 3.52 | +0.32 |
| Chinese→Vietnamese | 20 | **4.67** | 3.75 | 4.28 | 3.83 | +0.38 |
| Chinese→Indonesian | 20 | **4.45** | 3.77 | 3.97 | 3.45 | +0.48 |
| Chinese→Malay | 20 | **4.55** | 3.98 | 4.00 | 3.85 | +0.55 |
| Malay→Chinese | 20 | **4.43** | 3.18 | 2.93 | 3.43 | +1.00 |

Data: [`results.json`](voice-corridor-benchmark-2026/results.json) · [`results.csv`](voice-corridor-benchmark-2026/results.csv)

## Latency, stability, and comprehension benchmark

Two sections. **Section 1 (latency/stability):** median Final Transcript Latency 1.5 s for LiveLingo with zero Normalized Erasure, vs 2.7 s (Google Cloud), 4.8 s (Azure), 27 s (Whisper + GPT-4o-mini) on conversational broadcast audio. **Section 2 (comprehension fidelity, n=120):** LiveLingo composite **4.96 / 5** vs Google 4.77, Azure 4.65, Whisper + GPT-4o-mini 4.63 across en→es / en→zh-CN / en→ja / en→de, scored by three independent frontier LLM judges. Speech-to-speech addenda cover Gemini Live and the OpenAI Realtime API.

Data: [`results.json`](benchmark-2026/results.json) · [`results.csv`](benchmark-2026/results.csv) · [`comprehension-results.json`](benchmark-2026/comprehension-results.json) · [`comprehension-results.csv`](benchmark-2026/comprehension-results.csv) · [`audio.zip`](benchmark-2026/audio.zip) (30 authored English source utterances, 16 kHz mono WAV) · [`gemini-live-results.json`](benchmark-2026/gemini-live-results.json) · [`openai-realtime-results.json`](benchmark-2026/openai-realtime-results.json)

## Method (summary)

Every system receives **identical source audio** and runs its own complete speech-translation pipeline, the way a user actually experiences it. Three independent LLM judges from competing labs score each translation 0–5 for whether a listener understands the message the speaker intended; the composite is the mean of the judges, and judge parse-failures are excluded rather than scored zero. Full methodology, test-set provenance, reproducibility notes, and limitations are on the [benchmark pages](https://www.livelingo.io/research/benchmark-2026#methodology).

## Citing

```bibtex
@misc{livelingo2026voicebenchmarks,
  author       = {{LiveLingo Research}},
  title        = {LiveLingo Voice Translation Benchmarks 2026},
  year         = {2026},
  howpublished = {\url{https://www.livelingo.io/research/voice-corridor-benchmark-2026}},
  note         = {Data: CC-BY 4.0, https://github.com/livelingo/voice-translation-benchmark},
}
```

Per-corridor permalinks for citing a single pair: `https://www.livelingo.io/research/voice-corridor-benchmark-2026#tr-de` (etc.).

## License

[CC-BY 4.0](LICENSE). Attribution: “LiveLingo Research — livelingo.io”.
