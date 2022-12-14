---
layout: page
title: Setup
---

> ## Datos
> Para las lecciones de QGIS usaremos los datos de las cuencas hidrográficas del Perú que se puede descargar en [este enlace](https://downgit.github.io/#/home?url=https://github.com/hasencios/CursoUNALM_ANA_2022/tree/gh-pages/data/shp.rar)
> y se debe de guardar en la carpeta `shp`
>
> Los datos usados en el desarrollo de las lecciones serán proporcinados a medida que avancemos en el tutorial a través de un archivo compartido en GEE o Google Drive.
>
> Para las lecciones de R y RStudio usaremos el archivo que podemos descargar en [este enlace](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/weecology/portal-teachingdb).  Luego se deberá
> guardar el archivo en la carperta `data`
> 
> Tienes que descargar el archivo individualmente con los siguientes enlaces:
>
> - [gapminder_wide.csv](https://downgit.github.io/#/home?url=https://github.com/hasencios/CursoUNALM_ANA_2022/blob/gh-pages/data/gapminder_wide.csv)
{: .prereq}

> ## Software
> [**QGIS**](https://www.qgis.org/en/site/) es una aplicación profesional de SIG (Sistema de Información Geofgráfica) que está construida sobre software libre y de código abierto. Nos permite realizar tareas de procesamiento, análisis, modelamiento, entre otros,
> de los datos obtenidos del territorio y sus elementos que lo componen.
{: .prereq}

> [**R**](https://www.r-project.org/) es un lenguaje que, entre otras cosas, nos puede ayudar a realizar análisis estadísticos de series de tiempo hidrometeorológicas. Para este taller se debe de instalar lo siguiente:
> * [R](https://cran.r-project.org/bin/windows/base/)
> * [RStudio](https://rstudio.com/products/rstudio/download/)
> * [RTools](https://cran.r-project.org/bin/windows/Rtools/)
> * [TauDEM](https://github.com/dtarb/TauDEM/releases/download/v5.3.7/TauDEM537_setup.exe)
{: .prereq}

> [**Python**](http://python.org) es un lenguaje muy utilizado en
> la computación científica y también es ideal para la programación de propósito general.
> La instalación de todos los paquetes científicos individualmente puede ser
> un poco difícil, por lo que recomendamos un instalador todo en uno. 
>
> Para este taller utilizamos la versión 3.x. Específicamente usaremos [Anaconda](https://www.anaconda.com/products/distribution) para las lecciones.
>
> ### Paquetes de **Python** requeridos para este taller
>
> * [Pandas](http://pandas.pydata.org/)
> * [Jupyter notebook](http://jupyter.org/)
> * [Numpy](http://www.numpy.org/)
> * [Matplotlib](http://matplotlib.org/)
> * [plotnine](https://github.com/has2k1/plotnine)
{: .prereq}

## Instalación de software (Python)

Usaremos **Anaconda** para instalar **Python** y los paquetes necesarios.
Anaconda viene con **Pandas**, **Jupyter Notebook**, **Numpy** y **Matplotlib** preinstaladas.


### Instalación de **Anaconda**

**Anaconda** te instalará los paquetes.

#### Descarga e instala **Anaconda**

Descarga e instala [**Anaconda**](https://www.anaconda.com/products/individual).
Recuerde descargar e instalar el instalador para **Python** 3.x.

#### Descarga el paquete para crear gráficos.

El paquete para crear gráficos, `plotnine`, no está instalado por defecto.
Para instalarlo desde el terminal, escriba:

~~~
conda install -c conda-forge plotnine
~~~
{: .language-python}

### Instala los paquetes requeridos con **Conda**

En la terminal, escriba:

~~~
conda install -y numpy pandas matplotlib jupyter
conda install -c conda-forge plotnine
~~~
{: .language-bash}

## Abre un **Jupyter Notebook**

Después de instalar **Python** y los paquetes requeridos,
abre un **Jupyter Notebook** escribiendo este comando en la terminal:

~~~
jupyter lab
~~~
{: .language-bash}

Un **Jupyter Notebook** se abrirá automáticamente en tu navegador.
Si no es así, o si deseas utilizar un navegador diferente, abre este enlace: <http://localhost:8888>.

## Crear un **env** o espacio de trabajo

Después de instalar **Jupyter Notebook** y los paquetes requeridos,
vamos a instalar el espacio de trabajo necesario para descargar los GCM:

~~~
conda config --prepend channels conda-forge
conda config --append channels claut
conda create -n "gcm_unalm" ec3 esgf-pyclient matplotlib netCDF4 pandas requests "seaborn>=0.9.0" xarray
~~~
{: .language-bash}

Esto creará un nuevo entorno, llamado "gcm_unalm", que contendrá todos los paquetes que utilizaremos para completar los ejercicios contenidos en la lección, incluyendo Python 3.7.1 o superior.

~~~
conda activate gcm_unalm
conda install jupyterlab #Esto solo una vez
jupyter lab 
~~~
{: .language-bash}

Si prefiere tener una sola instalación de Jupyter que pueda acceder a todos sus entornos, puede utilizar Jupyter desde su entorno "base" e instalar un "kernel" para su entorno "gcm_unalm" emitiendo los siguientes comandos: 

~~~
conda install ipykernel
python -m ipykernel install --user --name="gcm_unalm" --display-name="gcm_unalm"
~~~
{: .language-bash}

Al final de todo, deberías tener instalado Python 3 en un nuevo y brillante entorno Conda que contiene todos los paquetes y módulos que necesitaremos para completar los ejercicios.