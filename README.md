# helix28-node

Reference implementation of the Helix28Chain dual-strand node.

## Components

- **Strand Alpha Validator (The Keepers)** — zk-DID state management, 
  Tendermint BFT consensus, 2-second block time
- **Strand Beta Validator (The Executors)** — RISC Zero zkVM execution, 
  HotStuff BFT consensus, 500ms block time
- **Enzyme Node (The Relayers)** — ZKP query relay between strands, 
  binary yes/no responses only

## Tech Stack

- Language: Rust
- zkVM: RISC Zero (RISC-V target)
- Alpha Consensus: Tendermint BFT
- Beta Consensus: HotStuff BFT with parallel execution
- Networking: libp2p
- Data Availability: Celestia-compatible DA layer
- Identity: W3C DID spec with Dilithium-3 post-quantum signatures

## Architecture

The dual-strand design mirrors DNA:
- Alpha stores cryptographic identity commitments (zk-DIDs + CIDs)
- Beta executes private smart contracts via zkVM
- Enzyme Nodes relay yes/no proof queries between strands
- No raw personal data ever crosses the strand boundary
- Strands synchronize at epoch boundaries every ~200 seconds

## Performance Targets

- Phase 0 testnet: 200 TPS, median latency under 3 seconds
- Phase 1 with hardware proving acceleration: 1,000+ TPS
- Targets updated with measured data at each testnet phase

## Status

Pre-development. Technical co-founder search active.
Architecture fully specified in the white paper.
Contributions and technical discussions welcome.

## Contributing

Open an issue to discuss the architecture.
Read the white paper first:
github.com/helix28chain/whitepaper
