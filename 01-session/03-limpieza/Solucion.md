# ¿Qué es la limpieza de datos?

La limpieza de datos es el proceso de identificar y corregir errores, inconsistencias y valores faltantes en un dataset. Este proceso incluye la eliminación de duplicados, corrección de formatos inconsistentes, tratamiento de valores nulos y normalización de datos. Es fundamental para garantizar la calidad de los datos antes de realizar análisis o entrenar modelos de machine learning.

# Importancia de la limpieza de datos

La limpieza de datos es crucial porque los datos sucios pueden llevar a conclusiones erróneas, modelos inexactos y decisiones de negocio incorrectas. Un dataset limpio mejora la confiabilidad de los análisis, aumenta la precisión de los modelos predictivos y garantiza que las insights obtenidos sean válidos. Estudios indican que los científicos de datos dedican entre 60-80% de su tiempo a la limpieza y preparación de datos.

# Proceso de limpieza implementado

## Importación del dataset
```python
from google.colab import drive
drive.mount('/content/drive')

import pandas as pd
ruta = '/content/drive/MyDrive/Colab Notebooks/Datasets/CovidDiagnosis.xlsx'
df = pd.read_excel(ruta)
```

## Exploración inicial
```python
df.info()                    # Información general del dataset
df.isnull().sum()           # Valores nulos por columna
df['Gender'].value_counts()  # Valores únicos en columnas categóricas
```

## Limpieza de valores nulos
```python
# Columna Age: Rellenar con mediana
mediana_edad = df['Age'].median()
df['Age'].fillna(mediana_edad, inplace=True)

# Columna Gender: Rellenar con moda
moda_genero = df['Gender'].mode()[0]
df['Gender'] = df['Gender'].fillna(moda_genero)
```

## Normalización de texto
```python
# Limpiar caracteres especiales con regex
import re
df['Gender'] = df['Gender'].apply(lambda x: re.sub(r'[^a-zA-Z]', '', str(x)))

# Estandarizar valores inconsistentes
df['Gender'] = df['Gender'].replace({
    'femenino': 'Femenino',
    'masculino': 'Masculino',
    'masculinoooo': 'Masculino'
})
```

# Problemas encontrados

- **Valores nulos en Age**: Se encontraron edades faltantes que afectaban el análisis estadístico. Se solucionó rellenando con la mediana para mantener la distribución original.
- **Valores nulos en Gender**: Registros sin género especificado. Se completaron con la moda (valor más frecuente).
- **Inconsistencias en Gender**: Valores como "masculinoooo", "masculino.....//", espacios extra y caracteres especiales. Se normalizaron usando expresiones regulares y reemplazos.
- **Formato inconsistente**: Mezcla de mayúsculas, minúsculas y caracteres especiales. Se estandarizó todo a formato título.

# Herramientas utilizadas

- **pandas**: Biblioteca principal para manipulación y análisis de datos
- **re (regex)**: Limpieza de texto con expresiones regulares
- **Google Colab**: Entorno de ejecución en la nube con acceso a Google Drive

# Resultados obtenidos

- **Dataset original**: Contenía valores nulos y inconsistencias en múltiples columnas
- **Valores nulos eliminados**: 0 valores nulos en todo el dataset
- **Columna Gender estandarizada**: Solo dos valores válidos: "Femenino" y "Masculino"
- **Dataset final**: CovidDiagnosis_LIMPIO.xlsx guardado sin errores
- **Calidad mejorada**: Dataset listo para análisis estadístico y modelado

# Ejecución de la actividad

- Se ejecutó todo el proceso en Google Colab con el dataset CovidDiagnosis.xlsx
- Se aplicaron técnicas de imputación, normalización y estandarización
- Se verificó la calidad final del dataset con df.info() y value_counts()
- El dataset limpio se guardó exitosamente en Google Drive como CovidDiagnosis_LIMPIO.xlsx