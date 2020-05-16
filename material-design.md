# DOCUMENTACIÓ MATERIAL DESIGN

Material Design és un framework de CSS de Google que permet implementar el disseny de Google a les pàgines d'HTML. La documentació està a aquesta [web](https://materializecss.com/getting-started.html).

## Utilitzar Material Design en un document HTML

Només hem d'afegir els links que ens proporciona la documentació.

Aquests links són 3:
1. Dins de `<head></head>` i en aquest ordre:
   1. Les Google Icon Font: `<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">`
   2. La llibreria de CSS: `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">`
2. Dins de `<body></body>`:
   1. La llibreria de JS: `<script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>`

Per tant, quedaria una cosa així:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!--Import Google Icon Font-->
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">

    <!-- Compiled and minified CSS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">

    <title>Document</title>
</head>
<body>
    <!-- Compiled and minified JavaScript -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>    

    <div class="container">
        <h1 class="blue-text">Hola món!</h1>
    </div>
</body>
</html>
```

A partir d'aquí, ja es pot començar a utilitzar el framework.

## Ús

Material Design es basa en classes de CSS, per tant, sempre s'haurà d'utilitzar en la propietat class de l'objecte HTML.

Per exemple, si volem canviar el color d'un div, n'hi ha prou obrint la [documentació de colors de Material Design](https://materializecss.com/color.html), escollir el color i afegir-lo a class: 
```html
<h1 class="green-text text-accent-2">Hola món!</h1>
```