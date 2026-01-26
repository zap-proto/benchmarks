# ZAP Protocol Benchmarks

Real-world performance benchmarks for ZAP Protocol comparing against Protobuf, JSON, and traditional architectures.

## Benchmark Categories

### 1. Serialization Benchmarks (`bench-serialize/`)
Core encoding/decoding performance comparisons.

### 2. Agent Benchmarks (`bench-agents/`)
MCP server memory overhead and multi-agent orchestration:
- Claude Code with 100 individual MCP servers
- Hanzo Dev with 1 ZAP router (proxying to 100 MCP servers)
- 20 parallel sub-agent task execution

### 3. Blockchain Benchmarks (`bench-blockchain/`)
Warp messaging and consensus operations:
- Cross-chain message encoding
- Validator set updates
- State proof verification
- Consensus round-trip times

### 4. Inference Benchmarks (`bench-inference/`)
Distributed AI inference:
- KV cache shard transfers
- Model weight distribution
- Batch prompt encoding

## Quick Start

```bash
# Install dependencies
make setup

# Run all benchmarks
make bench

# Run specific benchmark suite
make bench-agents
make bench-blockchain
make bench-serialize
make bench-inference

# Generate reports
make report
```

## Requirements

- Go 1.21+
- Python 3.11+
- Node.js 20+ (for MCP benchmarks)
- Docker (optional, for isolated tests)

## Results

Results are written to `results/` directory in JSON format and can be visualized with:

```bash
make charts
```

## Methodology

All benchmarks follow these principles:

1. **Reproducibility**: Fixed seeds, controlled environments
2. **Statistical rigor**: Multiple iterations, percentile reporting
3. **Fair comparison**: Same data structures across formats
4. **Real workloads**: Based on actual Hanzo/Lux production patterns

See [METHODOLOGY.md](METHODOLOGY.md) for detailed methodology.

## License

Apache 2.0
