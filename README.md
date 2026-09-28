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
```

En VS Code, seleccionar el interprete `.venv\Scripts\python.exe` y abrir `entrega/fase_c_sql.ipynb`.

## Ejecutar la Fase C

Ejecutar las celdas en orden. El notebook carga el Parquet original directamente con DuckDB y presenta seis consultas SQL analiticas, cada una con su tabla e interpretacion. La ruta se resuelve automaticamente desde la raiz del proyecto o desde la carpeta `entrega`.
