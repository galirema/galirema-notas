# Proyecto Galirema

Presentación de proyecto Galirema (Galicia recursos marinos) en Librecon2017


_Francisco Fernández Cortés_


### En recuerdo de Aaron Swartz

![Aaron Swartz](https://lh3.googleusercontent.com/udQAVgBVvd-0GkZDNn2k3_5lCAuaJbPWuDRoAITPc4B4S0ETjVCDM70J60cm8qpQT-x6rZDR69ELe08D7bBo1SJiqixSLfHrECnKXaG8ftJxGbhd4GGxTfcNdUAquNGkEVIs6Y1-2gjtURDgtumZoZGoBfH0ZM6N5zhhoGJG-1RQd0_f0txS4pEpPTW81L7u1OLtRdjmyJ85rZDa1C38vt8eSSWhi0D7hn6bciwSUNyi5q-4Ilj5xcD4leRd2yxNDa-mgSMHWuKsxf7uCscwIsC-wOwP5BI4TbxkbQqWG9aVleS1dVjbAW4vllmfElbDOVBn6c_uWKL_BH-IHVzUZX2597NEUE39ekAbNK8mjJhj2gf1LfMqpux22cgm4fixhtZhBh5sc_p-8wHQI_ejUM1u_5Ovb4IfZ_JLakXDDBPj24o6E1G29R3dfXbO4x_VgO9c-IZx3xRJXYWiizm2UD4hGOpJNaC9_BJXRNSYY4e2kMoSZWPnxF7RR0Nm818vkFJ6ZsAEZRxEci0QqSAZSXmywo06mnzAXf8YejPeC-4lzKKHnAPe3TpNF22g72SQDJq8sebxJ1vIv-MkxjG0vNJRv__PlNdq_OKZ9-SQchA9Pt2Eqg5DSww9jv9BkfVWrPMhio5p45Unv0KPOL_SAUnsZhvxe0cy7qQ=s500 "Aaron Swartz 1986-2013")



## Menú

1. Antecedentes

1. Objetivo

1. Fuentes de Información

1. Metodologías

1. Desarrollo del proyecto

1. Características de los datos

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

* __Identificación de las fuentes__

* __Datos sobre la [planificación](IndicePlanes.md)__
    * Importado en _PDF_: 1992-1994 (3)
    * Importado en _HTML_: 1995-2002 (8)
    * En _SQL_ base de datos: 2003-2017 (15)
    
    ![PlanesImportados](https://lh3.googleusercontent.com/3OA-ztjJQxtGVR8JL3QkXPMzjNBIheVGrQ5sIPp5bsz50JMFHzHdigBt9a2ds5921dEwxcbNaDRcFyMyf3bNVv9UoU3n-GZCFi3_xt6IPY3Go7kRkb_2Raz0QFh_3LlSuDrD3YrURL3jiexzbbMhOy_F7YjcDa7vJSStnN8HDQoTXwftJWflj_012OhliJcNzdW6Jre7ifDkGI7vwojHLpfkABkCnozo_ytQ1Uf2J71_7p52akh0J69hG7Ot02kwi71qSjMA4UY5f8o_OMMc--6KVhTzr11pqcK2vztdqSW1HFBnEcMM1QuTnFdVZvqY3jCHrY6UKYWefYP4Zv6nVChhKNscD9DL5UJIe2CkkMUKEF2T61Hnzi4ZCQO-xGBinxGTtgYb2rTSwBF088_m5fGTihn55IeisxhtmpAREUskU3XbrylUeh9HaTqXU_gB6xPyVY1hPzs_dKjozZTaf60y4-HkcIJsNNy37yiFb36fQRULJNkZDxGc0sZg5lyl0EGDUpKMuMI9iX1GxXFbq_UhDCh_FTqbPkQ0CeelC8SzGwwX305L8-pSCmJCHs0KbTXbcpOmq2IO4azlJSOCwHc15iIx9EWddKchcM_UGnZIOrel-xTlaiTP1y2rt7CcDqxCn63XkC4olhdKAxmWuaXC2ItdiN3Mdic=s500 "Estado del procesado de planes")



* __Datos sobre el recurso__ (Num. de Zonas identificadas)

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
|Total| 45| 34| 45| 20| 58| 21| 48| 7| 278|


![áreasxzcosta](https://lh3.googleusercontent.com/zH_HyIOXkyIaVeIVEwDAdBExkuWPvmARLHiTgFK3CH_VxeNuj4V0cPXvvv6dtwDq10berfQILObrA9ME8Jm4xxFswANdZ-nxt5U8BRYYNWFLZX7JiLbnfJJ5aLo9CQBKTr2eCZezQfgwdpXxh_qYSeyjz0SiBWMF5be8qglmZlCmdkzLqL9MLCOgj5ROs6laPPhARJPtmK3rMBtPehwpuDl4u47wWv-ro8S1WwgIZ_Gy4_ZpnE79dzv4oL4pQPCV-FL-7jB7wkSQ161PA_qnxmSnfP9wHCKnKJqD2nh-8JuPSu1bxHJaCXE-ophc66p7mZGsEyKIoOo1SUoMncjhA2D3q1M-HMbBT-L21xk8s3vLSS96t15lL89sfgkRHCcpjy1yn-jGfOcTO6WmMY7zehFvO4r7jx6MAV5v7eBy4EQnD_PH5NNMGeD4tyBgn3oraAZXdjeKU-Evo2yKcFCwTLW2_1XPSZMcv_7Ij6DgP1_vuVni0jhaExxf-OtHzuAgGWiXY6C3tjgJYYOwGnLl_E-19lX4-GLLyRylG_ZMyFjUO-ew-6YvzdtWVgijFSqsndTCXs_rB1wgcmXpv24iReiUwIri9IdTlbgZ2V48fB6M4tWoWiF8tCDvs3izDOmeYKjS77wceX2_16w5qpm36oQu8R1oWU0oLzI=s500 "Áreas identificadas por zona de costa")


![TiposPlan2017](https://lh3.googleusercontent.com/zOEf0STX-CIhEnbV3VFl8xhzTez7jLiaSZWKYTG2A13EkmgaPYET34AC8qQ9PU6idZQwiswA1hJPHFK5tBwTkIJQQAZ_tAUKocG5MY2nBIkVrq_W77iUD-qqmFZHMhDkT7a_EThb-ZhxqAb7TgpO1-nh049dIpV8JzVBOujXZStePaK6zeaVU-vBnYlhCHHUJI0g5XcDaDtYwD-DKq69gCQDJAb_RXEkZaA2BlC5OMvw376PwGJ5DRaQwH2jJcFO_nlfv1M0znK9nBfyLe6hQLG-h7qKZ7nYkq9L8p3jps6_NMEysxiwN1UP1O6aLX_lnNSDNDJgExTpGI1qBiP7wWzxYwdft2tf5gx5YlP77gLCbSKp8yM99zn5dNviAyCyCQOO8BGy_-zGYspF5EFisnubpN12rxQXFk3ZNx6JcjrbF5s5C-tnv1Y6T65ia5XokXfGkBSFR171qkNPXjEskw0uFPHdO3uFHE4PitjjSqyhGAtwyJSOckthBM_RRjmg574WAELb7U_n6nX5hrEzB6PktIjiTDAOIx1JRhvLXmYqvYm1otyKqb218X-XJKI_ktyQJl51n04zm8PMaQj6Ko3ZzgCRwSVqL_CE_f6oElJ4sljBOXMjExCebRh_w44IhyQtML8Hk3_nA6FjkJIGEOLOdoPZL4JYxsc=s500 "Tipos de plan 2017")


![areasxtplan](https://lh3.googleusercontent.com/VszDUVF1O_mvOwifDqIvmC9ilqu9cvL5b69ExDnH_NEKADdJMmTAR3ZsZkzi_UrJsE49q-1hsb6kzG_VeJ5j9dbOP7RCme9VSbovSRGBApTwIvy6CXCrGDX2yFfJzODPD39sw8pUWRoAnRRkWygZ5gg5g_zf3kChZB6f7gdGhhwr4F8cOHOL6M0r4Lw8UhJ03c_GUjXDBvj2YJcaGv7wZjNtRYDBMAARXCVwHgZSp66JxDrDIuPrrCK_2wy-EKyqFPIA_6YYLaASrlWMu8mQkkr3MRl2_J_QAO3t-bpAL964z5rnoHaAkqcNCqHQh2AdlW84REHBLyy2S05FhbGZMMJGCvhonjhhjX8IKev0Tt3Z210jf11qADRWsmSq88ZsGXy3yplszVngBQsje4aZXK0lahecWNVn9lAqQuo2wS4GoR-fnsLd-5lgfLjqgLjRLLleYhSD6nGI5JDealCAiTlb96p4DcFCAS5XQhpZzPo_1ZR649C7kq6RgBXT-TiOCX0Hj1Wi93GZQa1-mKZ6iVcxlwgqCx0vM2_ch1iLn4W73DYqcC6hjCDNdhC3tGKjuxj7jR8eXS1aMeuM2ear9KNHv67q_SULNZjBg6S62zmwXSMbFQjT0D_otsarLAR41oRUQ9q2VAjLyQAfd8Z_B_4aldNKXIvJ9ZY=s500 "Áreas identificadas por tipo de plan")



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


## Características de los datos

* Los datos tratados por el proyecto en esta etapa son los correspondientes a la __fase de planificación anual de la explotación__.

* La información aportada por la administración sobre esta planificación la hace mediante un documento legal en el DOG

* En la orden de aprobación del plan general están enunciados los planes anuales por una serie características que después son publicados individualmente en la web.

* Las características que definen cada plan son: "___tipo de Plan___", "___entidad promotora___", "___individual/conjunto___", "___modalidad de captura___", "___especies objetivo del Plan___", "___zona de Trabajo___", "___días máximos de trabajo___", "___época de Trabajo___", "___puntos de control___", "___zonas de trabajo detallada___", "___ide plan explotación___",

* La información de la mayoría de los campos puede ser sencilla o múltiple. Para que la información presentada sea fácilmente comprobada por el usuario se presenta con la complejidad de la fuente original.

* Los campos con varias informaciones se presentan con formato csv (separado por comas) eliminándose los elementos de redacción que contienen en las fuentes.

* Los datos están extraídos de la publicación en gallego del DOG y del planes anuales.

* Las especies objetivo de la captura están en __código alfa-3 (FAO)__ que coincide con el código estadístico de las especies comerciales de la EU

* Añado el campo  "___ide plan explotación___", para facilitar las referencias con los sucesivos trabajos. 


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
