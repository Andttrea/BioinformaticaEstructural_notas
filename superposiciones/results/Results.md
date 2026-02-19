# Resumen de Resultados

Se realizó un análisis de superposición estructural en dos pares diferentes de proteínas utilizando el script de python indicad "prog3.1.py". Los resultados muestran valores variables de identidad de secuencia y desviación cuadrática media (RMSD), indicando diferentes grados de similitud estructural y de secuencia entre los pares analizados.

### Tabla de Resultados

| Par de Estructuras | Residuos Totales | Residuos Alineados | Identidad de Secuencia | RMSD |
|:-:|:-:|:-:|:-:|:-:|
| 2JUHcif por 2AJEcif | 121 / 97 | 97 | 79.38% | 10.61 Å |
| 2ROHcif MODEL_20 por 2ROHcif MODEL_1 | 122 / 122 | 96 | 71.88% | 25.10 Å |


### Primera Comparación: 2JUHcif por 2AJEcif

Esta superposición presenta una identidad de secuencia moderada del 79.38%, con 97 residuos alineados. La estructura 2JUHcif contiene 121 residuos mientras que 2AJEcif posee 97 residuos, esto sugiere que las proteínas tienen longitudes diferentes. El RMSD de 10.61 Ångströms indica una desviación estructural notable entre las dos proteínas, implicando que aunque comparten una buena proporción de residuos idénticos, sus conformaciones tridimensionales presentan diferencias significativas.

### Segunda Comparación: 2ROHcif MODEL_20 por 2ROHcif MODEL_1

Para este caso, se compararon dos modelos estructurales diferentes de la misma proteína (2ROHcif). Aunque ambas estructuras tienen la misma longitud, 122 residuos, solo 96 residuos fueron alineados correctamente. La identidad de secuencia es de 71.88%, lo que la hace menor comparada con el primer par, indicando variaciones significativas entre los modelos. El RMSD de 25.10 Ångströms es substancialmente más alto, sugiriendo que estos dos modelos presentan conformaciones muy diferentes a pesar de provenir de la misma proteína.

## Interpretación

La identidad de secuencia mide el porcentaje de residuos aminoacídicos idénticos en posiciones equivalentes después del alineamiento. El RMSD (Root Mean Square Deviation) cuantifica la desviación promedio entre átomos correspondientes. Los resultados indican que:

- **Caso 1**: Moderada similitud de secuencia con desviación estructural notable
- **Caso 2**: Menor similitud de secuencia con desviación estructural substancial, posiblemente debida a diferentes conformaciones o variables en el modelado