# Reporte de Actividad

## 1. Predicción de Estructura con AlphaFold2

El objetivo de esta actividad fue predecir la estructura terciaria de la proteína **CD300H**, la cual puede desempeñar un papel importante en la inmunidad innata al mediar una señal para la producción de un quimioatrayente de neutrófilos.

### Metodología
1.  **Obtención de la secuencia**: La secuencia de la proteína fue descargada de [UniProt](https://www.uniprot.org/uniprotkb/A0A0K2S4Q6/entry).
    *   Archivo FASTA: [`A0A0K2S4Q6.fasta`](./A0A0K2S4Q6.fasta)

2.  **Predicción**: Se utilizó esta secuencia como entrada para **AlphaFold2** mediante [ColabFold](https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/AlphaFold2.ipynb).
    *   Resultados de la predicción: [`results_alpha_fold2_CD300H/`](./results_alpha_fold2_CD300H/)

## 2. Validación de la Estructura

Posteriormente, se realizó un análisis de calidad de la estructura predicha. Para ello, se utilizó el modelo `test_d2d55_unrelaxed_rank_001_alphafold2_ptm_model_4_seed_000.pdb` como entrada para herramientas de validación estándar:

*   **SAVES**: Un "metaservidor" de validación estructural que evalúa la calidad y fiabilidad de una estructura 3D existente.
    *   Resultados: [`SAVES_results/`](./SAVES_results/)
*   **Swiss-Model**: Servidor automatizado de modelado por homología. Se utilizó su módulo de evaluación de estructura (Structure Assessment).
    *   Resultados: [`swiss_model_resuts/`](./swiss_model_resuts/)

## 3. Interpretación de Resultados

El análisis detallado e interpretación de los resultados obtenidos con las herramientas anteriores se encuentra en el siguiente documento:
*   [**Results.md**](./Results.md)
