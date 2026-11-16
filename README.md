# Proyecto analítico · Desocupación 2025

Este proyecto mide cómo varía la tasa de desocupación entre regiones agrupadas, grupos de edad y sexos dentro del nivel medio, usando la base anual de la Encuesta Nacional de Empleo 2025 del INE. El cuaderno `cuaderno_entrega_final.ipynb` parte del archivo crudo, limpia los datos, calcula tasas ponderadas por `fact_anual`, verifica la estabilidad de los hallazgos con 60 mitades de personas y detecta casos extremos de horas y condición. Solo guarda agregados en `salidas/`, sin identificadores.

## Cómo ejecutarlo

1. Descargar `ano-2025.csv` (formato CSV, Año 2025) desde https://www.ine.gob.cl/docs/default-source/ocupacion-y-desocupacion/bbdd/bases-anuales/csv/ano-2025.csv?sfvrsn=ab6fa5e3_6&download=true y colocarlo en `data/ano-2025.csv`.
2. Crear un entorno con Python 3.12.3 e instalar `requirements.txt`: `pip install -r requirements.txt`.
3. Abrir `cuaderno_entrega_final.ipynb` y ejecutar **Kernel → Restart & Run All**. La semilla es 42; las particiones de robustez son 0 a 29.
4. Las salidas quedan en `salidas/`: figuras explicativas y tablas de tasas y robustez.

## Notas

- La base anual del INE tiene 390.903 registros; el panel de cuatro visitas tiene 118.760 registros y 29.690 personas.
- La robustez depende de la partición: con otra semilla base, la desviación de la razón entre regiones cambia de 0,45 a 0,20. Por eso se reporta junto con la semilla usada.
- La licencia y los términos de uso son los del INE; el archivo de datos no se redistribuye en este repositorio.
