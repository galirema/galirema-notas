# Cadros de planes

* Para poder enlazar con los detalles de cada plan anual y tener una imagen básicade las caracteristicas generales de cada tipo de plan.

* Estos cuadros se obtienen mediante una consulta SQL.

## El objetivo

* El resultado de la consulta es un cuadro de cuatro columnas:
  * _idPlanAnual_: Identificador del plan
  * _Entidade(1)_: Entidad o entidades que proponen el plan
  * _Modalidade_: Modalidad de captura empleada en el plan
  * _Especies(2)_: Especies objeto de la captura bajo la normativa del plan. Las especies estan expresadas con el codigo de 3 carácteres alfanuméricos oficila en la UE auspiciada por la FAO, separadas por comas. 

* En esta consulta hemos incrustado los marcas de formato de _markdown_ para que aparezca como una cuadro, también se ha introducido las url que los enlazan con los post de __galicia mariñeira__ donde se publican los detalles de cada plan anual.

* En esta consulta icluye el enlace con los post de detalle de cada plan anual de explotación, en este caso para un site drupal que es galiciamarineira.info.  
Para que sea eficiente el nombre de estos post debe ser generado automaticamente y en el que deben entrar una serie de elementos que identifiquen exactamente cada plan.  
Los elementos elegidos para generar el nombre del post son los siguientes:
 * _pexma_ es un acrónimo de __Plan de EXplotación MArisquera__
 * _año de vigencia del plan anual_ cuatro dígitos __0000__
 * _Tipo de plan_ en los que la orden incluye a ese plan que en la tabla anual está recogido en el campo _«tipoCode»_
 * _identificación del plan_ para eso utilizamos el campo _«idPlanAnual»_ de la tabla de importación de datos de la que es la clave primaria y se autoincrementa cada vez que genera uno nuevo.  
 Como es un numero entero para integrarlo en una variable alfanumerica como es el nombre del post debemos introducir ceros a la izquierda para que mantenga los tres dígitos necesarios.  
 Para hacerlo automaticamente en la consulta utilizamos la expresión _CASE WHEN - ELSE- END_  
 ```sql
 CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual" ELSE "idPlanAnual
 ```  
 Esta expresión se intercala dos veces en la consulta.

## La consulta SQL
 
* La consulta tiene tres partes:
  * ___codplan1___: Contiene la parte visible del enlace que es código del campo _idPlanAnual_ escrito con tres dígitos con las marcas de markdown (entre corchetes)
  * ___lingazon1___: La segunda parte del enlace la URL que señala al post con las correspondientes marcas (entre paréntesis)
  * ___fila plan___: el resto de la información de la tabla con las marcas correspondientes (en este caso el signo tuberia, la barra vertical)

Mostamos un ejemplo de esta consulta realizada para el año 2018 y las autorizaciones como tipo de plan.

```sql
SELECT 
   '[' || CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual"
   WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual"
   ELSE "idPlanAnual"  END AS "codplan1",
   '](http://www.galiciamarineira.info/content/pexma' || "anualidad" || "tipoCode"
   || CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" || ')|'
   WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual" || ')|'
   ELSE "idPlanAnual" || ')|'  END AS "lingazon1",
   RTRIM("entidad") || '|' || RTRIM("modalidade") || '|' || RTRIM("especiesPlan") AS "fila plan"
   FROM "pexma2018"
   WHERE "tipoCode"
   LIKE 'A%'
   ORDER by "idPlanAnual" ASC;
   ```
## El resultado

* Resultado de la consulta ya tiene incluidas las marcas del formato markdown pero debemos limpiarlo de los restos del formato csv al haber dividido la consulta en los tres campos que señalamos y que debemos eliminar

codplan1	lingazon1	fila plan  
[001	](http://www.galiciamarineira.info/content/pexma2018AAUT001)|	A.M. Fonte Santa Helena-Baldaio|A pé;|CTG, CLJ, COC, RAE, OYF,  
[002	](http://www.galiciamarineira.info/content/pexma2018AAUT002)|	A.M Esteiro do río Anllóns|A pé;|COC, CLJ,  
[003	](http://www.galiciamarineira.info/content/pexma2018AAUT003)|	C.P. A Coruña|A pé; Embarcación;|CTG, CTS, COC, CLJ, OYF, OYG,  
[004	](http://www.galiciamarineira.info/content/pexma2018AAUT004)|	C.P. A Pobra do Caramiñal|A pé;|CTG, CLJ, CTS, COC, RAE,  
[005	](http://www.galiciamarineira.info/content/pexma2018AAUT005)|	C.P. A Pobra do Caramiñal|Embarcación;|CTG, CLJ, CTS, COC, VNA, VNR, VEV, DSX,  
[006	](http://www.galiciamarineira.info/content/pexma2018AAUT006)|	C.P. Aguiño|Embarcación;|CTS, VNR, VEV, DSX,  
[007	](http://www.galiciamarineira.info/content/pexma2018AAUT007)|	C.P. Barallobre|A pé;|CTS, CTG, CLJ, COC, OYF, VNA, PEE, OYG, LPZ, EQK, EQI,  
  
