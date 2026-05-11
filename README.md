# PhysicsML

Machine Learning applications (XGBoost + SHAP) across different domains of
physics. Each subproject lives in its own repository with isolated dependencies
and notebooks.

## Projects

| Project | Domain |
|---------|--------|
| [CosmoML](https://github.com/AlejandroMirRamos/CosmoML)   | Cosmology — SNe Ia (Pantheon+SH0ES, DES SN5YR) and BAO (DESI DR2) under ΛCDM, wCDM, w₀wₐCDM |
| [AlpsML](https://github.com/AlejandroMirRamos/AlpsML)     | Axion-like particles — UV models with `alpaca` and MCMC |
| [BMesonsML](https://github.com/AlejandroMirRamos/BMesonsML) | B meson physics — likelihoods with `flavio` / `wilson` |

## Common stack

All subprojects share the same ML pattern:

- **XGBoost** as a surrogate for χ² (or a derived target).
- **SHAP** to interpret feature importance and parameter degeneracies.
- Jupyter notebooks as the interface, with reusable logic in an importable
  package per subproject.

Domain-specific dependencies (`astropy`, `alpaca`, `flavio`, `wilson`, …) are
kept isolated in each repo's `requirements.txt` / `pyproject.toml`.
