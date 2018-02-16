# Gráficos para el Pexma2017

## Tipo de plan por zona de costa

### Consulta SQL

```sql
SELECT "costa", "tipoCode", COUNT("idPlanAnual") FROM "pexma2017" GROUP BY "tipoCode", "costa";
```

## AAUT Autorizaciones

* __Gráfico M07-06 AAUUT por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|AAUT|23|
|CF|AAUT|9|
|CL|AAUT|4|
|CM|AAUT|2|
|MN|AAUT|4|
|PO|AAUT|1|
|VI|AAUT|2|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'AAUT', { role: 'style' }, { role: 'annotation' }],
         ['CL', 4, '#0C20D5', '4'],
         ['CF', 9, '#0C20D5', '9'],
         ['CM', 2, '#0C20D5', '2'],
         ['MN', 4, '#0C20D5', '4'],
         ['AR', 23, '#0C20D5', '23'],
         ['PO', 1, '#0C20D5', '1'],
         ['VI', 2, '#0C20D5', '2'],
         ['GL', 0, '#0C20D5', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Autorizaciones por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales AAUT (45)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-06 AAUTxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## BESP Libre Marisqueo

* __Gráfico M07-07 BESP por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|BESP|9|
|CF|BESP|7|
|CL|BESP|7|
|CM|BESP|6|
|MN|BESP|1|
|PO|BESP|5|
|VI|BESP|13|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'BESP', { role: 'style' }, { role: 'annotation' }],
         ['CL', 7, '#EC0B29', '7'],
         ['CF', 7, '#EC0B29', '7'],
         ['CM', 6, '#EC0B29', '6'],
         ['MN', 1, '#EC0B29', '1'],
         ['AR', 9, '#EC0B29', '9'],
         ['PO', 5, '#EC0B29', '5'],
         ['VI', 13, '#EC0B29', '13'],
         ['GL', 0, '#EC0B29', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Específicos por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales BESP (48)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-07 BESPxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

##DPER Percebe


* __Gráfico M07-08 DPER por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|DPER|3|
|CF|DPER|3|
|CL|DPER|10|
|CM|DPER|10|
|MN|DPER|2|
|PO|DPER|2|
|VI|DPER|5|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'DPER', { role: 'style' }, { role: 'annotation' }],
         ['CL', 10, '#EFA505', '10'],
         ['CF', 3, '#EFA505', '3'],
         ['CM', 10, '#EFA505', '10'],
         ['MN', 2, '#EFA505', '2'],
         ['AR', 3, '#EFA505', '3'],
         ['PO', 2, '#EFA505', '2'],
         ['VI', 5, '#EFA505', '5'],
         ['GL', 0, '#EFA505', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Percebe por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales DPER (35)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-08 DPERxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## FEQD Equinodermos

* __Gráfico M07-09 FEQD por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|FEQD|2|
|CF|FEQD|2|
|CL|FEQD|4|
|CM|FEQD|3|
|PO|FEQD|2|
|VI|FEQD|5|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'FEQD', { role: 'style' }, { role: 'annotation' }],
         ['CL', 4, '#07A421', '4'],
         ['CF', 2, '#07A421', '2'],
         ['CM', 3, '#07A421', '3'],
         ['MN', 0, '#07A421', '0'],
         ['AR', 2, '#07A421', '2'],
         ['PO', 2, '#07A421', '2'],
         ['VI', 5, '#07A421', '5'],
         ['GL', 0, '#07A421', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Equinodermos por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales FEQD (18)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-09 FEQDxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## GSOL Solénidos

* __Gráfico M07-10 GSOL por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|GSOL|10|
|CM|GSOL|3|
|MN|GSOL|3|
|PO|GSOL|2|
|VI|GSOL|6|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'GSOL', { role: 'style' }, { role: 'annotation' }],
         ['CL', 0, '#BC04A1', '0'],
         ['CF', 0, '#BC04A1', '0'],
         ['CM', 3, '#BC04A1', '3'],
         ['MN', 3, '#BC04A1', '3'],
         ['AR', 10, '#BC04A1', '10'],
         ['PO', 2, '#BC04A1', '2'],
         ['VI', 6, '#BC04A1', '6'],
         ['GL', 0, '#BC04A1', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Solénidos por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales GSOL (24)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-10 GSOLxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## HPEN Peneiras

* __Gráfico M07-11 HPEN por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|HPEN|1|
|"CM|HPEN|1|
|"PO|HPEN|2|
|"VI|HPEN|1|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'HPEN', { role: 'style' }, { role: 'annotation' }],
         ['CL', 0, '#07A6CE', '0'],
         ['CF', 0, '#07A6CE', '0'],
         ['CM', 1, '#07A6CE', '1'],
         ['MN', 0, '#07A6CE', '0'],
         ['AR', 1, '#07A6CE', '1'],
         ['PO', 2, '#07A6CE', '2'],
         ['VI', 1, '#07A6CE', '1'],
         ['GL', 0, '#07A6CE', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Oreja de mar por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales HPEN (5)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-11 HPENxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## IALG Algas

* __Gráfico M07-12 IALG por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|IALG|2|
|CF|IALG|1|
|CM|IALG|4|
|GL|IALG|4|
|MN|IALG|2|
|PO|IALG|2|
|VI|IALG|5|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'IALG', { role: 'style' }, { role: 'annotation' }],
         ['CL', 0, '#C10586', '0'],
         ['CF', 1, '#C10586', '1'],
         ['CM', 4, '#C10586', '4'],
         ['MN', 2, '#C10586', '2'],
         ['AR', 2, '#C10586', '2'],
         ['PO', 2, '#C10586', '2'],
         ['VI', 5, '#C10586', '5'],
         ['GL', 4, '#C10586', '4']
      ]);


      var options = {
        title: 'Plan General 2017. Algas por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales IALG (20)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-12 IALGxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## JANE Anémonas

* __Gráfico M07-13 JANE por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|JANE|2|
|CF|JANE|2|
|PO|JANE|1|
|VI|JANE|4|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'JANE', { role: 'style' }, { role: 'annotation' }],
         ['CL', 0, '#76BA09', '0'],
         ['CF', 2, '#76BA09', '2'],
         ['CM', 0, '#76BA09', '0'],
         ['MN', 0, '#76BA09', '0'],
         ['AR', 2, '#76BA09', '2'],
         ['PO', 1, '#76BA09', '1'],
         ['VI', 4, '#76BA09', '4'],
         ['GL', 0, '#76BA09', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Anemonas por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales JANE (9)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-13 JANExzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----



      chart.draw(data, options);
    }
</script>
```
----

## KPOL Poliquetos


* __Gráfico M07-14 KPOL por zona de costa__  

|zona|tipo plan|nº de planes|
|----|---------|-----------:|
|AR|KPOL|3|
|CF|KPOL|4|
|CL|KPOL|1|
|CM|KPOL|5|
|MN|KPOL|3|
|PO|KPOL|2|
|VI|KPOL|4|

----

```javascript
  <script type="text/javascript">

    google.load('visualization', '1', {packages: ['corechart', 'bar']});
    google.setOnLoadCallback(drawBasic);

    function drawBasic() {

      var data = google.visualization.arrayToDataTable([
         ['Zona de costa', 'KPOL', { role: 'style' }, { role: 'annotation' }],
         ['CL', 1, '#C10606', '1'],
         ['CF', 4, '#C10606', '4'],
         ['CM', 5, '#C10606', '5'],
         ['MN', 3, '#C10606', '3'],
         ['AR', 3, '#C10606', '3'],
         ['PO', 2, '#C10606', '2'],
         ['VI', 4, '#C10606', '4'],
         ['GL', 0, '#C10606', '0']
      ]);


      var options = {
        title: 'Plan General 2017. Poliquetos por zona de costa.',
        legend: 'none',
        width: 650,
        height: 450,
        hAxis: {
          title: 'Zona de costa',
        },
        vAxis: {
          title: 'Num. planes anuales KPOL (22)',
            minValue: 0
        }
      };

      var chart = new google.visualization.ColumnChart(
        document.getElementById('chart_div'));

// lineas png  (M07-14 KPOLxzcosta2017 ESpng.html)
      // Wait for the chart to finish drawing before calling the getImageURI() method. -- PNG -
//        google.visualization.events.addListener(chart, 'ready', function () {
//        chart_div.innerHTML = '<img src="' + chart.getImageURI() + '">';
//        console.log(chart_div.innerHTML);
//      });
//  -----


      chart.draw(data, options);
    }
</script>
```
----

## Fichero HTML

* Cabecera y cuerpo del fichero html donde incluyo el script en javascript del gráfico.

----

```html
<html>

<!---- (M07-nn TTTTxzcosta2017 ES.html)  ---->
   <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />

<head>

  <script type="text/javascript" src="https://www.google.com/jsapi"></script>

<!---- Script   ---->

</head>

<body>

  <div id="chart_div"><div>

</body>

</html>
```
----


