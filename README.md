<<<<<<< HEAD
# ADSO-2901817
ADSO-2901817
=======
# Hola, Soy xTheSnopxx|! 👋

![GitHub followers](https://img.shields.io/github/followers/xTheSnopx?style=for-the-badge)

---
## Collab Work Submissions

¡Hola! Este repositorio contiene tareas de **Google Colab** en las que uso **Python** para el análisis y la visualización de datos.

En estos proyectos, trabajamos con conjuntos de datos, realizamos limpiezas, generamos estadísticas descriptivas y creamos diferentes tipos de gráficos con **pandas** y **matplotlib**.

--

## 📥 Cómo usar

1. Descarga el notebook `.ipynb` de este repositorio.
2. Abre [Google Colab](https://colab.research.google.com/).
3. Sube el archivo del notebook a Colab.
4. Ejecuta las celdas para reproducir el análisis y las visualizaciones.
5. También puedes adaptar el código a tus propios conjuntos de datos.

--

## 📊 Fragmento de código de ejemplo
x|
```python
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv('/content/validation.csv')

# Preview first rows
df.head()

# Example: Histogram of 'NCBIGeneID'
df['NCBIGeneID'].plot(kind='hist', bins=20, title='NCBIGeneID Distribution', figsize=(12, 6),
                      color='skyblue', edgecolor='black', rwidth=0.8)
plt.xlabel('NCBIGeneID')
plt.ylabel('Frequency')
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.show()
>>>>>>> 098453b (Archivo README, Entrega De Los trabajos De La Sesion 1)
