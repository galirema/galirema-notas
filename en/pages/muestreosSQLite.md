# Base de datos

* Para utilizar la información del proyecto utilizo SQLite como sistema de gestión de bases de datos relacional.

* El proceso de importación de los datos de la fase de planificación de la explotación de los recursos marinos costeros hay tres niveles.

	1. De importación de datos y desarrollo
	1. Datos públicos importados
	1. Datos públicos operativos para analisis

## Nivel 1

* Este e un nivel interno donde se realiza la prepaparación de los datos originales de las fuentes para ser importados.  
El esquema de la base de datos y las tables utilizadas estan condicionados por las fuentes originales y por lo tanto no será el mas indicado como esquema definitivo.  
Tambien se incluyen datos elaborados a partir de los originales para poder realizar los primeros análisis.

* La base de datos se llama "___muestreos.sqlite___" que tiene los siguientes tipos de tablas:
	* Tablas con datos informativos:  
Tiene los datos para documentar la información y el análisis.
	* Tablas con datos de la explotación:  
Con los datos de la explotación en periodos de vigencia anual. En estas tablas se han añadido campos con información cuantitativa que en los documentos de importación estan como información cualitativa.
	* Tablas con datos para el análisis:  
Son tablas necesarias para realizar el análisis de los datos que necesitan una elaboración determinada para poder ser analizados.

* BD Muestreos: [Tablas](muestreosTablas.md)


## Nivel 2

* Los datos importados en el nivel anterior se publican en el repositorio de GitHub "___galirema___"
* El nombre de esta base es "___galin.sqlite___" La información de esta base de datos corresponde a la información de los documentos base originales que son públicos no recogen la información tratada de la base muestreos.


## Nivel 3

* Este nivel corresponde al esquema operativo que tendrán los datos importados que permita compaginar la información de todas las fuentes de una forma estandarizada y evitando informaciones duplicadas y utilizando la codificación necesaria para poder relacionar la información contenida de una forma eficiente.  
Como no podria ser de otra forma la base de datos es "__galirema.sqlite__"

* Tablas que integran la base de datos
	* Tablas de datos
	* Tablas de codificación
	* tablas de relaciones
	



