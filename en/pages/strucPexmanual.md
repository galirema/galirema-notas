# Tabla modelo: pexmanual  

* Esquema de la tabla pexma`aaaa` comentada con la procedencia del valor de cada uno de los campos de la tabla
	* __Plan general anual__ DOG orden del plan general de explotación marisquera.
	* __pescagalicia.com__ donde estan publicados los planes de explotación anuales aprobados en la orden anual.
	* __Análisis__ recogen información cuantitativa que en los textos originales están de forma cualitativa.


```sql
CREATE TABLE "pexmanual" (
 "idPlanAnual" INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL ,
 "entidad" CHAR(100),   -- dato obtenido del plan general anual
 "modalidade" CHAR(50),   -- plan general anual
 "especiesPlan" CHAR(100),   -- plan general anual
 "zonaTraballo" TEXT,   -- plan general anual
 "diasMax" TEXT,   -- plan general anual
 "epocaTraballo" TEXT,   -- plan general anual
 "puntosControl" TEXT,   -- plan general anual
 "tipoCode" CHAR(4),   -- plan general anual
 "conxunto" BOOL,   -- plan general anual
 "urlFicha" TEXT,   -- pescadegalicia.com plan explotación
 "id_plan_explotacion" INTEGER,
 "BMSigremar" TEXT,   -- pescadegalicia.com plan de explotación
 "idzonatra" INTEGER,   -- análisis
 "anualidad" INTEGER DEFAULT 2000,
 "numesp" INTEGER,   -- análisis
 "codeMod" CHAR(1),   -- análisis
 "costa" CHAR(2)   -- análisis
);
```


[Volver a las tablas de la BD muestreos](muestreosTablas.md)


