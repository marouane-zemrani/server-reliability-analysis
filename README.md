# Server Reliability Analysis & Preventive Maintenance

**Academic statistics project | EMINES, Mohammed VI Polytechnic University (UM6P) | 2025–2026**

This project explores how statistical lifetime models can be used to analyze equipment reliability and support preventive maintenance decisions. The case study considers a **hypothetical fleet of 1,000 servers**, using simulated failure times rather than real industrial data.

The original group report and presentation are in French. The Jupyter notebook provides a **standalone English explanation and Python implementation** of the main methods developed in those documents.

## What the notebook covers

- **Probability foundations:** exponential distribution, memoryless property, survival functions, hazard rates, and Weibull/Erlang models.
- **Reliability analysis:** simulation of Weibull lifetimes, empirical survival and failure-hazard estimates.
- **Parameter estimation:** Weibull probability plot and maximum likelihood estimation (MLE).
- **System architecture:** reliability of independent components in series and in parallel.
- **Maintenance decisions:** residual lifetime and a conditional failure-risk threshold.
- **Model comparison:** Weibull, exponential, and Erlang distributions.
- **Statistical inference:** nonparametric bootstrap, likelihood-ratio test, bootstrap Kolmogorov–Smirnov tests, and a bootstrap-calibrated Pearson goodness-of-fit test.

**Tools:** Python, NumPy, pandas, SciPy, Matplotlib, and Jupyter.

## Repository structure

```text
server-reliability-analysis/
├── README.md
├── requirements.txt
├── server_reliability_analysis.ipynb
└── docs/
    ├── rapport_statistique_original.pdf          # Original group report (French)
    └── presentation_statistique_originale.pdf     # Original group slides (French)
```

## Run the analysis

Requires **Python 3.10+**.

```bash
python -m venv .venv
```

Activate the environment:

- **Windows (PowerShell):** `.venv\Scripts\Activate.ps1`
- **macOS / Linux:** `source .venv/bin/activate`

Then install dependencies and start Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter lab
```

Open `server_reliability_analysis.ipynb` and run the cells from top to bottom. The notebook displays the results and figures directly; **no external dataset is required**. Bootstrap-based tests may take longer to run.

## Reproducibility and interpretation

The original simulated sample and random seed were not preserved. The notebook therefore generates a **new reproducible sample** from a Weibull distribution with shape **β = 2** and scale **η = 3 thousand hours**. Its numerical results **will not necessarily match** those in the original French report or slides. The goal is to reproduce the methods, not to force the original numerical outputs.

The French PDF documents are historical academic deliverables; some of their numerical statements contain inconsistencies. The notebook recomputes its own results and includes checks and methodological caveats. In particular, a risk-based replacement threshold **is not** a proven economically optimal maintenance policy, and fitting a simulated Weibull sample does not validate the model for real servers.

## Credits

Original group project: **Saif Eddine Kaddouri, Marouane Zemrani, Yassine Hannane, and Youssef Laabadi**.  
Supervisor: **Abdelkrim Alahyane**.  

The English notebook is a subsequent reimplementation based on the original group work, not a recovery of the original code.
