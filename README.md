# Emerging Tech: Deutsch and Deutsch-Jozsa Notebook

This repository contains a single notebook, `problems.ipynb`, with worked solutions for five quantum-computing exercises focused on:

1. Constructing promised Boolean functions (constant or balanced)
2. Classically determining whether a function is constant or balanced
3. Building Deutsch single-bit quantum oracles in Qiskit
4. Running Deutsch's algorithm with those oracles
5. Scaling the idea to a 4-input Deutsch-Jozsa workflow

The notebook combines short mathematical explanations with executable Python/Qiskit code.

## Clone the repository

```bash
git clone https://github.com/AdamGallagher339/emerging-tech.git
cd emerging-tech
```

## Create and activate a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

## Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## Run the notebook

```bash
jupyter notebook problems.ipynb
```

In Jupyter, use **Kernel -> Restart Kernel and Run All Cells** to verify execution order and reproducibility.

## Repository structure

- `problems.ipynb`: main assignment notebook
- `requirements.txt`: minimal Python dependencies required by the notebook
- `LICENSE`: project license

## Notes

- The notebook is designed to run in a standard Python 3 environment.
- All quantum simulations are local and use Aer simulators.

## Run & Verify (recommended)

Follow these commands locally to reproduce the notebook results.

1. Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

2. Install pinned dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

3. Execute the notebook (runs all cells and verifies execution):

```bash
jupyter nbconvert --to notebook --execute problems.ipynb --ExecutePreprocessor.timeout=120
```

Notes:
- To avoid committing outputs, clear them in-place before committing:

	```bash
	jupyter nbconvert --ClearOutputPreprocessor.enabled=True --inplace problems.ipynb
	```
- CI is configured to execute the notebook on push/PR. The notebook contains an emulator fallback path when Qiskit is not available, so the repository is runnable without a local Qiskit installation. If you want to run the Aer simulator locally, install Qiskit with:

	```bash
	pip install qiskit qiskit-aer
	```