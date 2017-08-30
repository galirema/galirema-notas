# Enlaces publicados por el proyecto Galirema


## Google url shortener

* Los enlaces que de alguna manera han sido utilizados por el proyecto son acortados.  
Los enlaces acortados son mas sencillos de manejar para publicarlos en las redes sociales.  
El acortador empeado es el de google <https://goo.gl> que ademas permite un seguimiento estadístico de su actividad.

* Empecé a utilizar _"Google url shortener"_ em noviembre de 2011 y lo sigo utilizando en la actualidad.

* Existe una API para este servicio: [Guia URL Shortener][]

* En la [Referencia][] de la API se pueden hacer consultas a la base de datos de url acortadas. Obteniendo información que puede ser tratada. (Nota: Mas adelante debo hacer un pequeño howto; en "_/home/lanchalisa/Dropbox/galirema/galigooA/probas.txt_" hay una utilización exitosa de 2 consiltas el comando __Url:list__  
```
GET https://www.googleapis.com/urlshortener/v1/url/history?projection=FULL&fields=items%2CitemsPerPage%2Ckind%2CnextPageToken%2CtotalItems&key={YOUR_API_KEY} 
GET https://www.googleapis.com/urlshortener/v1/url/history?projection=FULL&start-token=2016-03-29T13%3A17%3A34.879%2B00%3A00&fields=items%2CitemsPerPage%2Ckind%2CnextPageToken%2CtotalItems&key={YOUR_API_KEY}
```

* También hay un explorador alternativo para realizar estas consultas a la base de datos del acortador:
	+ [insert](http://code.google.com/apis/explorer/#_s=urlshortener&_v=v1&_m=url.insert)
	+ [get](http://developers.google.com/apis-explorer/#p/urlshortener/v1/urlshortener.url.get)
	+ [list](http://developers.google.com/apis-explorer/#p/urlshortener/v1/urlshortener.url.list)

* Propiedades de una URL [Referencia](referenciaVisionGeneral.md)

* [Google URL Shortener Documentación](https://developers.google.com/url-shortener/)

* Listado correcto:
```
GET https://www.googleapis.com/urlshortener/v1/url/history?projection=ANALYTICS_CLICKS&fields=items(analytics%2FallTime%2Ccreated%2Cid%2Ckind%2ClongUrl%2Cstatus)&key={YOUR_API_KEY}
```
	* _projection_=__ANALYTICS_CLICKS__
	* _fields_=items(__analytics%2FallTime__%2C __created__%2C __id__%2C __kind__%2C __longUrl__%2C __status__)


* Como ejemplo puedes utilizar la url acortada para llamar a _Galirema-Notas_ (en __Drive__)  <https://goo.gl/S6CWCA> en los enlaces anteriores, si quieres hacer la comprobación web hay que añadirle el signo mas <https://goo.gl/S6CWCA+>  

Esta url de esta wiki funcionaba de el __Drive__ de _Google_, ahora no está permitido por lo que da error pero la analítica de __GShortener__ si funciona.

+ Resultado del dia 2017/06/10: De Get para una URL acortada `https://goo.gl/S6CWCA`

``` bash
Request:

GET https://www.googleapis.com/urlshortener/v1/url?shortUrl=https%3A%2F%2Fgoo.gl%2FS6CWCA&projection=FULL&fields=analytics%2FallTime&key={YOUR_API_KEY}

Response: 

200
 
- Hide headers -
 
cache-control:  public, max-age=0, must-revalidate, no-transform
content-encoding:  gzip
content-length:  247
content-type:  application/json; charset=UTF-8
date:  Sat, 10 Jun 2017 15:40:56 GMT
etag:  "qQqhpr1RL6vGc3-0yacNoUjh_Uc/a2UU8uKdU1gm1ahcgHNbugmWmgQ"
expires:  Sat, 10 Jun 2017 15:40:56 GMT
server:  GSE
vary:  Origin, X-Origin
 
{
 "analytics": {
  "allTime": {
   "shortUrlClicks": "326",
   "longUrlClicks": "326",
   "referrers": [
    {
     "count": "325",
     "id": "unknown"
    },
    {
     "count": "1",
     "id": "mail.google.com"
    }
   ],
   "countries": [
    {
     "count": "326",
     "id": "ES"
    }
   ],
   "browsers": [
    {
     "count": "320",
     "id": "Chrome"
    },
    {
     "count": "5",
     "id": "Safari"
    },
    {
     "count": "1",
     "id": "Firefox"
    }
   ],
   "platforms": [
    {
     "count": "297",
     "id": "X11"
    },
    {
     "count": "24",
     "id": "Android"
    },
    {
     "count": "5",
     "id": "Macintosh"
    }
   ]
  }
 }
}
 
```
## Galirema

Los procesos de enlaces acortados por galirema son los [siguientes](URLgalire.md)



 [Guia URL Shortener]: https://developers.google.com/url-shortener/
 [getting_started]: https://developers.google.com/url-shortener/v1/getting_started
 [performance]: https://developers.google.com/url-shortener/v1/performance
 [Referencia]: https://developers.google.com/url-shortener/v1/



