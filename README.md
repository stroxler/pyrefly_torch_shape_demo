# Pyrefly Torch Shape Demo

A minimal demonstration project showing how to set up experimental Pyrefly tensor shape checking for PyTorch code.

The actual code is just a copy of the `nanogpt.py` model already contained in Pyrefly under `tensor-shapes/examples/torch/nanogpt.py`, and you can find many other models in that directory; this project is just a quick demo of how to use tensor shapes directly by grabbing a copy of the experimental stubs in the Pyrefly repository.

This demo works by cloning Pyrefly to `_pyrefly` and pointing `search-path` at it in `pyproject.toml`. That's not the only option, you could also just copy the `torch-stubs` folder from Pyrefly into your `site-packages`, but the approach here is good for early adopters because it should allow you to easily patch the stubs and submit a PR to Pyrefly if you find bugs or missing features you need.

## Setup

Run the setup script to create a virtual environment, install dependencies, and clone Pyrefly:
```bash
./setup.sh
```
This will create a `.venv` directory, install dependencies, and clone Pyrefly to `_pyrefly/` so that
we can point at the tensor shape stubs contained in it.

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
- Git for cloning the Pyrefly repository

## License

This demo project includes portions adapted from PyTorch Benchmark (TorchBenchmark), which is licensed under the BSD 3-Clause License. See `nanogpt.py` for the full license header.
