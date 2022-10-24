---
title: "Introducción a Python y descarga de GCM"
teaching: 60
exercises: 120
questions:
- "¿Qué es Python?"
- "¿Porqué deberías aprender Python?"
- "¿Cómo automatizar la descarga de las salidas de los GCM?"
objectives:
- "Describir las ventajas de usar programación vs. completar tareas repetitivas a mano"
- "Definir los tipos de datos en Python: **cadenas**, **enteros**, y números de **punto flotante**"
- "Realizar operaciones matemáticas en Python utilizando operadores básicos"
- "Dentro del contexto de Python definir: **listas**, **tuplas**, y **diccionarios**"
- "Describir el procedimiento para la descarga de las salidas de los GCM"
keypoints:
- "Python es un lenguaje interpretado que puede ser usado interactivamente (ejecutando un comando a la vez) o en modo scripting (ejecutando una serie de comandos guardados en un archivo)."
- "Se puede asignar un valor a una variable en Python. Esas variables pueden ser de varios tipos, tales como cadenas, y números: enteros, de punto flotante y complejos."
- "Las listas y las tuplas son similares en el sentido de que son listas ordenadas de elementos; difieren en que una tupla es inmutable (sus elementos no pueden ser modificados)."
- "Los diccionarios son estructuras de datos desordenadas que proporcionan mapeos entre claves y valores."
- "Python nos permite automatizar las descargar de las salidas de los GCMs"
---

## Intérprete

Python es un lenguaje interpretado que puede ser usado de dos formas:

* Modo "Interactivo": cuando lo usas como una "calculadora avanzada" ejecutando
  un comando a la vez. Para iniciar Python en este modo, simplemente ejecuta `python`
  en la línea de comandos:
  
<!--

~~~
$ python
~~~
{: .language-bash}

~~~
Python 3.7.9 (default, Aug 31 2020, 17:10:11) [MSC v.1916 64 bit (AMD64)] :: Anaconda, Inc. on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
~~~
{: .output}

Los res símbolos de mayor que `>>>` forman un indicador interactivo en Python, que significa que está esperando tu
entrada de datos.

~~~
2 + 2
~~~
{: .language-python}

~~~
4
~~~
{: .output}

~~~
print("Hello World")
~~~
{: .language-python}
~~~
Hello World
~~~
{: .output}

* Modo "Script": cuando ejecutas una serie de "comandos" guardados en un archivo de texto,
  generalmente con una extensión `.py` después del nombre de tu archivo:
~~~
$ python my_script.py
~~~
{: .language-bash}

~~~
Hello World
~~~
{: .output}

## Introducción a los tipos de datos incorporados en Python

### Strings, integers, and floats

Una de las cosas más básicas que podemos hacer en Python es asignar valores a las variables:

~~~
text = "hola mundo"  # Un ejemplo de string
number = 42  # Un ejemplo de integer
pi_value = 3.1415  # Un ejemplo de float
~~~
{: .language-python}

Aquí hemos asignado datos a las variables `text`,` number` y `pi_value`,
utilizando el operador de asignación `=`. Para revisar el valor de una variable, nosotros
podemos escribir el nombre de la variable en el intérprete y presionar <kbd>Return</kbd>:

~~~
text
~~~
{: .language-python}
~~~
"hola mundo"
~~~
{: .output}


Todo en Python tiene un tipo. Para obtener el tipo de algo, podemos pasarlo
a la función `type`:

~~~
type(text)
~~~
{: .language-python}
~~~
<class 'str'>
~~~
{: .output}

~~~
type(number)
~~~
{: .language-python}
~~~
<class 'int'>
~~~
{: .output}

~~~
type(6.02)
~~~
{: .language-python}
~~~
<class 'float'>
~~~
{: .output}


La variable `text` es de tipo 'str', abreviatura de **string** o cadena de caracteres. Las cadenas almacenan
secuencias de caracteres, que pueden ser letras, números, puntuación
o formas más exóticas de texto (¡incluso emoji!).

También podemos ver el valor de algo usando otra función incorporada, `print`:

~~~
print(text)
~~~
{: .language-python}
~~~
Data Carpentry
~~~
{: .output}
~~~
print(11)
~~~
{: .language-python}
~~~
11
~~~
{: .output}

Esto puede parecer redundante, pero de hecho es la única forma de mostrar resultados en un script:

*example.py*
~~~
# En un archivo script de Python
# los comentarios en Python inician con #
# Las siguientes líneas asignan la cadena "hola mundo" a la variable "text".
text = "hola mundo"

# ¡La siguiente línea no hace nada!
text

# La siguiente línea usa la función print para imprimir el valor asignado a "text"
print(text)
~~~
{: .language-python}

*Ejecutando el script*
~~~
$ python example.py
~~~
{: .language-bash}

~~~
hola mundo
~~~
{: .output}

Nota que "hola mundo" se imprime una vez.

**Sugerencia**: `print` y `type` son funciones incorporadas en Python. Más adelante en esta
lección, veremos métodos y funciones definidas por el usuario. La documentación 
de Python es excelente para darte una referencia sobre las diferencias entre ellos.


### Operadores

Podemos realizar cálculos matemáticos en Python usando los operadores básicos
 `+, -, /, *, %`:

~~~
2 + 2  # Suma
~~~
{: .language-python}

~~~
4
~~~
{: .output}

~~~
6 * 7  # Multiplicación
~~~
{: .language-python}
~~~
42
~~~
{: .output}
~~~
2 ** 16  # Potencia
~~~
{: .language-python}
~~~
65536
~~~
{: .output}
~~~
13 % 5  # Módulo
~~~
{: .language-python}
~~~
3
~~~
{: .output}


También podemos utilizar operadores de comparación y lógicos:
`<,>, ==,! =, <=,> =` y declaraciones de identidad como
`and, or, not`. El tipo de datos devuelto por estos operadres es
llamado _**boolean**_ y retorna verdadero o falso, como ves a continuación.

~~~
3 > 4
~~~
{: .language-python}
~~~
False
~~~
{: .output}

~~~
True and True
~~~
{: .language-python}
~~~
True
~~~
{: .output}

~~~
True or False
~~~
{: .language-python}
~~~
True
~~~
{: .output}

~~~
True and False
~~~
{: .language-python}
~~~
False
~~~
{: .output}

## Secuencias: Listas y Tuplas

### Listas

**list** (o listas) son una estructura de datos común para almacenar una secuencia ordenada de
elementos. Se puede acceder a cada elemento mediante un índice. Ten en cuenta que en Python,
los índices comienzan con 0 en lugar de 1:

~~~
numbers = [1, 2, 3]
numbers[0]
~~~
{: .language-python}
~~~
1
~~~
{: .output}

Se puede usar un bucle `for` para acceder a los elementos de una lista u otras 
estructuras de datos de Python, uno a la vez:

~~~
>>> for num in numbers:
...     print(num)
...
~~~
{: .language-python}

~~~
1
2
3
~~~
{: .output}

Usar **sangría** es muy importante en Python. Ten en cuenta que la segunda línea en el
ejemplo de arriba está sangrada (o indentada). Al igual que los tres `>>>` son un
indicador interactivo en Python, los tres puntos `...` son indicadores de 
líneas multiples en Python. Esta es la manera en que Python marca un bloque de código. [Nota: no 
tienes que escribir `>>>` o `...`.]

Para agregar elementos al final de una lista, podemos usar el método `append`. Los métodos
son una forma de interactuar con un objeto (una lista, por ejemplo). Podemos invocar un
método usando el punto `.` seguido del nombre del método y una lista de argumentos
entre paréntesis. Veamos un ejemplo usando `append`:

~~~
numbers.append(4)
print(numbers)
~~~
{: .language-python}

~~~
[1, 2, 3, 4]
~~~
{: .output}

Para averiguar qué métodos están disponibles para un
objeto, podemos usar el comando incorporado `help`:

~~~
help(numbers)

Help on list object:

class list(object)
 |  list() -> new empty list
 |  list(iterable) -> new list initialized from iterable's items
 ...
~~~
{: .output}

### Tuplas

Una tupla **tuple** es similar a una lista en que es una secuencia ordenada de elementos.
Sin embargo, las tuplas no se pueden cambiar una vez creadas (son "inmutables"). Las tuplas
se crean colocando valores separados por comas dentro de los paréntesis `()`.

~~~
# Las tuplas usan paréntesis
a_tuple = (1, 2, 3)
another_tuple = ('blue', 'green', 'red')

# Nota: las listas usan corchetes cuadrados
a_list = [1, 2, 3]
~~~
{: .language-python}

> ## Tuplas _vs._ Listas
> 1. ¿Qué sucede cuando ejecutas `a_list[1] = 5` ?
> 2. ¿Qué sucede cuando ejecutas `a_tuple[2] = 5`?
> 3. ¿Qué te dice `type(a_tuple)` sobre `a_tuple`?
>
{: .challenge}


## Diccionarios

Un diccionario **dictionary** es un contenedor que almacena pares de objetos - claves y valores.

~~~
translation = {'one': 1, 'two': 2}
translation['one']
~~~
{: .language-python}
~~~
1
~~~
{: .output}

Los diccionarios funcionan como listas, excepto que se crea el índice utilizando *claves*  **keys**.
Puedes pensar en una clave como un nombre o un identificador único para un conjunto de valores
en el diccionario. Las claves sólo pueden tener tipos particulares, tienen que ser
"**hashable**". Las cadenas y los tipos numéricos son aceptables, pero las listas no lo son.

~~~
rev = {1: 'one', 2: 'two'}
rev[1]
~~~
{: .language-python}
~~~
'one'
~~~
{: .output}

~~~
bad = {[1, 2, 3]: 3}
~~~
{: .language-python}
~~~
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
~~~
{: .output}

En Python, un "**Traceback**" es un bloque de error de varias líneas impreso para el
usuario.

Para agregar un elemento al diccionario, asignamos un valor a una nueva clave:

~~~
rev = {1: 'one', 2: 'two'}
rev[3] = 'three'
rev
~~~
{: .language-python}
~~~
{1: 'one', 2: 'two', 3: 'three'}
~~~
{: .output}

Usar bucles `for` con diccionarios es un poco más complicado. Podemos hacer
esto de dos maneras:
~~~
for key, value in rev.items():
    print(key, '->', value)
~~~
{: .language-python}

~~~
1 -> one
2 -> two
3 -> three
~~~
{: .output}

o

~~~
for key in rev.keys():
    print(key, '->', rev[key])
~~~
{: .language-python}
~~~
1 -> one
2 -> two
3 -> three
~~~
{: .output}


> ## Cambiando diccionarios
>
> 1. Primero, imprime el valor de `rev` del diccionario en la pantalla.
> 2. Reasigna el segundo valor (parar el *par clave: valor*) para que ya no
> lea "dos" sino "manzana".
> 3. Imprime el valor de `rev` en la pantalla nuevamente y ve si el valor ha cambiado.
>
{: .challenge}


Es importante tener en cuenta que los diccionarios están "desordenados" y no recuerdan
la secuencia de sus elementos (es decir, el orden en el que los pares clave: valor fueron
añadidos al diccionario). Debido a esto, el orden en que los elementos son
devuelto en los bucles sobre los diccionarios, puede aparecer al azar e incluso puede cambiar
con el tiempo.


## Funciones

Definir una sección de código como una función en Python se hace utilizando la palabra clave `def`.
Por ejemplo, una función que tome dos argumentos y devuelve su suma
puede ser definida como:

~~~
def add_function(a, b):
    result = a + b
    return result

z = add_function(20, 22)
print(z)
~~~
{: .language-python}
~~~
42
~~~
{: .output}

## Descarga de salidas de modelos GCM

Los datos climáticos que necesitamos están disponibles a través de la **Earth System Grid Federation** (ESGF), una red  de centros académicos y gubernamentales en los Estados Unidos, Europa y Asia. Es un repositorio para todos los datos climáticos del CMIP5 y la flamante CMIP6. En este laboratorio, nos centraremos en la salida de datos del CMIP5.

El ESGF es una red de nodos. Por ejemplo, si visita esta página web del [ESGF](https://esgf-node.llnl.gov/projects/esgf-llnl/), estará visitando el nodo del Lawrence-Livermore National Laboratory, pero podría, teóricamente, elegir cualquiera de los otros nodos que aparecen en la página principal del ESGF.

## Realizar una consulta de las salidas de los GCM

El ESGF tiene una interfaz de búsqueda muy intuitiva, pero en su lugar, usaremos el paquete [esgf-pyclient](https://github.com/ESGF/esgf-pyclient), que proporciona una forma fácil de acceder a la API de búsqueda del ESGF directamente en Python.

 - Primero, importaremos las bibliotecas que necesitaremos. Específicamente, importaremos **pyesgf**, que es el nombre del módulo contenido en la biblioteca **esgf-pyclient**. Importaremos tanto las funciones de búsqueda como las de inicio de sesión. También importaremos **os**, **requests**, y **tqdm**, que usaremos en una función de descarga de archivos personalizados, que verán más adelante. Finalmente, usaremos **pandas** para crear una tabla desde la que leeremos nuestros resultados.

~~~
# Cargamos los paquetes
from pyesgf.search import SearchConnection
import os
import pandas as pd
import requests
from tqdm import tqdm
~~~
{: .language-python}

Inicie su búsqueda creando un nuevo objeto `SearchConnection`. Aquí indicaremos que queremos utilizar el nodo LLNL como punto de partida, y pediremos que nuestra búsqueda se distribuya a través de la red federada.

~~~
# Iniciamos la conexión con el servidor
conn = SearchConnection('https://esgf-node.llnl.gov/esg-search', distrib=True)
~~~
{: .language-python}

Ahora tenemos que proporcionar los criterios de búsqueda. El API del ESGF utiliza una serie de palabras clave definidas para encontrar los datos que está buscando. Las opciones que nos interesan se resumen en la siguiente tabla.

Nos interesan tres variables de temperatura y una de precipitación en este laboratorio: "tas", que es la Temperatura del Aire Cercana la Superficie; "tasmax", que es la Temperatura Máxima Diaria del Aire Cercana a la Superficie; "tasmin", la Temperatura Mínima Diaria del Aire Cercano a la Superficie; y "pr" que es la precipitatión en todas sus formas.

### Busqueda de los datos

 - Pasemos los criterios anteriores a nuestra función de búsqueda. Tengan en cuenta que también pasamos latest=True, lo que significa que queremos la última versión de cada conjunto de datos.
 
~~~
# Consulta del modelo CanESM2
query = conn.new_context(
    latest=True,
    facets='null', 
    project='CMIP5',
    model='CanESM2',
    experiment='historical,rcp26,rcp45,rcp60,rcp85',
    variable='pr,prc,tas,tasmax,tasmin',
    time_frequency="mon",
    realm='atmos',
    ensemble='r1i1p1')
~~~
{: .language-python}

y ejecutamos la busqueda.

~~~
results = query.search()
~~~
{: .language-python}

Puedes saber cuántos resultados ha obtenido tu búsqueda comprobando la longitud de `results`. También puedes obtener la propiedad `hit_count` del objeto de la consulta antes de buscar.

~~~
print(len(results))
~~~
{: .language-python}

~~~
15
~~~
{: .output}

~~~
print(query.hit_count)
~~~
{: .language-python}

~~~
15
~~~
{: .output}

~~~
print(query.hit_count == len(results))
~~~
{: .language-python}

~~~
True
~~~
{: .output}

Los resultados de la búsqueda contienen objetos de "contexto", que aún no nos dan la información que necesitamos. Procesemos el primer `hit`, para ver cómo el `esgf-pyclient` devuelve los resultados.

La información sobre los resultados se almacena en una propiedad de objeto llamada `json`. Puedes ver todos los detalles usando `results.json`. No imprimiremos el resultado completo aquí, pero podemos ver porciones del resultado.

Veamos el identificador del resultado.

~~~
print(results[0].json['id'])
~~~
{: .language-python}

~~~
cmip5.output.CCCma.CanESM2.rcp85.mon.atmos.r1i1p1.v20130331|crd-esgf-drc.ec.gc.ca
~~~
{: .output}

Este es un registro de la salida general del CMIP5, pero no es algo que podamos descargar directamente. Francamente, probablemente no queramos descargarlo de todas formas. Veamos las variables para las que el registro tiene datos.

~~~
print(results[0].json['variable'])
~~~
{: .language-python}

~~~
['ccb', 'cct', 'ci', 'cl', 'cli', 'clivi', 'clt', 'clw', 'clwvi', 'co2', 'co2mass', 'evspsbl', 'fco2antt', 'fco2nat', 'hfls', 'hfss', 'hur', 'hurs', 'hus', 'huss', 'mc', 'pr', 'prc', 'prsn', 'prw', 'ps', 'psl', 'rlds', 'rldscs', 'rlus', 'rlut', 'rlutcs', 'rsds', 'rsdscs', 'rsdt', 'rsus', 'rsuscs', 'rsut', 'rsutcs', 'rtmt', 'sbl', 'sci', 'sfcWind', 'ta', 'tas', 'tasmax', 'tasmin', 'tauu', 'tauv', 'tro3', 'ts', 'ua', 'uas', 'va', 'vas', 'wap', 'zg']
~~~
{: .output}

¡Eso es demasiado! No queremos acceder a la información de todas las variables. Sólo queremos `tas`, `tasmax`, `tasmin` y `pr`. Podemos profundizar en el registro solicitando una búsqueda adicional usando el file_context del registro como entrada para la búsqueda.

~~~
hit = results[0].file_context().search()
~~~
{: .language-python}

Esto debería devolver ahora un resultado por cada archivo del registro principal. Podemos ver cuántos registros tenemos.

~~~
print(len(hit))
~~~
{: .language-python}

~~~
57
~~~
{: .output}

Podemos usar una función anónima `lambda` para extraer el nombre de archivo y la URL de cada resultado.

~~~
files = map(lambda f : {'filename': f.filename, 'url': f.download_url}, hit)
~~~
{: .language-python}

La función `map` devuelve un iterador de clase `map`. Volvamos a convertirlo en una lista.

~~~
files = list(files)
~~~
{: .language-python}

Puedes echar un vistazo a los primeros cinco registros.

~~~
print(files[0:10])
~~~
{: .language-python}

~~~
[{'filename': 'ccb_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/ccb/r1i1p1/ccb_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'cct_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/cct/r1i1p1/cct_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'ci_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/ci/r1i1p1/ci_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'cl_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/cl/r1i1p1/cl_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'cli_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/cli/r1i1p1/cli_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'clivi_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/clivi/r1i1p1/clivi_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'clt_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/clt/r1i1p1/clt_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'clw_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/clw/r1i1p1/clw_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'clwvi_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/clwvi/r1i1p1/clwvi_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'co2_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/co2/r1i1p1/co2_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}]
~~~
{: .output}

Todavía tenemos información sobre variables que no nos interesan. Dejemos los items que no nos interesan. Ten en cuenta que el filtro devuelve un iterador que no es una lista, así que terminaremos la llamada al filtro en lista.

~~~
var = 'tas' # pr_
~~~
{: .language-python}

~~~
files = list(filter(lambda x: var in x['filename'], files))
print(files)
~~~
{: .language-python}

~~~
[{'filename': 'tas_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/tas/r1i1p1/tas_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'tasmax_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/tasmax/r1i1p1/tasmax_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}, {'filename': 'tasmin_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/rcp85/mon/atmos/tasmin/r1i1p1/tasmin_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc'}]
~~~
{: .output}

Repitamos este proceso para el segundo resultado de nuestra búsqueda original. En lugar de ejecutar cada línea individualmente, podemos colapsar esto en una sola llamada.

~~~
files2 = list(filter(lambda x: var in x['filename'],
                     list(map(lambda f : {'filename': f.filename, 'url': f.download_url},
                              results[1].file_context().search()))))
print(files2)
~~~
{: .language-python}

~~~
[{'filename': 'tas_Amon_CanESM2_historical_r1i1p1_185001-200512.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/historical/mon/atmos/tas/r1i1p1/tas_Amon_CanESM2_historical_r1i1p1_185001-200512.nc'}, {'filename': 'tasmax_Amon_CanESM2_historical_r1i1p1_185001-200512.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/historical/mon/atmos/tasmax/r1i1p1/tasmax_Amon_CanESM2_historical_r1i1p1_185001-200512.nc'}, {'filename': 'tasmin_Amon_CanESM2_historical_r1i1p1_185001-200512.nc', 'url': 'http://crd-esgf-drc.ec.gc.ca/thredds/fileServer/esg_dataroot/AR5/CMIP5/output/CCCma/CanESM2/historical/mon/atmos/tasmin/r1i1p1/tasmin_Amon_CanESM2_historical_r1i1p1_185001-200512.nc'}]
~~~
{: .output}

Ahora vamos a añadir files2 al final de los files. No es que esta función sea una función en sí, modificando los files directamente sin necesidad de sobrescribir el objeto asignando un valor a los files con un signo igual.

~~~
files.extend(files2)
~~~
{: .language-python}

Dos resultados menos, `python len(results) - 2` - ¡Quedan 2! Esto podría ser tedioso. Usemos un `for` de for para hacer el resto del trabajo por nosotros.

~~~
for i in range(2, len(results)):
    files.extend(list(filter(lambda x: var in x['filename'],
                      list(map(lambda f : {'filename': f.filename, 'url': f.download_url},
                               results[i].file_context().search())))))
~~~
{: .language-python}

### Sistematizando los resultados

Hasta ahora, hemos estado usando una lista de diccionarios para almacenar nuestros resultados, pero esto se está volviendo un poco difícil de manejar. Convirtamos nuestros resultados en un marco de datos de `Pandas`.

~~~
files = pd.DataFrame.from_dict(files)
print(files)
~~~
{: .language-python}

~~~
                                             filename  \
0      tas_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc   
1   tasmax_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc   
2   tasmin_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc   
3   tas_Amon_CanESM2_historical_r1i1p1_185001-2005...   
4   tasmax_Amon_CanESM2_historical_r1i1p1_185001-2...   
..                                                ...   
61  tasmin_Amon_CanESM2_rcp45_r1i1p1_200601-210012.nc   
62  tasmin_Amon_CanESM2_rcp45_r1i1p1_210101-230012.nc   
63     tas_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc   
64  tasmax_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc   
65  tasmin_Amon_CanESM2_rcp85_r1i1p1_200601-210012.nc   

                                                  url  
0   http://crd-esgf-drc.ec.gc.ca/thredds/fileServe...  
1   http://crd-esgf-drc.ec.gc.ca/thredds/fileServe...  
2   http://crd-esgf-drc.ec.gc.ca/thredds/fileServe...  
3   http://crd-esgf-drc.ec.gc.ca/thredds/fileServe...  
4   http://crd-esgf-drc.ec.gc.ca/thredds/fileServe...  
..                                                ...  
61  http://esgf.nci.org.au/thredds/fileServer/repl...  
62  http://esgf.nci.org.au/thredds/fileServer/repl...  
63  http://esgf.nci.org.au/thredds/fileServer/repl...  
64  http://esgf.nci.org.au/thredds/fileServer/repl...  
65  http://esgf.nci.org.au/thredds/fileServer/repl...  

[66 rows x 2 columns]
~~~
{: .output}

Podemos eliminar las proyecciones de largo alcance (2101-2300) de nuestra lista de descargas.

~~~
files = files[~files['filename'].str.contains("210101")]
~~~
{: .language-python}

Notarán que tenemos múltiples URLs para el mismo archivo. No es necesario que descarguemos cada archivo varias veces, por lo que puedes optar por soltar los duplicados utilizando `files[['nombre de archivo']].drop_duplicates()`.

También puedes optar por conservar las URL adicionales como fuentes de respaldo en caso de que una de las descargas falle. Nuestra función de descarga, a continuación, contiene un código para comprobar si el tamaño del archivo es el esperado, sin embargo, actualmente no incluye ningún código para manejar los casos en los que el tamaño no es el correcto.

## Descargando la información

**Python** no tiene una función de descarga de archivos incorporada, así que podemos usar la nuestra. Define la siguiente función, que descargará los archivos de una URL dada y los guardará bajo el nombre de archivo que especifiques.

~~~
# Adapted from: https://stackoverflow.com/a/37573701
def download(url, filename):
    print("Downloading ", filename)
    r = requests.get(url, stream=True)
    total_size, block_size = int(r.headers.get('content-length', 0)), 1024
    with open(filename, 'wb') as f:
        for data in tqdm(r.iter_content(block_size),
                         total=total_size//block_size,
                         unit='KiB', unit_scale=True):
            f.write(data)
            
    if total_size != 0 and os.path.getsize(filename) != total_size:
        print("Downloaded size does not match expected size!\n",
              "FYI, the status code was ", r.status_code)
~~~
{: .language-python}

Ahora puedes descargar un archivo como el siguiente:

~~~
download(files[0]['url'], files[0]['filename'])
~~~
{: .language-python}

O podrías descargarlos todos de una sola vez. 

~~~
for index, row in files.iterrows():
    if os.path.isfile(row.filename):
        print("File exists. Skipping.")
    else:
        download(row.url, row.filename)
~~~
{: .language-python}

Ahora que sabes cómo buscar y filtrar datos, practica con diferentes conjuntos de filtros, y luego completa los ejercicios, a continuación.

{% include links.md %}

-->