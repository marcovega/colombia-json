# Ciudades y departamentos de Colombia en json

Lista de departamentos con sus respectivas ciudades en json.

La lista ha sido extraída de la página de Wikipedia [Anexo:Municipios de Colombia](https://es.wikipedia.org/wiki/Anexo:Municipios_de_Colombia)
el 1 de Febrero del 2016.

Incluyen 31 departamentos y 1124 municipios / pueblos / ciudades.

## Utilización JavaScript

Método gracias a Rich en Rich's Blog:

loadJSON es una función que permite extraer por medio de XMLHttpRequest nuestro archivo json.

``` js
function loadJSON(callback) {   

    var xobj = new XMLHttpRequest();
        xobj.overrideMimeType("application/json");
        xobj.open('GET', 'colombia-json.json', true); // Reemplaza colombia-json.json con el nombre que le hayas puesto
        xobj.onreadystatechange = function () {
          if (xobj.readyState == 4 && xobj.status == "200") {
            callback(xobj.responseText);
          }
    };
    xobj.send(null);  
}
```

Através de la función anónima, cargamos el JSON de la siguiente forma:

```js
function init() {
 loadJSON(function(response) {
  // Parse JSON string into object
    var JSONFinal = JSON.parse(response);
 });
}
```
La variable JSONFinal contiene todos nuestros departamentos y ciudades.
