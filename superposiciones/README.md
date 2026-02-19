# Reporte de la actividad

## 1. Selección de dominios en CATH

Primero visitamos CATH (https://www.cathdb.info), una base de datos biológica de acceso público que clasifica, de forma jerárquica, las estructuras de dominios de proteínas (las unidades funcionales y estructurales que las componen).

A partir de esta base de datos, escogimos un clúster perteneciente a una superfamilia CATH que contenía 12 dominios.

## 2. Búsqueda de similitudes estructurales con Foldseek

Posteriormente, alineamos los dominios seleccionados utilizando Foldseek (https://search.foldseek.com/foldmason). Foldseek es una herramienta de bioinformática diseñada para buscar estructuras de proteínas similares en bases de datos masivas de forma rápida y eficiente.

Los resultados obtenidos con Foldseek (foldmason) se encuentran en la carpeta:

- [foldmason](./foldmason/)

## 3. Selección de parejas de estructuras

Para calcular el porcentaje de identidad y el RMSD seleccionamos aleatoriamente dos parejas de estructuras presentes en el Guide Tree generado por Foldseek.

Las parejas escogidas (registradas en [emparejamiento.txt](./emparejamiento.txt)) fueron:

- Par 1:
	- 2JUHcif_MODEL_2_A
	- 2AJEcif_MODEL_6_A
- Par 2:
	- 2ROHcif_MODEL_20_A
	- 2ROHcif_MODEL_1_A

A continuación, descargamos los archivos PDB correspondientes a estas secuencias.

## 4. Scripts utilizados

Utilizamos el script proporcionado por el Dr. Bruno Contreras, disponible en:

- https://github.com/eead-csic-compbio/bioinformatica_estructural/blob/master/code/prog3.1.py

Además, empleamos un script basado en [SVD](./src/SVD.py) para la superposición estructural.

El archivo `prog3.1.py` fue guardado localmente con el nombre [indentity_rmsd.py](./src/indentity_rmsd.py).

## 5. Modificación del script para calcular identidad y RMSD

Modificamos el script prog3.1.py para:

- Calcular el porcentaje de identidad entre dos secuencias alineadas.
- Calcular el RMSD entre las estructuras correspondientes.
- Imprimir ambos resultados por pantalla.

Se añadió la función calcular_identidad, que:

- Compara las secuencias aminoácido por aminoácido en un alineamiento.
- Cuenta el número de posiciones con aminoácidos idénticos.
- Calcula el porcentaje de identidad como:

% identidad = (número de posiciones idénticas / número total de posiciones comparables) × 100

Este valor refleja el grado de similitud evolutiva entre las proteínas: un porcentaje alto sugiere que las proteínas son muy parecidas y, probablemente, comparten funciones similares.

## 6. Ejecución del análisis

Como input utilizamos las secuencias de las dos parejas seleccionadas previamente. El programa se ejecutó dos veces:

- Una vez para la pareja 2JUHcif_MODEL_2_A vs 2AJEcif_MODEL_6_A.
- Una vez para la pareja 2ROHcif_MODEL_20_A vs 2ROHcif_MODEL_1_A.

En cada ejecución se obtuvo el porcentaje de identidad y el RMSD correspondientes.

## 7. Resultados

Los resultados numéricos del análisis se encuentran en la carpeta:

- [results](./results/)

En la misma carpeta se incluye, además, un [archivo Markdown](./results/Results.md) con la interpretación de dichos resultados.