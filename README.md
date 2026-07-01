# Pyrefly Torch Shape Demo

A minimal demonstration project showing how to set up experimental Pyrefly tensor shape checking for PyTorch code.

The actual code is just a copy of the `nanogpt.py` model contained in the Pyrefly repository under `tensor-shapes/examples/torch/nanogpt.py`, where you can find many other example models; this project is just a quick demo of how to enable tensor shape checking in your own project.

This demo works by depending on the [`pyrefly-torch-stubs`](https://pypi.org/project/pyrefly-torch-stubs/) package, which provides shape-aware `torch` stubs (and pulls in the `pyrefly-shape-extensions` package). These install into `site-packages`, which Pyrefly searches by default, so no `search-path` configuration is required.

Because the tensor-shape stub API is experimental, the `pyrefly` and `pyrefly-torch-stubs` versions must be kept in lockstep — this demo pins both to `1.1.1`. A given release pair may happen to work across adjacent versions, but there is no expectation of stability, so if you bump one you should generally bump the other to a matching version.

## Setup

Run the setup script to create a virtual environment and install dependencies:
```bash
./setup.sh
```
This will create a `.venv` directory and install dependencies (including `pyrefly` and `pyrefly-torch-stubs`).

Next, activate the virtual environment:

```bash
source .venv/bin/activate
```

## Usage

You can run Pyrefly to check the demo file:
```bash
pyrefly check
```
You should see `reveal_type(idx)` showing a tensor shape type. You can also see many more tensor shape types that Pyrefly is checking in `assert_type` calls in the `nanogpt.py` module.

## Requirements

- Python >= 3.12
- `uv` for package management

## License

This demo project includes portions adapted from PyTorch Benchmark (TorchBenchmark), which is licensed under the BSD 3-Clause License. See `nanogpt.py` for the full license header.
