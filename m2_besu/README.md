## Milestone #2: Lighthouse and Besu

References:

- Besu merge branch: https://github.com/hyperledger/besu/tree/merge

## How To Run

This testnet requires 3 terminal processes, one for Besu one for a beacon node
and one for a validator client. See the per-terminal commands below.

### Terminal 1: Besu

```bash
git clone --recursive https://github.com/hyperledger/besu
cd besu
git checkout merge
./gradlew --parallel installDist
besu/build/install/besu/bin/besu --config-file=besu-config.toml
```

### Terminal 2: Lighthouse Beacon Node

```bash
cd m2_lighthouse
./start_beacon_node.sh 8550
```

*Note: it's important to start the beacon node before the validator client
since that script also generates the testnet configuration.*

### Terminal 3: Lighthouse Validator Client

```bash
cd m2_lighthouse
./start_validator_client.sh
```
