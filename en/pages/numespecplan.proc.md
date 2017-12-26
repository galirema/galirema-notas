# Proceso número de especies por plan

## Tratamiento Campo "especiesPlan"

* No campo "especiesPlan" están as especies obxecto de explotación cun formato estandarizado o código alfa3-FAO separado por comas.

* No documento do plan Xeral publicado no DOG está redactado co nome común da especie, este formato presenta unha grande variabilidade por moitos motivo desde culturais ata ortográficos. Por este motivo optamos polo estándar propiciado pola UE e empregado obrigatoriamente na publicación nas estatísticas de primeira venda.

* A relación existente entre o nome común e o código Alfa3-FAO está expresada na táboa "__especienomes__"   

* A secuencia deste proceso é a seguinte:

## Estandarizar as especies por plan

1. O normal é que o listado o obteñamos do plan xeral e polo tanto este paso o fagamos cando importamos o plan xeral. A situación anormal esta no caso dos plans de algas que o listado das especies está en cada plan anual.

1. O para cambiar o nome común polo código Alfa3 empregamos a ferramenta de substitución de texto do editor, tendo especial coidado en eliminar as expresións lingüísticas do listado (conxuncións copulativas normalmente) e que cada código termine con unha coma e deste xeito facilitemos a consulta deste campo na base de datos.

1. O campo da táboa que o listado das especies de cada plan na base de datos de importación é _"especiesPlan"_

## Táboa pespec"aaaa"

1. Para poder relacionar mellor cada plan con unha especie creamos para cada ano a táboa _pespec_ coa cifra do ano a que corresponde. O comando SQL para a súa creación é o seguinte:  
```sql
CREATE TABLE "pespec2016" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));
```

1. Para desagregar o campo _"especiesPlan"_ para poder cargar o campo _"codeFAO"_ de _"pespecaaaa"_ empregamos a consulta SQL:  
```sql
SELECT "anualidad", "idPlanAnual", "tipoCode", RTRIM("especiesPlan") FROM "pexma2013" ORDER BY "idPlanAnual" ASC;
```

1. O resultado da consulta en formato csv o manipulamos para que cada especie dun plan cos códigos que identifican o plan están nunha liña do texto (si un plan ten 4 especie xeraremos 4 liñas que conterá a información correspondente `"anualidad","idPlanAnual","tipoCode","codeFAO"`

1. O arquivo csv coa nova estrutura xerada e coa cabeceira `"anualidad","idPlanAnual","tipoCode","codeFAO"` esta listo para ser cargado na táboa _"pespecaaaa"_ 

## Cargar o campo "numesp" das táboas de importación

1. A información do campo _"numesp"_ é o numero de especies que regula cada plan no territorio de xestión

1. Para facer esta operación construímos os comandos SQL para cada rexistro da táboa _"pexmaaaaa"_ cunha consulta SQL a táboa _"pespecaaaa"_ do ano do plan.  
```sql
SELECT 'UPDATE pexma2007 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2007" GROUP BY "idPlanAnual";
```  
o resultado desta consulta son os comandos SQL para cargar dicho campo en cada rexistro. Hai que modificar o carácter `+` polo carácter `'` para que poidan executarxes os comandos SQL.

## Consultas executadas:

```sql

-- pespec2004

CREATE TABLE "pespec2004" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2004 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2004" GROUP BY "idPlanAnual";


-- pespec2005

CREATE TABLE "pespec2005" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2005 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2005" GROUP BY "idPlanAnual";


-- pespec2006

CREATE TABLE "pespec2006" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2006 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2006" GROUP BY "idPlanAnual";

-- pespec2007

CREATE TABLE "pespec2007" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2007 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2007" GROUP BY "idPlanAnual";

-- pespec2008

CREATE TABLE "pespec2008" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2008 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2008" GROUP BY "idPlanAnual";

-- pespec2009

CREATE TABLE "pespec2009" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2009 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2009" GROUP BY "idPlanAnual";


-- pespec2010

CREATE TABLE "pespec2010" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2010 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2010" GROUP BY "idPlanAnual";

-- 2011

CREATE TABLE "pespec2011" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2011 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2011" GROUP BY "idPlanAnual";

---- variante para cargar lo poliquetos del año 2012
SELECT 'UPDATE pexma2011 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL;' AS orden FROM "pespec2011" WHERE "tipoCode" LIKE 'K%' GROUP BY "idPlanAnual";

-- 2012

CREATE TABLE "pespec2012" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2012 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2012" GROUP BY "idPlanAnual";

---- variante para cargar lo poliquetos del año 2012
SELECT 'UPDATE pexma2012 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL;' AS orden FROM "pespec2012" WHERE "tipoCode" LIKE 'K%' GROUP BY "idPlanAnual";

-- 2013
CREATE TABLE "pespec2013" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));
SELECT 'UPDATE pexma2013 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2013" GROUP BY "idPlanAnual";

---- variante para cargar lo poliquetos del año 2013
SELECT 'UPDATE pexma2013 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2013" WHERE "tipoCode" LIKE 'K%' GROUP BY "idPlanAnual";

-- 2014

CREATE TABLE "pespec2014" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT "anualidad", "idPlanAnual", "tipoCode", RTRIM("especiesPlan") FROM "pexma2014" ORDER BY "idPlanAnual" ASC;

SELECT 'UPDATE pexma2014 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2014" GROUP BY "idPlanAnual";

---- variante para cargar lo poliquetos del año 2014
SELECT 'UPDATE pexma2014 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2014" WHERE "tipoCode" LIKE 'K%' GROUP BY "idPlanAnual";

-- 2015

CREATE TABLE "pespec2015" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3))

---- variante para cargar lo poliquetos del año 2015
SELECT 'UPDATE pexma2015 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2015" WHERE "tipoCode" LIKE 'K%' GROUP BY "idPlanAnual";

-- 2016

CREATE TABLE "pespec2016" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2016 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2016" GROUP BY "idPlanAnual";

---- variante para cargar lo poliquetos del año 2016
SELECT 'UPDATE pexma2016 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2016" WHERE "tipoCode" LIKE 'K%' GROUP BY "idPlanAnual";

-- 2017

CREATE TABLE "pespec2017" ("idesplan" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL , "anualidad" INTEGER, "idPlanAnual" INTEGER, "tipoCode" CHAR(4), "codeFAO" CHAR(3));

SELECT 'UPDATE pexma2017 SET numesp= '|| COUNT("codeFAO") || ' WHERE idPlanAnual = +' || "idPlanAnual" ||'+ AND numesp ISNULL' AS orden FROM "pespec2017" GROUP BY "idPlanAnual";
```
