# Generación de las fichas de los planes anuales

## El objetivo

* Una vez que la información de las distintas órdenes del Plan General de Explotación Marisquera está introducida en la base de datos se pueden ejecutar consultas que generen un informe con la normativa de cada plan anual.

* Los entornos gráficos de manejo de las bases de datos pueden tener programas para generar este tipo de informes. Como en el proyecto __Galirema__ usamos __Markdown__ para generar documentos universales que pueden ser tranformados en documentos HTML, PDF, DOC, etc...  
La principal destino es el de documentos HTML para ser publicados en la web.

* Por esta razon en la consulta incrustamos las marcas de formateo __markdown__ para que el resltado de la consulta tenga un formato que nos permite no utilizar esos programas generadores de informes.

## La consulta SQL

* La consulta obtiene toda la información que que hemos digitalizado de las órdenes publicadas en el _D.O.G._ y en los documentos de los planes anuales publicado en formato _PDF_ en _pescadegalicia.gal_ y deja espacio para cuandola información esté relacionada con la información del gis _Sigremar_.


```sql
SELECT 
'<!--Pexma2008' || "tipoCode"  AS 'Nome da Ficha',
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual" ELSE "idPlanAnual"  END AS "codplan1", -- Comentario inicial: Nombre del post
'-->¿-?## Pexma 2008¿-?### ' || "tipoCode" || '¿-?# ' AS "Encabezado01",
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" || ' ' WHEN length("idPlanAnual")= 2 THEN '0' ||"idPlanAnual" || ' ' ELSE "idPlanAnual" || ' '  END AS codplan2, 
RTRIM("entidad") AS "Encabezado02",
'¿-? ¿-?|Campo|Contenido|¿-?|:----|:--------|¿-?Código plan|' As "PlanAnual",
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual" ELSE "idPlanAnual"  END AS 'codplan3', 
'¿-?entidad|' || rtrim("entidad") AS Entidade,
'¿-?modalidad|' || rtrim("modalidade") AS Modalidade,
'¿-?especies|' || rtrim("especiesPlan") AS Especies,
'¿-?zona de Trabajo |' || rtrim("zonaTraballo") || ' %%2008 ' || substr("tipoCode",1,1) AS Zona,
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual"||'%%' WHEN length("idPlanAnual")= 2 THEN '0' || "idPlanAnual"||'%%' ELSE "idPlanAnual"||'%%'  END AS "codplan4",
'¿-?dias max. |' || rtrim("diasMax") AS Dias,
'¿-?epoca de Trabajo |' || rtrim("epocaTraballo") AS Calendario,
'¿-?puntos de Control|' || rtrim("puntosControl") AS Control,
'¿-?Tipo de plan|' || "tipoCode" || '¿-?Conjunto|' AS Tipoplan,
CASE WHEN UPPER("conxunto")= 'T' THEN 'SI' ELSE 'NO' END,
'¿-?url Ficha|<' ||  "urlFicha" || '>¿-?BMSigremar|'|| "BMSigremar" AS "ShortURL-resto"
FROM "pexma2008"
-- WHERE "tipoCode" LIKE 'A%'  -- filtro para ejecutar por tipo de plan
ORDER BY "tipoCode", "idPlanAnual";
```

* Para filtrar la consulta por tipo de plan hay que descomentar la clausula WHERE y elegir el tipo de plan por su primer caracter (en el ejemplo estaria filtrada por los planes de autorizaciones «AAUT»).

* Para facilitar el formateado del informe del plan hemos introducido en la consulta además de las marcas de __markdown__ unas marcas propias como ___¿-?___ que indica que debo introducir un retorno de carro. Otra marca propia es el doble signo de tanto por ciento ___%%___ para enmarcar una información por ahora desconocida como es el código de las [AXU](indicesZonasProduccion.md) _«Áreas de Xestión Unificada»_ que es las zonas de producción que son gestionadas por la misma normativa.

* Para completar el documento obtenido con la consulta, utilizamos unas de las características de markdown para facilitar el uso de abreviaturas que puenden repetirse muchas veces en un documento que consiste en añadir una lista de las abreviaturas y su significado al final del documento. (En el caso del markdown de GitHub no funciona como puedes comprobar [aqui](draft-plangeneral2016.md)).  
El efecto que produce es que cuando pasas el puntero del ratón se impresiona en la pantalla el significado de la abreviatura como sucede en la [publicación final](http://www.galiciamarineira.info/content/planes-general-y-espec%C3%ADficos-2018) o en la imagen de mas adelante. 

```markdown
*[CTS]: Ameixa babosa
*[ULO]: Cornicha
*[VNA]: Ameixa bicuda
*[CTG]: Ameixa fina
*[CLJ]: Ameixa xaponesa
*[VNR]: Ameixa rubia
*[KLK]: Ameixón
*[GKL]: Rabioso
*[UTL]: Arola
*[COC]: Berberecho
```

![ejemplo001](https://lh3.googleusercontent.com/ZObxbix2-0egUI4JbGXypPjhoj6rQcC0DfTmNUXYna9tfX2CFnM7iMDenV867c7iBEUBK0eR5YIfQKq_UMPveNXfBrDlE10abkchVhh2t3ZzRy2UjHILfqkGUdRcNl9hF-1JjPlJQNAlRWR7fhHCWpWV01VpTgrQ55pl5-yetlx1Mfdy8h2NDFDVKtKiTUdIjAragfGq-Rr09VFGousU5lyFutbbOn77KFjpVRAE7HoaHt5y_rmGHMGNg_qxzkWmfF6mKCwbQnIU2eOJCHNkWbBckQgsq2v-4hKZfRJv826Jr8_64HYcQCrSwvzM1kbtyTE-zE1TvkPWTWbhLBtibcE0aWE0RbjBvApRKzQeZCvbTkFJtaGQSLo_JfLi68jhOVQj0EKO7KScjLO3yUmCMX7VVhqGWdzO_Fwwk3LVFWaiOi20hiUR_E6bhVNAPICEI6RNDAlm0F__GzjNOaeiUP2zbUXIu_4SqAhA10nvrkPHNBILn81cZDBVkmgMYh8oamyBfDSbbEnxCErQjGc5whyStTBh3aCtv5Y7Ti_LmjlprH4PEfWF1ByiQljbMZ4HkgaE5jHMYvl8bpppjPzYp1gFFaqH_OGbAzpe2ICsCDp3zDWpzGaKRJBDP-SW1zNrjfDk3fJAzwyGDOj94Jzz-SjdAQMp9mDw=w374-h289-no)

## El resultado de la consulta

* Como ejemplo hemos elejido el 2008 ya que es el primer año que tenemos acceso a los planes individuales anuales y por lo tanto tenemos información de todos los campos de la tabla.

* El resultado nos devuelve 228 filas, una por cada plan aprobado.

~~~
"Nome da Ficha"	"codplan1"	"Encabezado01"	"codplan2"	"Encabezado02"	"PlanAnual"	"codplan3"	"Entidade"	"Modalidade"	"Especies"	"Zona"	"codplan4"	"Dias"	"Calendario"	"Control"	"Tipoplan"	""CASE WHEN UPPER(""conxunto"")= 'T' THEN 'SI' ELSE 'NO' END""	"ShortURL-resto"
"<!--Pexma2008AAUT"	"001"	"-->¿-?## Pexma 2008¿-?### AAUT¿-?# "	"001 "	"C.P. O Vicedo"	"¿-? ¿-?|Campo|Contenido|¿-?|:----|:--------|¿-?Código plan|"	"001"	"¿-?entidad|C.P. O Vicedo"	"¿-?modalidad|A pé;"	"¿-?especies|DON,"	"¿-?zona de Trabajo |Praia de Arealonga e Lombo das Navallas %%2008 A"	"001%%"	"¿-?dias max. |30"	"¿-?epoca de Trabajo |Xaneiro, febreiro, De outubro a decembro"	"¿-?puntos de Control|Caseta de Arealonga e Lombo das Navallas"	"¿-?Tipo de plan|AAUT¿-?Conjunto|"	"NO"	"¿-?url Ficha|<http://goo.gl/SphStt>¿-?BMSigremar|Praia de Arealonga, dende Os Castelos a Punta Pena Furada e Lombo das Navallas (CL-117),"
"<!--Pexma2008AAUT"	"002"	"-->¿-?## Pexma 2008¿-?### AAUT¿-?# "	"002 "	"A.M. Fonte Santa Helena-Baldaio"	"¿-? ¿-?|Campo|Contenido|¿-?|:----|:--------|¿-?Código plan|"	"002"	"¿-?entidad|A.M. Fonte Santa Helena-Baldaio"	"¿-?modalidad|A pé;"	"¿-?especies|CTG, CTS, COC, OYF,"	"¿-?zona de Trabajo |Lagoas de Baldaio %%2008 A"	"002%%"	"¿-?dias max. |44"	"¿-?epoca de Trabajo |Marzo, abril, De xuño a decembro"	"¿-?puntos de Control|Fonte Santa Helena"	"¿-?Tipo de plan|AAUT¿-?Conjunto|"	"NO"	"¿-?url Ficha|<http://goo.gl/LOzM1X>¿-?BMSigremar|Lagoas de Baldaio (CF-040), (CF-167),"
"<!--Pexma2008AAUT"	"003"	"-->¿-?## Pexma 2008¿-?### AAUT¿-?# "	"003 "	"A.M. Esteiro do río Anllóns"	"¿-? ¿-?|Campo|Contenido|¿-?|:----|:--------|¿-?Código plan|"	"003"	"¿-?entidad|A.M. Esteiro do río Anllóns"	"¿-?modalidad|A pé;"	"¿-?especies|COC, CLJ, PEE,"	"¿-?zona de Trabajo |Zona de autorización (marxe dereita da enseada do río Anllóns, entre illa Cagallóns e liña de punta Revoleas e enseada de Insua) %%2008 A"	"003%%"	"¿-?dias max. |COC: 220 días, CLJ: 9 días; PEE: 9 días"	"¿-?epoca de Trabajo |COC: de xaneiro a decembro; CLJ e PEE: decembro"	"¿-?puntos de Control|Pedras de Cambón, O Pendón, Ourixeira, Lodeiro"	"¿-?Tipo de plan|AAUT¿-?Conjunto|"	"NO"	"¿-?url Ficha|<http://goo.gl/Ejqf61>¿-?BMSigremar|Zonas: (A, A1/2, A3, G, (CM-121),) O Couto (CM-093), Zona Bígaro; "
"<!--Pexma2008AAUT"	"004"	"-->¿-?## Pexma 2008¿-?### AAUT¿-?# "	"004 "	"C.P. A Coruña"	"¿-? ¿-?|Campo|Contenido|¿-?|:----|:--------|¿-?Código plan|"	"004"	"¿-?entidad|C.P. A Coruña"	"¿-?modalidad|A pé; Embarcación;"	"¿-?especies|CTG, CTS, CLJ, COC,"	"¿-?zona de Trabajo |Zonas de autorización %%2008 A"	"004%%"	"¿-?dias max. |A pé: 13 días; Embarc: 24 días"	"¿-?epoca de Trabajo |A pé: de setembro a decembro; Embarc: de xaneiro a marzo e de setembro a decembro"	"¿-?puntos de Control|Punto de venda autorizado no lugar das Xubias (A Coruña)"	"¿-?Tipo de plan|AAUT¿-?Conjunto|"	"NO"	"¿-?url Ficha|<http://goo.gl/3mNONd>¿-?BMSigremar|zona de autorización (CF-001), (CF-002), (CF-004), (CF-005), (CF-006), (CF-007), (CF-008), (CF-009), (CF-166),"
~~~

* Para que sean mas visible en el ejemplo he utilizado como separador en vez de la coma (¨,¨) el tabulador (¨\t¨) las marcas que debo eliminar o cambiar son las siguientes:


|Marca|Acción|Nueva Marca|Comentario|
|:----|:----:|----------:|----------|
|"\t"|Eliminar||Quitmos la separación entre los campos de la consulta|
|¿-?|Cambiar| \n|Cambiamos la marca por un retorno de carro añadiendo una linea|
|"\n"|Cambiar| \n\n\n|Pera separar dos registros distintos añadimos 3 retornos de carro (3 lineas)|

* Como resultado de los cambios realizados es el sigiente:

```markdown
<!--Pexma2008AAUT001-->
## Pexma 2008
### AAUT
# 001 C.P. O Vicedo
 
|Campo|Contenido|
|:----|:--------|
Código plan|001
entidad|C.P. O Vicedo
modalidad|A pé;
especies|DON,
zona de Trabajo |Praia de Arealonga e Lombo das Navallas %%2008 A001%%
dias max. |30
epoca de Trabajo |Xaneiro, febreiro, De outubro a decembro
puntos de Control|Caseta de Arealonga e Lombo das Navallas
Tipo de plan|AAUT
Conjunto|NO
url Ficha|<http://goo.gl/SphStt>
BMSigremar|Praia de Arealonga, dende Os Castelos a Punta Pena Furada e Lombo das Navallas (CL-117),


<!--Pexma2008AAUT002-->
## Pexma 2008
### AAUT
# 002 A.M. Fonte Santa Helena-Baldaio
 
|Campo|Contenido|
|:----|:--------|
Código plan|002
entidad|A.M. Fonte Santa Helena-Baldaio
modalidad|A pé;
especies|CTG, CTS, COC, OYF,
zona de Trabajo |Lagoas de Baldaio %%2008 A002%%
dias max. |44
epoca de Trabajo |Marzo, abril, De xuño a decembro
puntos de Control|Fonte Santa Helena
Tipo de plan|AAUT
Conjunto|NO
url Ficha|<http://goo.gl/LOzM1X>
BMSigremar|Lagoas de Baldaio (CF-040), (CF-167),


<!--Pexma2008AAUT003-->
## Pexma 2008
### AAUT
# 003 A.M. Esteiro do río Anllóns
 
|Campo|Contenido|
|:----|:--------|
Código plan|003
entidad|A.M. Esteiro do río Anllóns
modalidad|A pé;
especies|COC, CLJ, PEE,
zona de Trabajo |Zona de autorización (marxe dereita da enseada do río Anllóns, entre illa Cagallóns e liña de punta Revoleas e enseada de Insua) %%2008 A003%%
dias max. |COC: 220 días, CLJ: 9 días; PEE: 9 días
epoca de Trabajo |COC: de xaneiro a decembro; CLJ e PEE: decembro
puntos de Control|Pedras de Cambón, O Pendón, Ourixeira, Lodeiro
Tipo de plan|AAUT
Conjunto|NO
url Ficha|<http://goo.gl/Ejqf61>
BMSigremar|Zonas: (A, A1/2, A3, G, (CM-121),) O Couto (CM-093), Zona Bígaro; 


<!--Pexma2008AAUT004-->
## Pexma 2008
### AAUT
# 004 C.P. A Coruña
 
|Campo|Contenido|
|:----|:--------|
Código plan|004
entidad|C.P. A Coruña
modalidad|A pé; Embarcación;
especies|CTG, CTS, CLJ, COC,
zona de Trabajo |Zonas de autorización %%2008 A004%%
dias max. |A pé: 13 días; Embarc: 24 días
epoca de Trabajo |A pé: de setembro a decembro; Embarc: de xaneiro a marzo e de setembro a decembro
puntos de Control|Punto de venda autorizado no lugar das Xubias (A Coruña)
Tipo de plan|AAUT
Conjunto|NO
url Ficha|<http://goo.gl/3mNONd>
BMSigremar|zona de autorización (CF-001), (CF-002), (CF-004), (CF-005), (CF-006), (CF-007), (CF-008), (CF-009), (CF-166),
```
* Añadimos al final del archivo la biblioteca de las abreviaturas

* Si utilizamos un editor de markdow ya podemos exportarlo a otro con formato HTML que podremos subir a la web donde queremos publicarlo


## Procesos Ejecutados

|anualidad|lineas CSV|lineas MD|Lineas HTML|
|--------:|---------:|--------:|----------:|
|2018|234|||
|2017|226|||
|2016|229|||
|2015|234|||
|2014|229|||
|2013|219|||
|2012|210|||
|2011|209|||
|2010|218|||
|2009|233|||
|2008|228|||
|2007|225|||
|2006|211|||
|2005|191|||
|2004|185|||
|2003|173|||
|2002|162|||
|2001|169|||
|2000|166|||

