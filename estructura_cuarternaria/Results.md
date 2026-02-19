# Interpretación de Resultados AlphaFold 3

A continuación, se presentan los resultados de la evaluación de calidad utilizando Swiss-Model Structure Assessment para el caso donde hubo un recorte de la secuencia, como en el que no. 


## Resultados para la Secuencia Trimeada (NANOG_trimmed)

Este modelo se centra en el homeodominio de unión al ADN, excluyendo las regiones desordenadas.

### MolProbity

![MolProbity Trimeada](swiss_model/NANOG_trimmed/MolProbity%20Results.png)

*   **MolProbity Score**: El puntaje obtenido es de **1.68**. Este es un muy buen resultado, dado que el objetivo es obtener una puntuación baja, un valor de 1.68 indica una calidad estereoquímica muy alta, comparable a estructuras cristalinas de alta resolución. Esto sugiere que el empaquetamiento de las cadenas laterales y la geometría local son muy precisos en este dominio estructurado.

### QMEANDisCo

![QMEANDisCo Trimeada](swiss_model/NANOG_trimmed/QMEANDisCo.png)

*   **QMEANDisCo Global**: El puntaje obtenido es de **0.67 ± 0.11**.
    Aunque no llega a valores cercanos a 1, un puntaje de 0.67 es significativamente mejor que el obtenido para la secuencia completa o para modelos de baja calidad. El gráfico de calidad local muestra que la mayoría de los residuos en esta región central tienen una similitud predicha local con el objetivo alta (barras azules por encima de 0.7-0.8), esto nos que indica que el núcleo del homeodominio está muy bien modelado y es confiable.

### Gráfico de Ramachandran

![Ramachandran Trimeada](swiss_model/NANOG_trimmed/Ramachandran_plot.png)

El gráfico muestra una conformación muy limpia. Observamos que la gran mayoría de los residuos (puntos) se encuentran dentro de las regiones verde oscuro (favorecidas). No se observan apenas residuos en zonas prohibidas (blancas), lo que confirma que la columna vertebral del modelo trimeado adopta conformaciones energéticamente estables y estereoquímicamente correctas, típicas de hélices alfa bien formadas.

### Estructura 3D

![Estructura Trimeada](swiss_model/NANOG_trimmed/structure.png)

La visualización muestra claramente el homeodominio interactuando con el surco mayor del ADN. Observamos que la estructura es compacta y bien definida. 

Podemos observar como esta estructura se parece a la estructura encontrada en Uniprot.

![Estructura Cristalográfica](results_alpha_fold3/proteina_pbd.png) 


---

## Resultados para la Secuencia Completa (NANOG_full)

Este modelo incluye la secuencia aminoacídica completa, incluyendo los dominios desordenados N- y C- terminales.

### MolProbity

![MolProbity Full](swiss_model/NONOG_full/MolProbity%20Results.png)

*   **MolProbity Score**: El puntaje obtenido es de **2.60**. Aunque sigue siendo un valor razonable, es notablemente peor (más alto) que el de la versión trimeada (1.68). Este aumento se debe probablemente a colisiones estéricas o geometría subóptima en las largas colas desordenadas que AlphaFold intenta modelar, pero que carecen de una estructura estable definida.

### QMEANDisCo

![QMEANDisCo Full](swiss_model/NONOG_full/QMEANDisCo.png)

*   **QMEANDisCo Global**: El puntaje cae a **0.42 ± 0.05**.
    Este valor bajo es engañoso si se evalúa la proteína completa como un todo. Como podemos observar en el gráfico de calidad local (Local Quality Estimate), hay una "isla" central de alta calidad, este se muestra por las barras azules altas,  que corresponde al homeodominio bien plegado. Sin embargo, los extremos N- y C- terminales muestran barras naranjas muy bajas (calidad < 0.4 o 0.5), lo que indica que estas regiones son intrínsecamente desordenadas y el modelo tiene muy baja confianza en su posición espacial. 

### Gráfico de Ramachandran

![Ramachandran Full](swiss_model/NONOG_full/Ramachandran_plot.png)

A diferencia del gráfico "limpio" de la versión trimeada, aquí observamos una dispersión mucho mayor de puntos. Muchos residuos caen en las regiones permitidas (verde claro) o incluso no favorecidas, lo cual es característico de regiones desordenadas y flexibles que no adoptan una estructura secundaria fija. Aunque el núcleo estructurado sigue estando bien, el "ruido" de las colas desordenadas domina la visualización.

### Estructura 3D

![Estructura Full](swiss_model/NONOG_full/structure.png)

La imagen muestra el homeodominio compactado unido al ADN (similar a la versión trimeada), pero rodeado de largas cadenas extendidas (en naranja) que representan las regiones desordenadas predichas con baja confianza (pLDDT bajo). Esta visualización confirma por qué las métricas globales son inferiores: la mayor parte de la masa de la proteína no tiene una estructura fija.
