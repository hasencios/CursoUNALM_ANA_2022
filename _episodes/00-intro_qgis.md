---
title: "Introducción a QGIS"
teaching: 30
exercises: 30
questions:
- ¿Cómo cargar información vectorial y raster en QGIS?
- ¿Cómo crear información georreferenciada en QGIS?
objectives:
- Acceder a QGIS y cargar información vectorial y raster
- Generar campos para almacenar información de área y perimétro de un polígono
- Crear un shapefile de puntos y determinar sus coordenadas
keypoints:
- "QGIS nos permite la visualización de información geoespacial que representa ciertas características de la realidad."
---
## Objetivos del Módulo I

Al finalizar el módulo cada alumno deberá de presentar mapas de las variables más importantes de su cuenca (precipitación, temperatura, LULC, clases de suelo, índices espectrales, etc), tal como se muestra a continuación:

<figure>
  <img src="../fig/DEM_Lurin.png" style="width:60%">
</figure>

<br>

<figure>
  <img src="../fig/landuse_lurin.png" style="width:60%">
</figure>

<br>

<figure>
  <img src="../fig/soil_lurin.png" style="width:60%">
</figure>

## Explorando QGIS y leyendo información vectorial

Vamos a esplorar QGIS y cargadar el shapefile de cuencas hidrográficas que ya hemos descargado.

<figure>
  <img src="../fig/00_QGIS_intro.png" style="width:100%">
</figure>

<br>

## Explorando Iri Data Library

En esta sección accederemos a la base de datos del producto grillado [PISCO](https://www.tandfonline.com/doi/abs/10.1080/02626667.2019.1649411). Para ello, vamos a ingresar a la siguiente website:

  * Acceder a través de la web [Iri Data Library](https://iridl.ldeo.columbia.edu/)
  
![RStudio layout](../fig/06-rmd-iridatalibrary.png)

* Esta parte del procedimiento se realizará en misma web donde se aloja el producto PISCO
* Se debe descargar el producto PISCO precipitación y temperatura máxima y mínima y guardar en la carpeta de trabajo (data)

## Leyendo la base de datos descargada

<figure>
  <img src="../fig/qGIS_Intro.png" style="width:100%">
</figure>

<br>

> ## Sugerencia
>
> La ruta donde se localiza nuestra carpeta de trabajo no debe contener espacios
> ni caracteres a fin de evitar problemas en lo sucesivo. Dentro de ésta
> se debe de tener subcarpetas con los siguientes nombres:
> 
> * `/code`: donde guardemos los **scripts** que vayamos generando
> * `/data`: donde almacenemos la base de datos que vamos a descargar 
> * `/result`: donde guardemos los archivos y gráficos generados
> * `/shp`: donde guardemos los vectoriales
> * `/raster`: donde guardemos los archivos raster
> * `/qgis`: donde guardemos el proyecto QGIS
>
{: .callout}
