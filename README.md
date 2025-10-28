🚀 Overview

This repository turns Chapter 4 into a hands-on learning resource.
You’ll find one notebook per subtopic, concise cheat-sheets, hands-on exercises, and a final mini-project implementing random walks.

Chapter 4 topics covered

4.1 The ndarray — Multidimensional array object

4.2 Pseudorandom number generation

4.3 Universal functions (ufuncs)

4.4 Array-oriented programming with arrays

4.5 File I/O with arrays

4.6 Linear algebra

4.7 Example: Random Walks (mini-project)

📚 Notebooks (Open in Colab)

All notebooks live under notebooks/ in this repo (branch main). Click a badge to open in Colab.

04.1_ndarray.ipynb — The NumPy ndarray


04.2_random_numbers.ipynb — Pseudorandom number generation


04.3_ufuncs.ipynb — Universal functions (ufuncs)


04.4_array_programming.ipynb — Array-oriented programming patterns


04.5_file_io.ipynb — File input/output with np.save / np.load / savetxt


04.6_linear_algebra.ipynb — numpy.linalg essentials


04.7_random_walks.ipynb — Example: Random Walks (mini-project)


🔍 Quick summaries (what each notebook contains)
4.1 — The ndarray

Array construction, indexing, shape, dtype, broadcasting basics.

Key: np.array, np.asarray, np.arange, reshape, ndim, astype.

Exercises: reshape, transpose, boolean indexing.

4.2 — Pseudorandom Number Generation

Use the modern Generator API: np.random.default_rng.

Key: integers, random, choice, normal.

Exercises: simulate coin flips, Monte Carlo estimations.

4.3 — Universal functions (ufuncs)

Vectorized elementwise ops, broadcasting, ufunc.reduce.

Key: np.add, np.multiply, np.sin, np.exp, np.where.

Exercises: moving average, performance comparisons.

4.4 — Array-Oriented Programming

Replace Python loops with vectorized ops (broadcasting, masking).

Patterns: boolean masking, np.newaxis, stacking.

Exercises: pairwise distances using broadcasting.

4.5 — File I/O with arrays

Save/load with np.save, np.savez_compressed, np.load, np.savetxt.

Exercises: compress and compare file sizes.

4.6 — Linear Algebra

Matrix ops, solving linear systems, eigenvalues, SVD.

Key: np.dot, np.matmul, np.linalg.solve, np.linalg.svd.

Exercises: PCA via SVD.

4.7 — Random Walks (mini-project)

Simulate many 1D random walks, compute positions with cumsum, analyze hitting times and distributions.

Exercises: first-passage times, distribution plots, optional animation.

💻 Quickstart — run everything locally

Clone

git clone https://github.com/QousainRaza/Numpy.git
cd Numpy


Create env & install

python -m venv .venv
# macOS / Linux
source .venv/bin/activate
# Windows
.venv\Scripts\activate

pip install -r requirements.txt


Open a notebook

jupyter notebook notebooks/04.7_random_walks.ipynb


Or click any Open in Colab badge above.

📦 requirements.txt (recommended)
numpy>=1.23
matplotlib
pandas
jupyterlab

🗂 Suggested repo structure
Numpy/
├── notebooks/
│   ├── 04.1_ndarray.ipynb
│   ├── 04.2_random_numbers.ipynb
│   ├── 04.3_ufuncs.ipynb
│   ├── 04.4_array_programming.ipynb
│   ├── 04.5_file_io.ipynb
│   ├── 04.6_linear_algebra.ipynb
│   └── 04.7_random_walks.ipynb
├── data/                   # optional: saved arrays, example datasets
├── requirements.txt
├── README.md
└── LICENSE

✅ Example: Random Walk (quick runnable snippet)

Paste into any notebook cell to try an experiment:

import numpy as np
import matplotlib.pyplot as plt

rng = np.random.default_rng(42)
n_steps = 1000
n_walks = 200

steps = rng.choice([-1, 1], size=(n_walks, n_steps))
positions = steps.cumsum(axis=1)

final_positions = positions[:, -1]
print("Mean final position:", final_positions.mean())
print("Std of final positions:", final_positions.std())

plt.figure(figsize=(10,5))
for i in range(10):
    plt.plot(positions[i], alpha=0.8)
plt.xlabel('Step')
plt.ylabel('Position')
plt.title('First 10 Random Walks (1D)')
plt.grid(True)
plt.show()

✅ Exercises & Mini-Projects (suggested)

Vectorized vs loop implementations (performance comparison).

Monte Carlo estimation of π.

Save simulation outputs with np.savez_compressed and inspect file sizes.

PCA from scratch using np.linalg.svd.

Random Walk: analyze first-passage times and maximum displacement distributions.

🤝 Contributing

Contributions, fixes, and additional exercises welcomed!
Workflow:

Fork → create a branch → open a PR.
Please include a short description in PR and clear commit messages.

Issues: https://github.com/QousainRaza/Numpy/issues

Pull requests: https://github.com/QousainRaza/Numpy/pulls

📖 Credits & References

Python for Data Analysis — Wes McKinney (Chapter 4)

NumPy docs — https://numpy.org/doc/

🧾 License & Contact

License: MIT — see LICENSE.
Author: Qousain Raza — update the repo contact details if you want additional contact info.
