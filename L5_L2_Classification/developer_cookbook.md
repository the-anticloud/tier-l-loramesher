# Developer Cookbook — L_LORAMESHER
**Stack:** Python 3.11, loramesher 0.x, K_MESHCORE, PAX 27B, AIOSS_FORMAT
**Domain:** LoRaMesher: LoRa mesh library for Anticloud IoT sensor swarms

## LoRaMesher sensor swarm
```python
from l_loramesher import LoRaMesherGateway

gateway = LoRaMesherGateway(
    lora_port="/dev/ttyUSB0",
    pax_model="./pax-27b-q4.gguf",
    aioss_chain="./loramesher.aioss"
)

gateway.start()
for reading in gateway.sensor_stream():
    print(f"Node {reading.node}: {reading.sensor_type}={reading.value}")
    if reading.battery_pct < 20:
        action = gateway.pax_battery_management(reading.node)
        gateway.apply(action)
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
