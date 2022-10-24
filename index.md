---
layout: lesson
root: .

maintainers:
  - Henry Asencios
---

**Lesson Maintainers:** {{ page.maintainers | join: ', ' }}

El Módulo I forma parte del Curso de Especialización en el Uso de Herramientas Hidrológicas e Hidrogeológicas en los Procedimientos de Evaluación Ambiental que ha sido diseñado por la [Facultad de Ingenieria Agrícola (FIA)](http://www.lamolina.edu.pe/facultad/agricola/) de la [Universidad Nacional Agraria La Molina (UNALM)](http://www.lamolina.edu.pe/) para los servidores de la [Autoridad Nacional de Agua (ANA)](https://www.ana.gob.pe/) que presentan conocimientos básicos  en SIG y de programación en el lenguaje **R** y/o **Python** para el manejo de series de tiempo hidrometeorológicas observadas y salidas de modelos de circulación global. 

Las lecciones tendrán una duración de 26 horas de trabajo y la finalidad de realizar la caracterización morfométrica de las cuencas de estudio, recopilar información temática, así como el manejo de series de tiempo de precipitación y temperatura extrema historica y futura, para diversos modelos y escenarios, que sirvan como imputs de los subsiguientes módulos de curso.

Se comenzará con una descripción general de **QGIS**, **R**, **Google Earth Engine (GEE)** y **Python**. Se discutirá acerca de la importancia del uso de herramientas de programación para la sistematización de los procesos de análisis de series de tiempo hidrometeorológicas, sus ventajas y limitaciones, la forma correcta de instalar y configurar, se mostrará algunos ejemplos disponibles en la literatura para ahondar en el mundo de la programación. Se presentará las nociones básicas de **RStudio**, **GEE** y **Python**. Una introducción al lenguaje **R**, **Python** y **JavaScript**, los tipos de datos (dataframes, listas, etc.), funciones definidas por el usuario, cómo leer y guardar información en archivos de texto o formato CSV, cómo generar gráficos, etc.

[Google Earth Engine (GEE)](https://www.google.com/intl/es_in/earth/education/tools/google-earth-engine/#!/) es una plataforma de geomática basada en la nube que permite a los usuarios visualizar y analizar imágenes de satélite de nuestro planeta. Los científicos y las organizaciones sin ánimo de lucro utilizan GEE para llevar a cabo estudios de sensoramiento remoto, tales como: predecir brotes de enfermedades, gestionar recursos naturales, monitorear desastres naturales, etc.

Se comenzará con una descripción general GEE (Componentes de GEE, Code Editor, Explorer y Clientes API). Se mostrará diversos productos generados con la base de datos disponibles y los algorítmos de GEE. Se presentará las nociones básicas de Code Editor. Una introducción al lenguaje Javascript. Descripción General del Code Editor. API Javascript de GEE. Convenciones: Guía de Estilo. Acceso a las funcionalidades de la API. Consultar la documentación de las funciones. Tipo de datos (Listas, Diccionarios, etc.). Funciones definidas por el usuario.

En el nivel intermedio, manipularemos las series de tiempo observadas (producto PISCO precipitación y temperatura) para determinar la climatología de las zonas de estudio y algunos estadísticos descriptivos. También se sistematizará la descarga de las salidas de diversos modelos de circulación global a través de la programación usando **GEE**. 

Finalmente, se llevará a cabo la regionalización de las salidas de los modelos de circulación global en base a las series de tiempo observadas para nuestras zonas de estudio definidas en el nivel anterior. Se probarán diversas técnicas de downscaling estadístico y se realizará una crítica de los resultados. Asimismo, se guardarán las series de tiempo historicas y futuras para los escenarios analizados con la finalidad de utilizarlas en el siguiente módulo del curso.

> ## Antes de empezar
>
> Los participantes deberán utilizar sus propias computadoras con acceso a internet
> a fin de asegurar un correcto uso de la plataforma para un desarrollo eficiente de los ejercicios. <br>**Estas lecciones asumen que los participantes no presentan conomientos previos de la plataforma GEE.**
>
> Para comenzar, seguir el procedimiento mostrado en la pestaña "[Episodios]"
> y descargar la data proporcionada para el desarrollo de los ejercicios.
>
> #### Prerequisitos
>
> Las lecciones requieren de conocimientos previos de algún lenguaje de programación tales como: **Python**, **R**, **Matlab**, **Fortran**, **C++**, **C**, **JavaScript**, etc. Asimismo, conocimientos de **Sensoramiento Remoto** y **Sistemas de Información Geográfica**.
{: .prereq}

<!--  
> ## For Instructors
> If you are teaching this lesson in a workshop, please see the
> [Instructor notes](guide).
{: .prereq}
--> 

{% include links.md %}