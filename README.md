# TinyGPT Tester

Automated test runner for the TinyGPT course. Validates student submissions (Java and Python) against expected outputs for each stage.

## Stages

| Stage | Slug                        | Description                                  |
| ----- | --------------------------- | -------------------------------------------- |
| E01   | `tokenization`              | Character tokenizer with encode/decode       |
| E02   | `embeddings`                | Token + positional embeddings                |
| E03   | `attention`                 | Scaled dot-product & multi-head attention    |
| E04   | `transformer-block`         | LayerNorm, MLP, transformer block            |
| E05   | `gpt-and-generate`          | GPT model forward pass & text generation     |
| E06   | `quantization-and-kv-cache` | INT8 quantization & KV cache                 |
| E07   | `profiling-and-compression` | Parameter counting, FLOPs, pruning, sparsity |

## Usage

```bash
# Build
make build

# Run a single stage
./tinygpt-tester -s tokenization -d /path/to/submission

# Test all solutions
make test-solutions
```

## Docker

```bash
# Build image
docker build -t ghcr.io/tensorhero-cn/tinygpt-tester .

# Run
docker run --rm -v /path/to/submission:/workspace ghcr.io/tensorhero-cn/tinygpt-tester -s tokenization -d /workspace
```

## Development

```bash
make deps    # Download and tidy dependencies
make test    # Run Go unit tests
make fmt     # Format code
make lint    # Lint code
```
