---
layout: post
title: INEGI Shapefiles
tags: geopandas
math: true
date: 2024-05-17 18:00 +0800
---
# Inegi Shapefiles

Este semestre tuve la oportunidad de hacer un proyecto que involucraba el uso de INEGI Shapefiles, a continuación compartiré un poco de cómo utilizarlos.

## ¿Qué es el INEGI?
El Instituto genera estadística básica, la cual obtiene de tres tipos de fuentes: censos, encuestas y registros administrativos, así como estadística derivada, mediante la cual produce indicadores demográficos, sociales y económicos, además de contabilidad nacional.

## ¿Qué es un shapefile?
Consiste en un conjunto de archivos que juntos representan datos geoespaciales vectoriales, es decir, datos que describen formas geométricas como puntos, líneas y polígonos, junto con atributos asociados.

## Tipos de geometría
- **Puntos:**  Representan ubicaciones específicas en el espacio utilizando coordenadas. Por ejemplo, puede representar un punto de interés en un mapa como un hospital o negocio.
- **Líneas:** Son secuencias de puntos conectados que representan elementos lineales, como carreteras, ríos o límites administrativos. 
- **Polígonos:** Son áreas cerradas formadas por una secuencia de líneas que se conectan para delimitar un área específica en el espacio. Por ejemplo, un polígono puede representar un país, un lago o un parque.

## Geopandas
GeoPandas extiende las capacidades de Pandas, una biblioteca muy popular para la manipulación de datos en Python, al agregar soporte para datos espaciales.

## Código
Después de que tengamos el Shapefile que vamos a analizar podemos hacer código.

Leer y creear el DataFrame:
```python
datos = gpd.read_file('camino_a_tu_shapefile.shp')
datos.head(5)
datos.tail(5)
```

Tipo:
```python
type(datos)
```

Conocer las columnas:
```python
datos.columns
```

Tipo de geometría:
```python
datos.geom_type
```

Graficar:
```python
datos.plot()
```

Cambiar índice por el de una columna:
```python
datos= datos.set_index("nuevo_index")
```

Solo obtener los datos de una columna:
```python
datos["columna"]
```

Dos columnas:
```python
datos[['columna1','columna2']]
```