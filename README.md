# PhysicsML

Interpretable Machine Learning (XGBoost + SHAP) for global fits in high energy
physics and cosmology. This repository gathers the code, Jupyter notebooks and
data behind the three applications presented in the accompanying paper, where an
XGBoost surrogate of the (generally non-Gaussian) log-likelihood accelerates
parameter-space exploration by several orders of magnitude while SHAP values keep
the inference physically interpretable.

Each subproject lives in its own repository with isolated dependencies and
provides the full pipeline used in the paper: training-set construction, XGBoost
surrogate training, SHAP analysis and MCMC sampling of the emulated posterior.

## Projects

| Project | Application |
|---------|-------------|
| [BMesonsML](https://github.com/AlejandroMirRamos/BMesonsML) | Flavour anomalies in semileptonic B-meson decays: surrogate of the `SMEFT19` global likelihood in Scenario III (C1, C3, βq), likelihood maps, SHAP ranking and observable correlations |
| [AlpsML](https://github.com/AlejandroMirRamos/AlpsML)     | Axion-like particles as a solution to the Belle II B⁺→K⁺νν̄ excess: UV models with PQ charges, `alpaca` likelihood, two-stage classifier + regressor surrogate and MCMC posterior |
| [CosmoML](https://github.com/AlejandroMirRamos/CosmoML)   | Cosmology: ΛCDM and w₀wₐCDM fits to SNe Ia (Pantheon+, DES-SN5YR) and BAO (DESI DR2) with a compressed Planck CMB prior; doubles as a controlled validation against the exact likelihood |

## Common stack

All subprojects share the same ML pattern:

- **XGBoost** trained as a surrogate of the χ² (or a transform of it chosen per
  application: direct log-likelihood, sigmoid classifier + regressor, or a
  shifted-log₁₀ target).
- **SHAP** to rank parameter importance and expose degeneracies, keeping the
  emulated fit interpretable.
- **MCMC** (Metropolis-Hastings or `emcee`) run on the emulated likelihood to
  map posteriors and confidence regions.
- Jupyter notebooks as the interface, with reusable logic in an importable
  package per subproject where needed.

Domain-specific dependencies (`astropy`, `alpaca`, `flavio`, `wilson`, `smelli`,
…) are kept isolated in each repo's `requirements.txt` / `pyproject.toml`.
