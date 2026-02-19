# Reporte de Actividad

## 1. Predicción de Estructura con AlphaFold2

En esta actividad se realizó la predicción de la estructura cuaternaria del factor de transcripción **NANOG** utilizando **AlphaFold 3**. La secuencia de la proteína se obtuvo de UniProt ([Q9H9S0](https://www.uniprot.org/uniprotkb/Q9H9S0/entry#sequences)).

NANOG es un regulador maestro de la pluripotencia que mantiene la identidad de las células madre embrionarias, promoviendo su autorrenovación y bloqueando activamente su diferenciación hacia linajes celulares específicos.

### Secuencia de ADN
El factor de transcripción se modeló en complejo con una secuencia de ADN específica obtenida de la literatura:

```text
5' - GCGTAATGAGCTTAATGCGC - 3'
3' - CGCATTACTCGAATTACGCG - 5'
```

## Metodología

Se generaron dos modelos de predicción:
1.  **Modelo Completo (`NANOG_full`)**: Utilizando la secuencia completa de la proteína.
2.  **Modelo Recortado (`NANOG_trimmed`)**: Utilizando una secuencia parcial correspondiente al dominio de unión al ADN.

Se utilizó la secuencia recortada para realizar una comparación justa con la estructura cristalográfica de referencia. Las estructuras obtenidas mediante cristalografía de rayos X frecuentemente solo resuelven los dominios estructurados estables, omitiendo regiones desordenadas (como los extremos N- y C- terminales). 

El recorte corresponde a los residuos **94-162**, que coinciden con la región cristalizada reportada en UniProt. Al generar un modelo predicho que corresponde exactamente a esta región, eliminamos el "ruido" introducido por las largas colas desordenadas que AlphaFold predice con baja confianza (pLDDT bajo) y que distorsionarían las métricas globales de calidad.

El recorte de la secuencia se realizó con el siguiente comando:

```bash
grep -v "^>" Q9H9S0.fasta | awk '{printf $1}' | awk '{print substr($0,94,68)}'
```

## Archivos y Resultados

### Secuencias
Las secuencias utilizadas se encuentran en:
-   **Recortada**: [`Q9H9S0_trimmed.fasta`](results_alpha_fold3/Q9H9S0_trimmed.fasta)
-   **Completa**: [`Q9H9S0.fasta`](results_alpha_fold3/Q9H9S0.fasta)

### Evaluación de Calidad (Swiss-Model)
Para el análisis de calidad de los modelos predichos, utilizamos la herramienta [Swiss-Model Structure Assessment](https://swissmodel.expasy.org/assess).

**Archivos de entrada (Modelos AlphaFold):**
-   Recortado: [`fold_nanog_trimmed_model_0.cif`](results_alpha_fold3/fold_nanog_trimmed/fold_nanog_trimmed_model_0.cif)
-   Completo: [`fold_nanog_full_model_0.cif`](results_alpha_fold3/fold_nanog_full/fold_nanog_full_model_0.cif)

**Resultados de la evaluación:**
Los reportes de Swiss-Model se encuentran organizados en la carpeta [`swiss_model`](swiss_model):
-   **Trimmed**: [`NANOG_trimmed`](swiss_model/NANOG_trimmed)
-   **Full**: [`NONOG_full`](swiss_model/NONOG_full)

## Interpretación
El análisis detallado e interpretación de estos resultados se encuentra documentado en: [Results.md](Results.md).

