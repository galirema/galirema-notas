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
'<!--Pexma2000' || "tipoCode"  AS 'Nome da Ficha',
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual" ELSE "idPlanAnual"  END AS "codplan1", -- Comentario inicial: Nombre del post
'-->¿-?## Pexma 2000¿-?### ' || "tipoCode" || '¿-?# ' AS "Encabezado01",
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" || ' ' WHEN length("idPlanAnual")= 2 THEN '0' ||"idPlanAnual" || ' ' ELSE "idPlanAnual" || ' '  END AS codplan2, 
RTRIM("entidad") AS "Encabezado02",
'¿-? ¿-?|Campo|Contenido|¿-?|:----|:--------|¿-?Código plan|' As "PlanAnual",
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual" WHEN length("idPlanAnual")= 2 THEN '0'||"idPlanAnual" ELSE "idPlanAnual"  END AS 'codplan3', 
'¿-?entidad|' || rtrim("entidad") AS Entidade,
'¿-?modalidad|' || rtrim("modalidade") AS Modalidade,
'¿-?especies|' || rtrim("especiesPlan") AS Especies,
'¿-?zona de Trabajo |' || rtrim("zonaTraballo") || ' %%2000 ' || substr("tipoCode",1,1) AS Zona,
CASE WHEN length("idPlanAnual")= 1 THEN '00' || "idPlanAnual"||'%%' WHEN length("idPlanAnual")= 2 THEN '0' || "idPlanAnual"||'%%' ELSE "idPlanAnual"||'%%'  END AS "codplan4",
'¿-?dias max. |' || rtrim("diasMax") AS Dias,
'¿-?epoca de Trabajo |' || rtrim("epocaTraballo") AS Calendario,
'¿-?puntos de Control|' || rtrim("puntosControl") AS Control,
'¿-?Tipo de plan|' || "tipoCode" || '¿-?Conjunto|' AS Tipoplan,
CASE WHEN UPPER("conxunto")= 'T' THEN 'SI' ELSE 'NO' END,
'¿-?url Ficha|<' ||  "urlFicha" || '>¿-?BMSigremar|'|| "BMSigremar" AS "ShortURL-resto"
FROM "pexma2000"
-- WHERE "tipoCode" LIKE 'A%'  -- filtro para ejecutar por tipo de plan
ORDER BY "tipoCode", "idPlanAnual";
```

* Para filtrar la consulta por tipo de plan hay que descomentar la clausula WHERE y elegir el tipo de plan por su primer caracter (en el ejemplo estaria filtrada por los planes de autorizaciones «AAUT»).

* Para facilitar el formateado del informe del plan hemos introducido en la consulta además de las marcas de __markdown__ unas marcas propias como ___¿-?___ que indica que debo introducir un retorno de carro. Otra marca propia es el doble signo de tanto por ciento ___%%___ para enmarcar una información por ahora desconocida como es el código de las [AXU](indicesZonasProduccion.md) _«Áreas de Xestión Unificada»_ que es las zonas de producción que son gestionadas por la misma normativa.

* Para completar el documento obtenido con la consulta, utilizamos unas de las características de markdown para facilitar el uso de abreviaturas que puenden repetirse muchas veces en un documento que consiste en añadir una lista de las abreviaturas y su significado al final del documento.

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


