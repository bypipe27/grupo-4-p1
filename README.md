# Grupo 4 - Proyecto 1

Prediccion de incidencia semanal de dengue por municipio.

## Requisitos

- Python 3.10 o superior.
- El archivo `datos/procesados/dengue_consolidado.parquet`.

## Preparar el entorno

En la raiz del proyecto, ejecutar:

```powershell
    py -m venv .venv
    .\.venv\Scripts\python.exe -m pip install -r requirements.txt
    .\.venv\Scripts\Activate.ps1
```

Si desea ejecutar una fase del proyecto específica, puede hacerlo
ejecutando en la terminal el comando:

    jupyter notebook entrega/fase_LETRA_etl.ipynb

Por ejemplo, si se quiere ejecutar el notebook de la fase B,
simplemente se ejecuta:

    jupyter notebook entrega/fase_b_etl.ipynb

Y se redireccionará al usuario al notebook, donde podrá ejecutar
las celdas.

## Ejecutar la Fase C

En VS Code, seleccionar el interprete `.venv\Scripts\python.exe` y abrir `entrega/fase_c_sql.ipynb`.

Ejecutar las celdas en orden. El notebook carga el Parquet original directamente con DuckDB y presenta seis consultas SQL analiticas, cada una con su tabla e interpretacion. La ruta se resuelve automaticamente desde la raiz del proyecto o desde la carpeta `entrega`.

## Ejecutar la Fase D

En VS Code, seleccionar el kernel `Python (grupo-4-p1)` y abrir `entrega/fase_d_visualizaciones.ipynb`.

Ejecutar las celdas en orden. El notebook reutiliza las agregaciones de la Fase C y genera ocho visualizaciones con matplotlib y seaborn:

- Evolucion semanal nacional.
- Evolucion semanal de los cinco departamentos con mas registros.
- Comparacion de los diez municipios con mayor volumen.
- Perfil de registros por rango de edad y sexo.
- Porcentaje de hospitalizacion registrada por departamento.
- Distribucion univariada de edad.
- Relacion entre edad y hospitalizacion registrada.
- Comparacion de registros por categoria de area.

Cada figura incluye titulo, ejes con unidades y un bloque `Insight:` en Markdown. Las medidas son registros notificados; no se interpretan como tasas de incidencia o riesgo poblacional porque el Parquet no contiene denominadores de poblacion. Las categorias de `AREA` se mantienen como codigos originales para no asignarles etiquetas no documentadas en el dataset.
