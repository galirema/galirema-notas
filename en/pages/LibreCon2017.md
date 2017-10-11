# Proyecto Galirema

Presentación de proyecto Galirema (Galicia recursos marinos) en Librecon2017


_Francisco Fernández Cortés_


### En recuerdo de Aaron Swartz


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

Empleamos herramientas eficientes pero sencillas, para que puedan ser utilizadas en equipos con recursos limitados, también estas herramientas son software "___open source___" para evitar cualquier tipo de barreras para su uso.

### Markdown

* [Markdown Home](http://daringfireball.net/projects/markdown/) 

* [Markdown en  wikipedia (ES)](https://es.wikipedia.org/wiki/Markdown)

* [Markdown en Wikipedia (EN)](https://en.wikipedia.org/wiki/Markdown)


### Pandoc

* [Pandoc Home](http://johnmacfarlane.net/pandoc/)

* [Plandoc en Wiqipedia (EN)](https://en.wikipedia.org/wiki/Pandoc)


### pdftotext

* [pdftotxt (en man pages](https://linux.die.net/man/1/pdftotext)


### SQLite

* [SQLite Home](https://www.sqlite.org/index.html)


### Mozilla Firefox

* [Mozilla Firefox en Wikipedia (EN)](https://es.wikipedia.org/wiki/Mozilla_Firefox)


### SQLite Manager

* [SQLite Manager addons](https://addons.mozilla.org/es/firefox/addon/sqlite-manager/)

### MDwiki

* [MDwiki (About)](http://dynalon.github.io/mdwiki/#!index.md)

* [MDwiki en GitHub](https://github.com/Dynalon/mdwiki)



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


* __Datos sobre los resultados de la explotación__

__Indice de estadísticas pesqueras de Galicia__

1. __Estadísticas CIPEM__ (1986-1993) recogida de datos manual mediante en una fase de construcción de la red estadística.  

1. __Estadísticas SIP__ (1994-2003) recogida de datos telemática ([telnet](https://es.wikipedia.org/wiki/Telnet)) en toda Galicia

1. __Estadísticas Pescadegalicia__ (2004-actualidad) Recogida de datos telemática en toda Galicia (aplicación Web)

Descarga de los datos estadísticos de [primera venta](http://www.pescadegalicia.gal/gl/descargas) 

| CIPEM | SIP | Pescadegalicia |
|------:|----:|---------------:|
| 1993 | 2003 [csv2003](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2003.csv) | 2017 |
| 1992 | 2002 | 2016 [csv2016](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2016.csv) |
| 1991 | 2001 | 2015 [csv2015](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2015.csv) |
| 1990 | 2000 | 2014 [csv2014](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2014.csv) |
| 1989 | 1999 | 2013 [csv2013](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2013.csv) |
| 1988 | 1998 | 2012 [csv2012](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2012.csv) |
| 1987 | 1997 | 2011 [csv2011](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2011.csv) |
| 1986 | 1996 | 2010 [csv2010](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2010.csv) |
|-| 1995 | 2009 [csv2009](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2009.csv) |
|-| 1994 | 2008 [csv2008](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2008.csv) |
|-|-| 2007 [csv2007](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2007.csv) |
|-|-| 2006 [csv2006](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2006.csv) |
|-|-| 2005 [csv2005](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2005.csv) |
|-|-| 2004 [csv2004](http://www.pescadegalicia.gal/descargas/pescafresca/pescafresca2004.csv) |


## Caracteristicas de los datos

* Los datos tratados por el proyecto en esta etapa son los correspondientes a la fase de la planificación anual de la explotación

* La información aportada por la administración sobre esta planificación la hace mediante un documento legal en el DOG

* En la orden de aprobación del plan general están enunciados los planes anuales por una serie características que después son publicados individualmente en la web.


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
