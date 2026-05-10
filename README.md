# PhysicsML

Aplicaciones de Machine Learning (XGBoost + SHAP) a distintos ámbitos de la
física. Cada subproyecto vive en su propio repositorio con sus dependencias y
notebooks independientes.

## Proyectos

| Proyecto | Ámbito | Estado |
|----------|--------|--------|
| [CosmoML](https://github.com/AlejandroMirRamos/CosmoML)   | Cosmología — SNe Ia (Pantheon+SH0ES, DES SN5YR) y BAO (DESI DR2) en ΛCDM, wCDM, w₀wₐCDM | en desarrollo |
| [AlpsML](https://github.com/AlejandroMirRamos/AlpsML)     | Axion-like particles — modelos UV con `alpaca` y MCMC | hecho |
| [BMesonsML](https://github.com/AlejandroMirRamos/BMesonsML) | Física de mesones B — likelihoods con `flavio`/`wilson` | pendiente |

## Pila común

Todos los subproyectos comparten el patrón ML:

- **XGBoost** como surrogate del χ² (o de un target derivado).
- **SHAP** para interpretar la importancia y degeneraciones entre parámetros.
- Notebooks Jupyter como interfaz, con la lógica reutilizable en un paquete
  importable por subproyecto.

Las dependencias específicas de cada dominio (`astropy`, `alpaca`, `flavio`,
`wilson`, …) se mantienen aisladas en el `requirements.txt` / `pyproject.toml`
de cada repo.
