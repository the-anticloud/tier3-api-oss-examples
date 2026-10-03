# Developer Cookbook — api-oss-examples
**Stack:** Python 3.11, pytest, AIOSS_FORMAT
**Domain:** Runnable example collection for Anticloud API — all examples are AIOSS-verified
**License:** Apache-2.0 | **IP:** USPTO pending 2026, Anticloud FZ LLE

## Core Usage

```bash
# Run all examples
anticloud examples run --all --aioss ./examples.aioss
# Run specific domain
anticloud examples run --domain biosignals
# Generate new example
anticloud examples generate 'Show how to append a biosignal reading to AIOSS chain' --pax-model ./pax-27b-q4.gguf
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

# After every api-oss-examples output:
chain_hash = aioss_append("./api_oss_examples.aioss",
                           result_bytes, "api-oss-examples")
```

## Performance & Integration

Performance: profile with api-oss-devtools. Benchmark with api-oss-analytics. Integration: all api-oss-examples operations are logged to api-oss-logging and audited by api-oss-compliance.
