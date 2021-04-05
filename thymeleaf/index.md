# Thymeleaf

Thymeleaf es un moderno motor de plantillas Java del lado del servidor para entornos web e independientes.
La documentación oficial la podemos encontrar en https://www.thymeleaf.org.

## Empezando a usarlo

Para usar thymeleaf, debemos añadirle el atributo `xmlns` a las páginas html que tengamos, para que no den errores cuando usemos los "nuevos atributos" de thymeleaf. 

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
  <head>
    <title>Hola Mundo</title>
    <meta charset="UTF-8" />
  </head>

  <body>
    <p th:text="${saludo}"></p>
  </body>
</html>
```
Ten en cuenta que la página así, no pasaría ningún validador de HTML5. Si quieres tener un documento HTML5 validado, deberás hacer lo siguiente:

```html
<p data-th-text="${saludo}"></p>
```
La diferencia es que eso tendríamos que hacerlo en todos los atributos de thymeleaf `th:*`.

## Mostrando valores recibidos en el modelo

Cualquier variable enviada en el objeto `model`, la podemos mostrar en una vista cd thymeleaf, de la siguiente forma:

```java
//Desde el controlador java...
String usuario="salva@formador.es";
model.addAttribute("nombre", usuario);
```

```html
<!-- Desde HTML -->
<p th:text="${nombre}">El contenido será eliminado</p>
```

El texto de `El contenido del párrafo será eliminado`, será sustituido en tiempo de compilación por el contenido de la variable `nombre`, por lo que la plantilla una vez compilada, quedará de la siguiente forma:

```html
<p>salva@formador.es</p>
```

## Condicionales IF

Documentar como se hace un if

## Bucles FOR

Documentar como se hace un forEach