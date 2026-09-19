# Function Vectors in Large Language Models
### [Project Website](https://functions.baulab.info) | [Arxiv Preprint](https://arxiv.org/abs/2310.15213) | [OpenReview](https://openreview.net/forum?id=AwyxtyMwaG)

This repository contains data and code for the paper: [Function Vectors in Large Language Models](https://arxiv.org/pdf/2310.15213).

<p align="left">
<img src="https://functions.baulab.info/images/Paper/fv-demonstrations.png" style="width:100%;"/>
</p> 

## Setup

### Recommended: Using `uv`

We recommend using [`uv`](https://docs.astral.sh/uv/) for fast, reliable environment management based on `pyproject.toml`.

To create the virtual environment and install all dependencies:
```bash
uv sync
```

To install with CUDA/GPU acceleration enabled for PyTorch (e.g., CUDA 12.1):
```bash
uv sync --extra-index-url https://download.pytorch.org/whl/cu121
```

You can then run any script or command directly inside the environment without manual activation using `uv run`:
```bash
uv run python src/compute_indirect_effect.py --help
```

### Alternative: Using `conda`

The legacy Conda environment definition is preserved in `fv_environment.yml`:
```bash
conda env create -f fv_environment.yml
conda activate fv
```

## Demo Notebook
Checkout `notebooks/fv_demo.ipynb` for a Jupyter notebook with a demo of how to create a function vector and use it in different contexts.

To launch Jupyter with `uv`:
```bash
uv run jupyter notebook
```
or launch JupyterLab:
```bash
uv run jupyter lab
```


## Data
The datasets used in our project can be found in the `dataset_files` folder.

## Code
Our main evaluation scripts are contained in the `src` directory with sample script wrappers in `src/eval_scripts`.

Other main code is split into various util files:
- `eval_utils.py` contains code for evaluating function vectors in a variety of contexts
- `extract_utils.py`  contains functions for extracting function vectors and other relevant model activations.
- `intervention_utils.py` contains main functionality for intervening with function vectors during inference
- `model_utils.py` contains helpful functions for loading models & tokenizers from huggingface
- `prompt_utils.py` contains data loading and prompt creation functionality

## Citing our work
This work appeared at ICLR 2024. The paper can be cited as follows:

```bibtex
@inproceedings{todd2024function,
    title={Function Vectors in Large Language Models}, 
    author={Eric Todd and Millicent L. Li and Arnab Sen Sharma and Aaron Mueller and Byron C. Wallace and David Bau},
    booktitle={The Twelfth International Conference on Learning Representations},
    url={https://openreview.net/forum?id=AwyxtyMwaG},
    note={arXiv:2310.15213},
    year={2024},
}
