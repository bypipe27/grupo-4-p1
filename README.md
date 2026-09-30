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
