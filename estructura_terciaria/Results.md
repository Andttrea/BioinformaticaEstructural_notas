# Interpretación de Resultados ALphaFold 2

## Resultados de SAVES v6.1

La herramienta SAVES (Structural Analysis and Verification Server) proporciona una validación integral de la estructura proteica.

![Resultados SAVES](SAVES_results/saves_result.png)

Los resultados obtenidos muestran:

*   **ERRAT**: El factor de calidad general es de **70.4403**. ERRAT analiza las estadísticas de interacciones no enlazadas entre diferentes tipos de átomos. Un valor más alto indica una mejor calidad, por lo que 70.44 puede indicar  que existen regiones en la estructura que podrían requerir refinamiento o que el modelo tiene cierta incertidumbre en el empaquetamiento atómico.
*   **VERIFY 3D**: Por su parte, el resultado es **FAIL**. Solo el **36.32%** de los residuos tienen una puntuación promediada 3D-1D >= 0.1. Verify3D evalúa la compatibilidad del modelo atómico (3D) con su propia secuencia de aminoácido. Para poder pasar la prueba, al menos el 80% de los aminoácidos deberían tener una puntuación >= 0.1. Este resultado bajo nos sugiere que una parte significativa del modelo podría tener un entorno local incorrecto o estar mal plegada en relación con la secuencia.

## Resultados de Swiss-Model Structure Assessment

Swiss-Model proporciona métricas adicionales para evaluar la calidad estereoquímica y geométrica del modelo.

### MolProbity

![MolProbity Results](swiss_model_resuts/MolProbity%20Results.png)

*   **MolProbity Score**: Nuestro score dado fue de **3.38**. El **MolProbity Score** es una puntuación combinada de calidad proteica que refleja la resolución cristalográfica a la que se esperaría tal calidad. El objetivo es tener una puntuación baja. Un valor de 3.38 sugiere una calidad moderada, que puede ser comparable con estructuras cristalinas de resolución media-baja.

### QMEAN y QMEANDisCo

![QMEANDisCo](swiss_model_resuts/QMEANDisCo.png)

**QMEANDisCo Global**: Nuestro score fue de **0.46 ± 0.06**.
    
* **QMEAN** (Qualitative Model Energy Analysis) es un estimador compuesto basado en diferentes propiedades geométricas. Este proporciona estimaciones de calidad absoluta tanto globales, para toda la estructura. como locales (por residuo) sobre la base de un único modelo. El valor oscila entre **0 y 1**, donde un valor más cercano a **1** indica una mejor calidad y mayor similitud con estructuras experimentales nativas.
Nuestro valor de 0.46 indica una calidad relativamente baja en comparación con estructuras experimentales de referencia, esto coincide con los hallazgos de Verify3D.


### Gráfico de Ramachandran

![Ramachandran Plot](swiss_model_resuts/ramachandran_plot.png)

El gráfico de Ramachandran visualiza los ángulos diedros $\phi$ (phi) y $\psi$ (psi) de la columna vertebral de la proteína. Idealmente los puntos (que representan cada residuo) deben "caer" dentro de los contornos verdes oscuros (regiones favorecidas) o verdes claros (regiones permitidas), que corresponden a conformaciones energéticamente estables para hélices alfa y láminas beta.

En el gráfico observado, la mayoría de los puntos se encuentran en las regiones favorecidas, lo cual es positivo. Sin embargo, se observan algunos residuos en las regiones blancas, lo que indica posibles distorsiones estereoquímicas o tensiones en el esqueleto del modelo en esas posiciones específicas.

### Alineamientos y Estructura

![Alineamiento](swiss_model_resuts/Alineamientos.png)

El alineamiento muestra la cobertura de la secuencia y la estructura secundaria predicha. Las regiones azules y cilindros representan hélices alfa, y las flechas púrpuras láminas beta. La altura de las barras indican la confianza o conservación en esas posiciones.

![Estructura 3D](swiss_model_resuts/structure.png)

La visualización 3D final muestra el plegamiento global predicho, donde podemos apreciar dominios con estructuras secundarias definidas (hélices y láminas) conectados por bucles.
