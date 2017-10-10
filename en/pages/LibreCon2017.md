# Proyecto Galirema

Presentación de proyecto Galirema (Galicia recursos marinos) en Librecon2017

_Francisco Fernández Cortés_


## Menú

1. Antecedentes

1. Objetivo

1. Fuentes de Información

1. Metodologías

1. Desarrollo del proyecto

1. Caracteristicas de los datos

1. Galirema en la web

1. A modo de ejemplo el __Pexma 2017__



## Antecedentes

* Los datos son los ladrillos básicos en el conocimiento de los procesos que nos rodean y en la gestión de los mismos.

* El aprovechamiento de los recursos marinos no está excluido de este principio y la sociedades han creado sus instrumentos para obtenerlos y utilizarlos.

* Con el desarrollo de internet una parte de esta información de dominio público está accesible en la web.

* Galicia en el año 1992 modifica la normativa de gestión de los recursos marisqueros y otros recursos marinos de competencia autonómica

* La modificación mas importante consiste en adecuar la extracción de los productos a la demanda comercial de los mismos, liberalizando la actividad marisquera mediante planes de explotación localizados a un territorio y especies aprovechadas.

* Este cambio hace que un año en toda Galicia puedan coexistir desde 150 a 250 normas de explotación distintas y mas de una norma en un mismo territorio.

* Toda esta información ha ido volcándose en internet a medida que este medio se ha convertido en un canal mas de comunicación con la Sociedad.

* Pero esta información esta dispersa en distintos sitios sin que faciliten su relación y con distintos niveles de accesibilidad a los datos que permitan su posterior aprovechamiento.  



## Objetivo

* Identificar las fuentes existentes en internet que contienen información sobre los recursos.

* Análisis de los datos en ella existentes y su reusabilidad.

* Desarrollo de metodologías para facilitar el que la información contenida pueda ser reutilizada por los interesados.

## Fuentes de Información

### Fuentes de datos oficiales

* Agrupamos las fuentes de datos en función del momento del proceso de aprovechamiento del recurso. 
* Distinguimos en los siguientes momentos:
    + __Planificación__: Estas fuentes contienen datos sobre la planificación anual del proceso de explotación.
    + __Recurso__: Son las fuentes que nos aportan información del recurso
    + __Resultados__: Son las fuentes de datos que nos dan información de los resultados de la explotación del recurso y que podremos relacionar con el modelo de gestión.

#### Listado de fuentes oficiales

|Fuentes|Planificación|Recurso|Resultados|GitHub Wiki|
|:------|:-----------:|:-----:|:--------:|:---------:|
|[Diario Oficial de Galicia](DiarioOficialGalicia.md)|__Si__|__Si__|no|[DiarioOficialGalicia](https://github.com/galirema/galirema/wiki/DiarioOficialGalicia)|
|[Pesca de Galicia](PescaDeGalicia.md)|__Si__|__Si__|__Si__|[PescaDeGalicia](https://github.com/galirema/galirema/wiki/PescaDeGalicia)|
|[INTECMAR](InstitutoTecnologicoMedioMariño.md)|no|__Si__|no|-|
|[SIGREMAR](IndiceSigremar.md)|no|__Si__|no|-|


### Otras fuentes complementarias

* __FAO__: La [lista ASFIS de especies](http://www.fao.org/fishery/collection/asfis/es) para los fines de estadísticas de pesca 

* __MAPAMA__:  [Denominaciones Comerciales](http://www.mapama.gob.es/es/pesca/temas/mercados-economia-pesquera/2Denomin_comerc.aspx#) que es la transposición a la legislación española la lista de especies comerciales reconocidas por la UE y que esta basada en la definida por la FAO y que recoge las denominaciones en todos los idiomas del estado español.


## Metodologías

* [Metodologías utilizadas](indiceMetodos.md)


## Desarrollo del proyecto

* Identificación de las fuentes

* Datos sobre la [planificación](IndicePlanes.md)
    * Importado en _PDF_: 1992-1994 (3)
    * Importado en _HTML_: 1995-2002 (8)
    * En _SQL_ base de datos: 2003-2017 (15)

* Datos sobre el recurso (Num. de Zonas identificadas)

|Tipo de Plan | CL | CF | CM | MN | AR | PO | VI | GL | TOTAL|
|:------------|---:|---:|---:|---:|---:|---:|---:|---:|-----:|
|Autorizacións| 5 | 10 | 2 | 4 | 22 | 1 | 2 | - | 46 |
|Zonas de Libre Marisqueo]| 14 | 10 | 8 | 3 | 10 | 6 | 14 | - | 65 |
|Percebe| 10 | 4 | 11 | 2 | 2 | 3 | 5 | - | 37 |
|Equinodermos| 8 | 2 | 3 | 2 | 3 | 2 | 5 | - | 25 |
|Solénidos| 4 | 1 | 6 | 4 | 11 | 2 | 7 | - | 35 |
|Peneiras| 0 | 0 | 1 | 0 | 2 | 2 | 2 | - | 7 |
|Algas| 1 | 1 | 9 | 2 | 3 | 2 | 5 | 7 | 30 |
|Anémonas| 2 | 2 | 0 | 0 | 2 | 1 | 4 | - | 11 |
|Poliquetos| 1 | 4 | 5 | 3 | 3 | 2 | 4 | - | 22 |


* Datos sobre los resultados de la explotación

    * Estadísticas de producción en [primera venta](IndiceEstadisticas.md)



## Caracteristicas de los datos


## Galirema en la web

Los recursos del __proyecto galirema__ en la web.

* __Generalistas__

    * [Galicia Mariñeira](http://www.galiciamarineira.info/) es un sitio con formato blog que pretende ser la entrada a los datos liberados por eso trata de reproducir la normativa que contiene los datos pero te permite navegar por los datos digitalizados (en castellano).

    * [Wiki Galirema](http://es.galirema.wikia.com/wiki/Wiki_Galirema) pretende presentar los resultados utilizando en formato wiki que permite una gestión mas personalizada de los contenidos si ser fiel a los documentos que contienen los datos (en gallego).


* __Desarrollo__

    * [Galirema en Github](https://github.com/galirema) es la entrada al [desarrollo del proyecto](https://github.com/galirema/galirema) En el está el repositorio de los datos obtenidos de fuentes no tratables, el acceso a los fuentes con datos tratables y la documentación del proyecto.

    * Alojado en [GitHub Pages](http://galirema.github.io/galirema/) se presenta ejemplos de tratamientos de los datos obtenidos con el proyecto

    * [Galirema en jsfiddle](https://jsfiddle.net/user/galirema/fiddles/) Está el código javascript de las plantillas de los distintos modelos de gráficos para representar los datos como "_Public fiddles_". 

    * Las anotaciones de desarrollo del proyecto utilizado un fork de __MDwiki__ de Dynalon y gh-pages están el el proyecto [galirema-notas](https://galirema.github.io/galirema-notas/en/#!index.md)

## A modo de ejemplo el __Pexma 2017__

* En galirema-notas [Informe plan general y especificos 2017](infoPlanGeneralEspecifico2017.md)

* [Documento pdf](uploads/pdf/infoPlanGeneralEspecifico2017.pdf)

* En github-pages: [Plan general y específicos 2017](http://galirema.github.io/galirema/InfoPlanGeneralEspecifico2017c.html)
