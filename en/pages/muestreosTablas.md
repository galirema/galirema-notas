# Base de Datos: Muestreos

* Estado de los contenidos de las [tablas de Muestreos](MuestreosDB-log.md)

## Tablas con datos informativos

 Estas tablas contienen la información que describe la información de los elementos del sistema y que evita que se repita continuamente en los campos, así la información referente a ellas está relacionada mediante códigos.

### Especies

* Tabla __asfisp FAO__: Tablas descargadas de la web de la [FAO-ASFIS](http://www.fao.org/fishery/collection/asfis/es) que sirven de estándar para las administraciones pesqueras del mundo. En ella contiene tres códigos de interés: El código __CEIUAPA__ ("Clasificación Estadística Internacional Uniforme de los Animales y Plantas Acuáticos" que clasifica a las especies en grupos e función de sus características taxonómicas, ecológicas y económicas). El código __taxonómico__ y el código __alfa-3__ que es un identificador único de las especies para el intercambio de datos. Esta información se actualiza anualmente.  
El código __alfa-3__ es el utilizado por la UE para la transmisión de las notas de primera venta de los productos pesqueros con fines estadísticos. El __proyecto Galirema__ lo utiliza como código para la identificación de las especies.  
Los datos aportados FAO-ASFIS están en dos formatos el primero en formato texto y codificación windows y la denominación local de las especies en 3 idiomas (ingles francés y español) y otro con formato de hoja de cálculo codificado en UTF-8 y 6 idiomas para los nombres locales (ingles, francés, español, árabe, chino y ruso). Las versiones de los años 2013 y 2014 están basadas en el archivo de tres idiomas pero exige un proceso de transformación a codificación UTF-8, a partir de 2015 utilizo la versión de 6 idiomas que no necesita ser procesada.  
	* Estructura de la tabla versión 3 idiomas: (2013, 2014)  
``` sql
CREATE TABLE "asfisp2013" ("idefao" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "ISSCAAP" INTEGER, "TAXOCODE" CHAR(13), "3A_CODE" CHAR(3), "Scientific_name" TEXT, "English_name" TEXT, "French_name" TEXT, "Spanish_name" TEXT, "Author" TEXT, "Family" TEXT, "Order" TEXT, "Stats_data" BOOL)
```  
	* Versión 6 idiomas: (2015, 2016)  
``` sql
CREATE TABLE "asfisp2015" ("idefao" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "ISSCAAP" INTEGER, "TAXOCODE" CHAR(13), "3A_CODE" CHAR(3), "Scientific_name" TEXT, "English_name" TEXT, "French_name" TEXT, "Spanish_name" TEXT, "Arabic_name" TEXT, "Chinese_name" TEXT,"Russian_name" TEXT, "Author" TEXT, "Family" TEXT, "Order" TEXT, "Stats_data" BOOL)
```  

* Tabla __especies__: Es la primera tabla que utilice en el proyecto hoy ya no la uso y no está actualizada.  
``` sql
CREATE TABLE "especies" ("id_especie" INTEGER PRIMARY KEY  NOT NULL ,"nombre" TEXT,"talla_legal" NUMERIC DEFAULT (null) ,"nombre_cientifico" TEXT,"ai3_code" CHAR(3),"grupo" CHAR(20))
```  

* Tabla __especinomes__: Es la tabla que ahora utilizo, esta basada en la orden de "Tallas mínimas" _ORDEN de 27 de julio de 2012 por la que se regulan los tamaños mínimos de diversos productos pesqueros_  
``` sql
CREATE TABLE "especinomes" ("idespecie" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "ncientifico" TEXT, "codigoFAO" CHAR(3), "nomeGL" TEXT, "nombreES" TEXT, "grupoSEP" CHAR(2), "referencias" TEXT, "codog" CHAR(5))
```  
Esta tabla a sido actualizada con otras especies que no están en la orden de tallas mínimas pero que están en las normas de explotación y son aprovechadas comercialmente.  



### Entidades

* Tabla __cofradias__: Esta tabla contiene la información basica de las entidades que participan en en proceso de explotación que mayoritariamente son las cofradías de pescadores pero tambien incluye a otro tipo de entidades (agrupaciones laborales y empresas)  
```sql
CREATE TABLE "cofradias" ("id_cofradia" INTEGER PRIMARY KEY  NOT NULL , "id_municipio" INTEGER NOT NULL , "nombre" TEXT, "tipoentidad" CHAR(3), "costa" CHAR(2), "activa" BOOL DEFAULT T, "iniact" NUMERIC, "finact" NUMERIC)
```  

* Tabla __municipios__: Los municipios costeros.  
```sql
CREATE TABLE "municipios" ("id_municipio" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "id_provincia" INTEGER NOT NULL , "nombre" TEXT NOT NULL )
```  

* Tabla __provincias__: Las provincias costeras, desglosando las zonas compartidas como registros independientes.  
```sql
CREATE TABLE "provincias" ("id_provincia" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "nombre" TEXT NOT NULL )
```  



### Artes

* Tabla __modalidad__: En esta tabla se recogen las modalidades utilizadas para la captura del recurso. las modalidades estan definidas por la forma de aceder al recurso (a pie, desde embarcación, mergullo, etc...) o por el arte utilizado (endeño remolcado, rastro de vieiras, bicheiro, etc..).  
Se considera una modalidad diferente cuando un plan acepta dos o mas ya que por la información contenida en las fuentes no permite cuantificar el peso de cada una de las modalidades en el plan y las capturas obtenidas.  
```sql
CREATE TABLE "modalidad" ("idemoda" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "codeMod" CHAR(1), "modalidade" CHAR(50), "modasinoni" VARCHAR(150), "opera" VARCHAR(50))
```  

### Legales

* Tabla __lex__: Recoge la normativa publicada y los enlaces acortado a los documentos originales. Los enlaces estan acortados para poder hacer un seguimiento estadiśtico de su uso.  
```sql
CREATE TABLE "lex" ("id_lex" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "nomecorto" CHAR(50) NOT NULL , "nomelongo" TEXT, "publi" CHAR(10), "datpubli" DATETIME, "numpubli" INTEGER, "anopubli" INTEGER, "tipolex" CHAR(50), "entipubl" TEXT, "urlsmd" TEXT, "notas" TEXT, "galipub" BOOL)
```  


## Tablas con datos de la explotación

* Tabla __pexmanual__: Esta tabla es modelo de [estructura](strucPexmanual.md) para las tablas que contienen los datos de la planificación de cada anualidad. Como estas tablas están creadas para la importación de datos de documento externos están diseñadas bajo ese condicionamiento. Como se quiere hacer los primeros análisis se han añadido campos con ese objetivo. Por esta razones estas tablas tienen un carácter provisional para la fase de importación.   
```sql
CREATE TABLE "pexmanual" ("idPlanAnual" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "entidad" CHAR(100), "modalidade" CHAR(50), "especiesPlan" CHAR(100), "zonaTraballo" TEXT, "diasMax" TEXT, "epocaTraballo" TEXT, "puntosControl" TEXT, "tipoCode" CHAR(4), "conxunto" BOOL, "urlFicha" TEXT, "id_plan_explotacion" INTEGER, "BMSigremar" TEXT, "idzonatra" INTEGER, "anualidad" INTEGER DEFAULT 2000, "numesp" INTEGER, "codeMod" CHAR(1), "costa" CHAR(2))
```  
Estado de las tablas pexma`aaaa`:
	* Tablas con todos los campos cubiertos
	* Tablas con campo _"idzonatra"_ vacío (2016, 2015, 2014, 2008, 2007,)
	* Tablas con los campos vacíos _"BMSigremar", "idzonatra"_ (2013, 2012, 2011, 2010, 2009,)

* Tabla __Bancos sigremar (sigbm2014)__:Es un modelo que no es el definitivo pues en estos últimos años sigremar a variado la consulta en la que presenta las propiedades de la figura geográfica.  
```sql
CREATE TABLE "sigbm2014" ("bsig" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL  UNIQUE , "fid" CHAR(20) NOT NULL , "CODIGO" CHAR(10) NOT NULL , "BANCO" TEXT, "ESTRATO" TEXT, "AREA" INTEGER, "LONGITUD" INTEGER, "ZONA" TEXT, "COFRADIA" TEXT, "REGIMEN" TEXT, "MODALIDAD" TEXT, "REC_XUNTA" TEXT, "REC_FAO" TEXT, "a_ident" INTEGER DEFAULT 2014, "misnotas" TEXT)
```  




## Tablas con datos para el análisis

* Tablas para el __análisis de especies__: Las tablas (pespec`aaaa`) están ligadas al proceso: [número de especies por plan](numespecplan.proc.md), por el que se puede tratar a las especies individualmente que en el texto original están en forma de listado.  
```sql
CREATE TABLE "pespec2016" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3))
```  


* Tablas para el __análisis de entidades__: Les entidades que participan en un plan en el documento original estan listadas por los que mediante el correspondiente tratamiento permite que puedan ser tratadas individualmente.  
El proceso número de entidades por plan generan las tablas "plantidad`aaaa`" para realizar el tratamiento de las entidades que participan en los distintos tipos de planes.  
```sql
CREATE TABLE "plantidad2016" ("ideplentidad" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER DEFAULT 2015, "idPlanAnual" INTEGER NOT NULL , "tipoCode" CHAR(4), "entidad" VARCHAR(150), "id_cofradia" INTEGER)
```  


[Volver a Bases de Datos](muestreosSQLite.md)


