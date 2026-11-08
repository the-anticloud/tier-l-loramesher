# Deploy Guide — L_LORAMESHER
**Tier:** TIER_8_RF_MESH_DEFENSE | **Stack:** Python 3.11, loramesher 0.x, K_MESHCORE, PAX 27B, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, loramesher 0.x. LoRa-capable hardware (ESP32 with SX1276). 4GB RAM gateway.

## Environment
ESP32 or similar MCU with SX1276 LoRa per mesh node. Gateway: Raspberry Pi with LoRa HAT.

## AIOSS Integration
```bash
aioss init --module L_LORAMESHER --output ./l_loramesher.aioss
aioss append --chain ./l_loramesher.aioss --payload ./output.bin --module L_LORAMESHER
aioss verify --chain ./l_loramesher.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_LORAMESHER",
    aioss_chain="./L_LORAMESHER.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_LORAMESHER.aioss --verbose
python -m L_LORAMESHER.tests.smoke
```
