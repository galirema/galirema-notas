# Informe sobre Plan General de Explotación Marisquera 

# B) Tratamiento de datos

## Inicio

* El informe constará de los siguientes módulos:

    + [M00](#M00): Ficha descriptiva de la Orden.
    + [M01](#M01): Tipos de plan aprobados en la Orden.
    + [M02](#M02): Nivel de colaboración.
    + [M03](#M03): Especies objetivo de captura
    + [M04](#M04): Modalidades de captura
    + [M05](#M05): Duración da actividad y época de captura
    + [M06](#M06): Entidades participantes
    + [M07](#M07): Las zonas de la costa en la orden


* En este apartado se presentan las consultas para obtener los datos para la ralización del informe y los cuadros para la elaboración de los gráficos.

* En los cuadros el encabezado que tiene __«comillas españolas»__ corresponde a un dato _alfanumérico_ y los datos están presentados con __'comillas simples'__. los encabezados y los datos sin comillas son tratados como _numéricos_ en el gráfico.
	+ Comillas en [Wikipedia ES](https://es.wikipedia.org/wiki/Comillas) y en [wikilengua](http://www.wikilengua.org/index.php/Comillas)


* Las consultas que se utilizan como ejemplo son las realizadas para el año 2016

* Los graficos estan hechos con la herramienta [google chart][] son script escritos en javascript 

* El código de las plantillas de estos gráficos se publicarán en [jsfiddle][].  
Los graficos publicados en las páginas web estan en formato __.png__.

## M00

### Ficha descriptiva de la Orden.

+ Es una ficha que resume los aspectos analizados en los distintos apartados del informe.

## M01

### Tipos de plan aprobados en la Orden.

* __Gráfico M01-01 Por tipo de plan__  

```sql
SELECT "anualidad", "tipoCode", COUNT("tipoCode") FROM "pexma2016" GROUP BY "tipoCode" ORDER BY "tipoCode";
```
* Cuadro base del gráfico M01-01 (__Número de planes por tipo de plan__)

|año|«Tipo de plan»|num. de planes|
|:--|:----------:|-------------:|
|2016|'AAUT'|46|
|2016|'BESP'|48|
|2016|'DPER'|35|
|2016|'FEQD'|18|
|2016|'GSOL'|25|
|2016|'HPEN'|6|
|2016|'IALG'|18|
|2016|'JANE'|9|

* [Plantilla Gráfico M01-01](https://goo.gl/TswyN0)

[volver a Inicio](#Inicio)

## M02

### Nivel de colaboración entre entidades.

* __Gráfico M02-01-Nivel de colaboración. Plan General 2016__  

```sql
SELECT "anualidad", CASE WHEN UPPER("conxunto") != 'F' THEN 'Plan Conxunto' ELSE 'Individual' END, COUNT("conxunto") FROM "pexma2016" GROUP BY "conxunto";  
```

* Cuadro base del gráfico M02-01 (__Nivel de colaboración en el plan general__)

|«Plan»|Num. de planes|
|----|-------------:|
|'Individual'|172|
|'Plan Conxunto'|33|

	
* [Plantilla Gráfico M02-01](https://goo.gl/Ge8uqz)



* __Gráfico M02-03 - Nivel de colaboración por tipos de plan 2016__  

```sql
SELECT "anualidad", "tipoCode", CASE WHEN UPPER("conxunto") != 'F' THEN 'Plan Conxunto' ELSE 'Individual' END, COUNT("conxunto") FROM "pexma2016" GROUP BY "tipoCode", "conxunto" ORDER BY "tipoCode";  
```

* Cuadro base del gráfico M02-03A (__Nivel de colaboración según tipos de plan__)

	* La variante A del gráfico M02-03 incluye la columna %individual para facilitar su comprensión al comparar con el valor de los planes conjuntos.

|«Tipo de Plan»|Individual|«% individual»|Plan Conxunto|«N. Planes»|
|:----------:|---------:|:------------:|------------:|:---------:|
|'AAUT'|45|'97,83'|1|'1'|
|'BESP'|37|'77,08'|11|'11'|
|'DPER'|34|'97,14'|1|'1'|
|'FEQD'|12|'66,67'|6|'6'|
|'GSOL'|16|'64,00'|9|'9'|
|'HPEN'|4|'66,67'|2|'2'|
|'IALG'|16|'88,89'|2|'2'|
|'JANE'|8|'88,89'|1|'1'|


* [Plantilla Gráfico M02-03A](https://goo.gl/Ln4nP2)

[volver a Inicio](#Inicio)

## M03

### Especies objetivo de captura

* __Gráfico M03-01 Especies aprovechadas__

```sql
-- Moluscos
SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'A%' OR "tipoCode" LIKE 'B%' OR "tipoCode" LIKE 'G%' OR "tipoCode" LIKE 'H%' GROUP BY "codeFAO" ORDER BY "codeFAO"; 
  
-- Crustáceos 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'D%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Equinodermos 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'F%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Actinias 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'J%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Algas 

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";

-- Poliquetos

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'K%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```

* Cuadro base del gráfico M03-01 __Especies aprovechadas__


|«Grupo %»|Num. Especies|
|:--------|------------:|
|'Moluscos 40,91%'|27|
|'Crustáceos 1.52%'|1|
|'Equinodermos 3,03%'|2|
|'Actinias 1,52%'|1|
|'Algas 53,03%'|35|

* El valor del % se calcula aparte no esta en el resultado de las consultas _SQL_

* [Plantilla Gráfico M03-01](https://goo.gl/kC1zng)

[volver a Inicio](#Inicio)


## M04

### Modalidades de captura

* __Gráfico M04-00x. Planes por modalidad de captura.__

```sql

SELECT "codeMod", COUNT("tipoCode") FROM "pexma2016" GROUP BY "codeMod" ORDER BY "codeMod";

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```


* Cuadro base del gráfico M04-00x. (__Planes por modalidad de captura.__)

|«Modalidad»|Num. de planes|
|:--------|-------------:|
|'A: A pie'|75|
|'B: Embarc.'|39|
|'C: A pie, embarc.'|23|
|'D: Rastro vieira'|5|
|'E:Endeño'|2|
|'F: Buceo'|15|
|'G: Apnea'|5|
|'H: Apnea, Buceo'|36|
|'I: Apnea, Buceo, Bicheiro'|1|
|'J: A pie, Buceo'|2|
|'K: Apnea, Buceo, A Pie'|2|


* [Plantilla Gráfico M04-00x](https://goo.gl/J39XT2)



* __Gráfico M04-01 Modalidad de captura por tipo de plan__

```sql
SELECT "tipoCode", "codeMod",  COUNT("tipoCode") FROM "pexma2016" GROUP BY "codeMod", "tipoCode" ORDER BY "tipoCode", "codeMod";

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```

* Cuadro base del gráfico M04-01b (__Modalidad de captura por tipo de plan__)

|«Tipo de plan»| A | B | C | D | E | F | G | H | I | J | K |
| :----------- | --| --| --| --| --| --| --| --| --| --| --|
| 'AAUT'       | 24| 14|  6|  2|  0|  0|  0|  0|  0|  0|  0|
| 'BESP'       | 28| 12|  3|  3|  2|  0|  0|  0|  0|  0|  0|
| 'DPER'       |  8| 13| 14|  0|  0|  0|  0|  0|  0|  0|  0|
| 'FEQD'       |  5|  0|  0|  0|  0|  8|  0|  3|  1|  1|  0|
| 'GSOL'       |  1|  0|  0|  0|  0|  0|  5| 19|  0|  0|  0|
| 'HPEN'       |  0|  0|  0|  0|  0|  1|  0|  5|  0|  0|  0|
| 'IALG'       |  8|  0|  0|  0|  0|  3|  0|  5|  0|  1|  1|
| 'JANE'       |  1|  0|  0|  0|  0|  3|  0|  4|  0|  0|  1|


* [Plantilla Gráfico M04-01b](https://goo.gl/jvn30F)

[volver a Inicio](#Inicio)


## M05

### Duración da actividad y época de captura

* Actualmente no se procesa este apartado porque se necesita un tratamiento más elaborado por el tipo de datos que poseemos.

## M06

### Entidades participantes

* __Gráfico M06-01 Tipo de entidades promotoras de planes de explotación en 2016__  

    * Basado en la vista __entidad16-01__  

```sql
CREATE VIEW "entidad16-01" AS  SELECT pen16.ideplentidad, pen16.anualidad, pen16.idPlanAnual, pen16.entidad, cfd.tipoentidad, cfd.activa, cfd.id_cofradia, cfd.costa FROM plantidad2016 pen16 INNER JOIN cofradias cfd ON pen16.id_cofradia= cfd.id_cofradia GROUP BY cfd.id_cofradia ORDER BY cfd.tipoentidad;
 
SELECT "tipoentidad", COUNT("tipoentidad") FROM "entidad16-01"  GROUP BY "tipoentidad";
```

* Cuadro base del gráfico M06-01 (__Tipo de entidades promotoras de planes de explotación__)

|«Tipo de entidad»|Num. Entidades|
|:----------------|-------------:|
|'CFP'|61|
|'AGM'|4|
|'COP'|2|
|'EMP'|5|
|'ASC'|1|


* [Plantilla Gráfico M06-01](https://goo.gl/zLR2tf)



* __Gráfico M06-02 Entidades por tipo de plan. Plan general 2016.__  

```sql
CREATE VIEW "entidad16-02" AS SELECT pen16.ideplentidad, pen16.anualidad, pen16.idPlanAnual, pen16.tipoCode, pen16.entidad, cfd.tipoentidad, cfd.activa, cfd.id_cofradia, cfd.costa FROM plantidad2016 pen16 INNER JOIN cofradias cfd ON pen16.id_cofradia= cfd.id_cofradia ORDER BY pen16.tipoCode, pen16.idPlanAnual;
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'A%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'B%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'D%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'F%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'G%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'H%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'I%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" WHERE "tipoCode" LIKE 'J%' GROUP BY "tipoCode", "tipoentidad", "entidad";
  
SELECT "tipoCode", "tipoentidad", "entidad", COUNT("idPlanAnual") FROM "entidad16-02" GROUP BY "tipoCode", "tipoentidad", "entidad" ORDER BY "entidad";

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```

* Cuadro base del gráfico M06-02 (__Entidades por tipo de plan__)

|«Tipo de plan»|Cofradías|Asoc. de Mariscadores|S. Coop. Galega|Empresas|Asoc. Cofradías|
|:-----------|--------:|--------------------:|--------------:|-------:|--------------:|
|'AAUT'|28|2|1|0|0|
|'BESP'|42|3|0|0|1|
|'DPER'|36|1|0|0|0|
|'FEQD'|29|2|0|0|0|
|'GSOL'|34|0|1|0|0|
|'HPEN'|14|0|0|0|0|
|'IALG'|19|0|0|5|0|
|'JANE'|10|0|0|0|0|


* [Plantilla Gráfico M06-02](https://goo.gl/lQCqcO)



* __Gráfico M06-03: Número de planes por entidad. Plan general 2016.__  

```sql
SELECT "anualidad", "id_cofradia", "entidad", COUNT("id_cofradia") AS 'Num. Plans' FROM "plantidad2016" GROUP BY "id_cofradia" ORDER BY "Num. Plans" DESC;  

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```

* Cuadro base del gráfico M06-03 (__Número de planes por entidad__)

|Num. planes|Num. Entidades|«{ role: 'style' }»|«{ role: 'annotation' }» |
|:----------|-------------:|-----------------|:---------------------:|
|1|11|#B464FF|'11'|
|2|15|#B464FF|'15'|
|3|14|#B464FF|'14'|
|4|9|#B464FF|'9'|
|5|8|#B464FF|'8'|
|6|4|#B464FF|'4'|
|7|5|#B464FF|'5'|
|8|6|#B464FF|'6'|
|9|0|#B464FF|'0'|
|10|1|#B464FF|'1'|
|11|0|#B464FF|'0'|
|12|0|#B464FF|'0'|


* [Plantilla Gráfico M06-03](https://jsfiddle.net/galirema/a6u0h3jr/)

[volver a Inicio](#Inicio)


## M07

### Las zonas de la costa en la orden


* __Gráfico M07-04 Entidades y planes por zona de costa__  

```sql
SELECT "costa", COUNT("id_cofradia") FROM "entidad16-01" GROUP BY "costa";

SELECT "costa", COUNT("idPlanAnual") FROM "pexma2016" GROUP BY "costa";  

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```

* Cuadro base del gráfico M07-04 (__Entidades y planes por zona de costa__)

|«Zona de Costa»|Planes|«{role: 'annotation'}»|Entidades|«{role: 'annotation'}»|
|---------------|------|----------------------|---------|----------------------|
|'Galicia (GL)'| 5| '5'| 5| '5'|
|'Costa Lucensa (CL)'| 25| '25'| 11| '11'|
|'Coruña-Ferrol (CF)'| 27| '27'| 12| '12'|
|'Costa da morte (CM)'| 27| '27'| 10| '10'|
|'Muros-Noia (MN)'| 11| '11'| 4| '4'|
|'Arousa (AR)'| 52| '52'| 13| '13'|
|'Pontevedra (PO)'| 17| '17'| 8| '8'|
|'Vigo (VI)'| 41| '41'| 10| '10'|


* [Plantilla Gráfico M07-04](https://goo.gl/Zm9Rko)



* __Gráfico M07-05 Tipo de plan por zona de costa__  

```sql
SELECT "costa", "tipoCode", COUNT("idPlanAnual") FROM "pexma2016" GROUP BY "costa", "tipoCode";

SELECT "codeFAO", COUNT("codeFAO") AS 'NUM PLANES' FROM "pespec2016" WHERE "tipoCode" LIKE 'I%' GROUP BY "codeFAO" ORDER BY "codeFAO";
```

* Cuadro base del gráfico M07-05 (__Tipo de plan por zona de costa__)
2016

|'Zona de costa'|'AAUT (46)'|'BESP (48)'|'DPER (35)'|'FEQD (18)'|'GSOL (25)'|'HPEN (6)'|'IALG (18)'|'JANE (9)'|
|:-------------:|----------:|----------:|----------:|----------:|----------:|---------:|----------:|---------:|
|'CL (25)'|3|8|9|4|0|0|1|0|
|'CF (27)'|11|7|4|2|0|0|1|2|
|'CM (27)'|2|5|10|3|4|1|2|0|
|'MN (11)'|4|1|2|0|3|0|1|0|
|'AR (52)'|23|9|3|2|10|2|1|2|
|'PO (17)'|1|5|2|2|2|2|2|1|
|'VI (41)'|2|13|5|5|6|1|5|4|
|'GL (5)'|0|0|0|0|0|0|5|0|


* [Plantilla Gráfico M07-05](https://goo.gl/u3mgaf)

[volver a Inicio](#Inicio)

## Tipo de plan por zona de costa

```sql
SELECT "costa", "tipoCode", COUNT("idPlanAnual") FROM "pexma2017" GROUP BY "tipoCode", "costa";
```
* __Gráfico M07-06 AAUUT por zona de costa__  


* __Gráfico M07-07 BESP por zona de costa__  


* __Gráfico M07-08 DPER por zona de costa__  


* __Gráfico M07-09 FEQD por zona de costa__  


* __Gráfico M07-10 GSOL por zona de costa__  


* __Gráfico M07-11 HPEN por zona de costa__  


* __Gráfico M07-12 IALG por zona de costa__  


* __Gráfico M07-13 JANE por zona de costa__  


* __Gráfico M07-14 KPOL por zona de costa__  

[volver a Inicio](#Inicio)




 [google chart]: https://developers.google.com/chart/
 [jsfiddle]: https://goo.gl/TBq457

