## Notebooks

| Notebook | Topic | Colab |
|----------|-------|-------|
| Notebook 0 | PyTorch Fundamentals | [Open in Colab](https://colab.research.google.com/drive/11llJ3i4BvuWb9ykW06dAznlhYwAewDce?usp=sharing) |
| Notebook 1 | Linear Regression | [Open in Colab](https://colab.research.google.com/drive/1UK8rMGzpagspFNIVZ_zWJD1ScR7TrpOC?usp=sharing) |
| Notebook 2 | Shallow neural networks | [Open in Colab](https://colab.research.google.com/drive/1uPFXq9fNhVkeTlNVbd5uHRgE7JyhtmgY?usp=sharing) |
| Notebook 3 | Deep neural networks | [Open in Colab](https://colab.research.google.com/drive/1KZE1B-2D27JwI6JuED5ft2i_zIrU88Id?usp=sharing) |
| Notebook 4 | Loss functions and optimizers | [Open in Colab](https://colab.research.google.com/drive/1uFKNoaSDivH1jA4bCTE861WWaSfPOb3s?usp=sharing) |
| Notebook 5 | Measuring performance and regularization | [Open in Colab](https://colab.research.google.com/drive/1sI5nzFFFJ9C9aQxC3cR1ts_ImJwvM65Z?usp=sharing) |
| Notebook 6 | Convolutional and residual networks | [Open in Colab](https://colab.research.google.com/drive/1WLO-JorH95jIBc1nyb-5jR6EReSwAVqn?usp=sharing) |
| Notebook 7 | Transformers and attention mechanisms | [Open in Colab](https://colab.research.google.com/drive/1om_JDZE69eP6lxD6RsbFwA8cBx0nQ0BT?usp=sharing) |

---

## Running locally in VS Code / Cursor

### 1. Install VS Code / Cursor extensions

Install these two extensions:

- **Python** (`ms-python.python`) — Python language support
- **Jupyter** (`ms-toolsai.jupyter`) — notebook support, including kernel selection and cell execution

In VS Code/Cursor: open the Extensions panel (`Cmd+Shift+X`), search for each name, and click **Install**.

### 2. Install dependencies

This project uses [`uv`](https://docs.astral.sh/uv/) as the package manager.
If you don't have it yet:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Then, from the repo root, create a virtual environment and install all dependencies (including `ipykernel`, which lets VS Code/Cursor talk to the Python kernel):

```bash
uv sync
uv add ipykernel
```

This reads `pyproject.toml` and installs `torch`, `torchvision`, `matplotlib`, and `ipykernel` into `.venv/`.

### 3. Select the kernel in VS Code / Cursor

1. Open any `.ipynb` file.
2. Click **Select Kernel** in the top-right corner of the notebook.
3. Choose **Python Environments…** → select the `.venv` interpreter inside this repo (it will show the path ending in `.venv/bin/python`).

That's it. You can now run all cells with `Shift+Enter` or **Run All**.

### 4. Verify the setup

Run the first cell of `notebook_0.ipynb`. It should import `torch` without errors and print the installed version.

---

### Quick-reference: common issues

| Symptom | Fix |
|---------|-----|
| `ModuleNotFoundError: No module named 'torch'` | Wrong kernel selected — repeat step 3 |
| Kernel not listed | Run `uv add --dev ipykernel` and reload VS Code/Cursor |
| `uv` not found | Install uv (step 2) and restart your terminal |
