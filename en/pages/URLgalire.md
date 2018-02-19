# Procesos en Google url shortener

## Años procesados

### Captura de datos

|Años|01|02|03|04|05|06|07|08|09|10|11|12|
|----|--|--|--|--|--|--|--|--|--|--|--|--|
|5521||||||||||||
|2017|4675|4728|4759|4791|4830|4862|4905|4932|4981|5036|5148|5237|
|2016|3341|3398|3459|3516|3563|3649|4088|4137|4186|4237|4323|4383|
|2015|1897|1995|2132|2228|2300|2380|2685|2732|2790|2879|2982|3060|
|2014|268|365|472|575|664|803|913|1050|1219|1355|1480|1581|


## BD URLCortas.sqlite

### Tablas de galirema

```sql
CREATE TABLE "galire2014" ("ideURL" INTEGER PRIMARY KEY ,"LongURL" TEXT,"Created" NUMERIC,"ShortURL" TEXT,"Detalles" TEXT,"Clicks" NUMERIC)
```

|Tabla galire|nº registros|IDEinicio|IDEfin|
|:-----------|-----------:|--------:|-----:|
|galire2018 (1)| 284|5238|5521|
|__galire2017__ (12)| 854|4384|5237|
|__galire2016__ (12)|1323|3061|4383|
|__galire2015__ (12)|1479|1582|3060|
|__galire2014__ (12)|1581|1|1581|





