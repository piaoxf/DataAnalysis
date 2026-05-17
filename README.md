# DataAnalysis — MITx 6.419x

Python environment for MITx 6.419x: Data Analysis: Statistical Modeling and Computation in Applications.

## Environment

- Python 3.13.7 (system)
- venv at `.venv/`
- Jupyter kernel: **Python (DataAnalysis)** (name: `dataanalysis`)
- PyTorch with CUDA 12.6 (RTX 4060)

## Activate

```powershell
.\.venv\Scripts\Activate.ps1
```

If activation is blocked by execution policy:

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

Deactivate with `deactivate`.

## Launch JupyterLab

```powershell
.\.venv\Scripts\Activate.ps1
jupyter lab
```

In notebooks, select the **Python (DataAnalysis)** kernel.

## Install / update packages

```powershell
.\.venv\Scripts\python.exe -m pip install <pkg>
# or update requirements.txt and:
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

## Verify GPU

```python
import torch
print(torch.__version__, torch.cuda.is_available(), torch.cuda.get_device_name(0))
```
