# ¿Qué es la comparación SQL vs NoSQL?

La comparación entre bases de datos SQL (relacionales) y NoSQL (no relacionales) permite entender las diferencias estructurales y comportamentales entre dos paradigmas de almacenamiento de datos. SQL utiliza tablas con esquemas fijos y relaciones definidas, mientras que NoSQL ofrece flexibilidad con documentos, gráficos o estructuras clave-valor sin esquemas rígidos.

# Importancia de entender ambos modelos

Comprender las diferencias entre SQL y NoSQL es fundamental para tomar decisiones arquitectónicas correctas. Cada modelo tiene ventajas específicas: SQL para datos estructurados con relaciones complejas, y NoSQL para escalabilidad, flexibilidad y datos semi-estructurados. La elección incorrecta puede afectar el rendimiento, mantenimiento y escalabilidad de una aplicación.

# Implementación del notebook comparativo

## Simulación SQL (estructura rígida)
```python
import pandas as pd
import numpy as np

# Datos con esquema fijo - como cartas de una baraja
sql_df = pd.DataFrame({
    'id': range(1, 201),
    'nombre': [f"Usuario_{i}" for i in range(200)],
    'edad': np.random.randint(18, 65, size=200),
    'email': [f"usuario{i}@ejemplo.com" for i in range(200)]
})
```

## Simulación NoSQL heterogéneo
```python
# Documentos con diferentes campos - como hojas de cuaderno variadas
documentos_nosql = []
for i in range(200):
    doc = {'id': i+1, 'nombre': nombres[i], 'edad': int(edades[i])}
    if random.random() < 0.5:
        doc['email'] = emails[i]
    if random.random() < 0.3:
        doc['telefono'] = f"300{random.randint(1000000,9999999)}"
    documentos_nosql.append(doc)
```

## Visualizaciones implementadas
```python
# Gráfico de distribución de edades SQL
sns.histplot(sql_df['edad'], bins=15, kde=True, color='skyblue')

# Gráfico de heterogeneidad NoSQL
conteo_campos = Counter(campos)
sns.barplot(x=list(conteo_campos.keys()), y=list(conteo_campos.values()))
```

# Problemas encontrados y soluciones

- **Generación de datos sintéticos**: Se necesitaban 200 registros representativos. Se solucionó usando numpy.random con seed fijo para reproducibilidad.
- **Visualización de heterogeneidad**: Mostrar campos variables en NoSQL era complejo. Se usó Counter para contar apariciones de cada campo.
- **Analogías educativas**: Hacer el contenido didáctico requería metáforas claras. Se implementaron analogías de cartas, hojas y baldes.

# Herramientas utilizadas

- **pandas**: Creación y manipulación de DataFrames para simular tablas SQL
- **matplotlib/seaborn**: Generación de gráficos comparativos y visualizaciones
- **collections.Counter**: Conteo de frecuencias en estructuras NoSQL
- **random**: Generación de datos aleatorios para simular heterogeneidad

# Resultados obtenidos

- **Notebook educativo completo**: 4 secciones con código, visualizaciones y explicaciones
- **Datos sintéticos**: 200 registros en cada modelo para comparación válida  
- **Visualizaciones claras**: Histogramas, gráficos de barras y distribuciones
- **Analogías efectivas**: Metáforas de cartas, hojas y baldes para facilitar comprensión
- **Reflexión comparativa**: Análisis de ventajas y desventajas de cada modelo

# Análisis comparativo final

**SQL**: Ideal para datos estructurados, integridad referencial y consultas complejas. Como una biblioteca ordenada donde todo tiene su lugar específico.

**NoSQL**: Perfecto para escalabilidad, flexibilidad de esquema y desarrollo ágil. Como una caja de archivo donde cada documento puede ser único.

**Conclusión**: La elección depende del caso de uso, tipo de datos y requisitos de escalabilidad del proyecto.

# Ejecución de la actividad

- Se creó el notebook notebook_sql_vs_nosql.ipynb con 200 registros sintéticos
- Se implementaron tres escenarios: SQL rígido, NoSQL heterogéneo y NoSQL homogéneo  
- Se generaron visualizaciones educativas para cada modelo
- Se incluyeron analogías didácticas y reflexión comparativa final