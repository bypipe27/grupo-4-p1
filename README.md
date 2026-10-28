# Grupo 4 - Proyectos 2 y 3

¿Quién termina hospitalizado por dengue? Análisis exploratorio, limpieza, modelos predictivos y segmentación de 581,071 casos de dengue notificados al SIVIGILA entre 2022 y 2025.

- **Variable objetivo:** `PAC_HOS` (hospitalización registrada) -> clasificación binaria.
- **Modelos supervisados:** Regresión Logística, Árbol de Decisión y Random Forest (modelo final).
- **Modelo no supervisado:** K-Means (k = 4), comparado con clustering jerárquico de Ward.

## Requisitos

- Python 3.10 o superior.
- El archivo `datos/procesados/dengue_consolidado.parquet` (consolidado del Proyecto 1, incluido en el repositorio).

## Preparar el entorno

En la raíz del proyecto:

Windows (PowerShell):

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\Activate.ps1
```

Linux / macOS:

```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
source .venv/bin/activate
```

## Ejecutar los notebooks

Los notebooks usan rutas relativas a la carpeta `entrega/`, así que deben abrirse desde ahí (en VS Code basta con abrirlos y elegir el intérprete de `.venv`):

```bash
jupyter notebook entrega/
```

Ejecutarlos en orden, cada uno de principio a fin:

| Fase | Notebook | Qué hace | Tiempo aprox. |
|---|---|---|---|
| A | `fase_a_eda.ipynb` | EDA: histogramas, boxplot, correlaciones de Pearson y Spearman, serie semanal, departamentos y hospitalización por edad, cada gráfico con su `Insight:` | < 1 min |
| B | `fase_b_limpieza.ipynb` | Diagnóstico, split 80/20 antes de transformar, imputación (mediana y KNN), outliers (IQR), Yeo-Johnson, One-Hot/Ordinal, escalado; genera `datos_limpios.parquet` | ~ 1 min |
| C | `fase_c_modelos.ipynb` | 3 modelos supervisados con `GridSearchCV`, tabla comparativa, matrices de confusión, ROC, umbral, validación temporal, K-Means y conclusiones | ~ 20 min |

La Fase C necesita el `datos_limpios.parquet` que produce la Fase B (ya incluido en `entrega/`).

## Entregables (`entrega/`)

- `fase_a_eda.ipynb` y `fase_a.odt` (3 hallazgos principales).
- `fase_b_limpieza.ipynb`, `fase_b_documento.docx` (pasos y justificación) y `datos_limpios.parquet`.
- `fase_c_modelos.ipynb`.
- `informe_p2p3.pdf` (informe final) y `presentacion.pdf`.
