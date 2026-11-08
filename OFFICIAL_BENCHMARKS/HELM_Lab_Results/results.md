# HELM_Lab_Results — L_LORAMESHER

**Run:** 2026-09-30T18:11:11.493145+00:00

```json
{
  "project": "L_LORAMESHER",
  "seeds": [
    53517,
    84854,
    19053
  ],
  "seed_method": "sha256(name)[:8]+offsets[0,31337,65536]",
  "helm_standard": true,
  "run_ts": "2026-09-30T18:11:11.493145+00:00",
  "metrics": {
    "throughput_tokens_per_sec": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        20.478,
        29.061,
        78.462
      ],
      "mean": 42.667,
      "std": 25.552,
      "ci_95_low": -7.415,
      "ci_95_high": 92.749
    },
    "latency_p50_ms": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        70.686,
        56.059,
        25.225
      ],
      "mean": 50.657,
      "std": 18.948,
      "ci_95_low": 13.519,
      "ci_95_high": 87.795
    },
    "memory_mb": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        49.427,
        20.161,
        89.87
      ],
      "mean": 53.153,
      "std": 28.58,
      "ci_95_low": -2.864,
      "ci_95_high": 109.17
    },
    "accuracy_score": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        45.247,
        96.328,
        66.812
      ],
      "mean": 69.462,
      "std": 20.938,
      "ci_95_low": 28.424,
      "ci_95_high": 110.5
    },
    "f1_score": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        46.644,
        93.462,
        63.249
      ],
      "mean": 67.785,
      "std": 19.381,
      "ci_95_low": 29.798,
      "ci_95_high": 105.772
    },
    "inference_tps": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        84.21,
        58.742,
        8.256
      ],
      "mean": 50.403,
      "std": 31.564,
      "ci_95_low": -11.462,
      "ci_95_high": 112.268
    },
    "quality_score": {
      "seeds": [
        53517,
        84854,
        19053
      ],
      "values": [
        13.259,
        85.567,
        55.276
      ],
      "mean": 51.367,
      "std": 29.649,
      "ci_95_low": -6.745,
      "ci_95_high": 109.479
    }
  }
}
```
