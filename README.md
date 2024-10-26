# Taller-EspecificidadJF
# **Parte 1: Introducción Teórica a la Especificidad**

¿Qué es la especificidad?

La especificidad son las reglas que el navegador usa para determinar los estilos a aplicar a un elemento, dependiendo de la etiqueta, clase o id, cuando este tiene varias "reglas" o estilos sobre este. Siguiendo esto, el navegador decide que estilos aplicar dependiendo del valor de especificidad que tiene determinada regla. Este valor es la suma de diferentes valores otorgados a cada selector usado al definir la regla de estilo, los distintos tipos de selectores con sus respectivos valores y algunas reglas son:

- **Selectores de estilo en línea** (atributo `style` directamente en el HTML): Valor de especificidad de **1000 puntos**.
- **Selectores de ID**: Valor de especificidad de **100 puntos**.
- **Selectores de clase, pseudoclases y atributos**: Valor de especificidad de **10 puntos**.
- **Selectores de elementos y pseudoelementos**: Valor de especificidad de **1 punto**.

| Selector                           | Tipo                | Especificidad |
|------------------------------------|---------------------|----------------|
| style="color: red;"               | Estilo en línea     | 1000           |
| #miID                              | ID                  | 100            |
| .miClase, :hover, [type]          | Clase/Atributo      | 10             |
| div, p, ::before                   | Elemento            | 1              |
| *, :not(.miClase), >              | Universal/Negado    | 0              |


Los selectores universales (`*`), combinadores (`+`, `>`, `~`) y las pseudoclases negadas (`:not()`) **no afectan la especificidad**.

El marcador `!important` sobrescribe otras reglas sin importar la especificidad.

> **Importante:** [Descargar presentación](https://github.com/JoseDFN/Taller-EspecificidadJF/raw/refs/heads/main/Explicacion%20Especificidad%20CSS%20y%20HTML.pptx)

# **Parte 2: Ejemplos Prácticos**

Demuestra cómo los diferentes selectores afectan la especificidad.

![image](https://github.com/user-attachments/assets/cf381259-f150-4711-a34c-07250eabc5bf)

El resultado esperado de esta versión del código es el de mostrar el texto dentro de la etiqueta `<p>` en color rojo, esto debido a que el selector `id = "parrafo"` es el que tiene un mayor valor de especificidad (100 puntos).

![image](https://github.com/user-attachments/assets/e9a5b3c4-7ba5-4b66-b5c1-a81a2cdd4651)

El resultado esperado en esta version del codigo es el de mostrar el texto dento de la etiqueta `<p>` en color azul, esto debido a que se le agrego el marcador `!important` dentro de los estilos definidos para la etiqueta en el archivo CSS (Forzando el uso de este estilo).

# **Parte 3: Ejercicios Prácticos**

### Ejercicio 1: Calculando la Especificidad

Dado el siguiente código, pide a los participantes que calculen la especificidad y determinen qué
estilos se aplicarán:

```html
<div id="main" class="content">
    <h1>Título</h1>
<p>Este es un párrafo.</p>
</div>
```
```css
/* Estilo por etiqueta */
h1 {
    color: blue;
}
/* Estilo por clase */
.content h1 {
    color: green;
}
/* Estilo por ID */
#main h1 {
    color: red;
}
```

![image](https://github.com/user-attachments/assets/ec9dae13-e8d4-4af3-8d4d-e7f2a9e6f4fd)

Pregunta: ¿Qué color tendrá el título `<h1>`?

El título `<h1>` tendría color rojo, ya que el estilo aplicado con mayor especificidad es el id `estiloMain` con el elemento `<h1>`, el cual tiene un valor de especificidad de 101, y se le aplica el estilo de color de letra rojo.

### Ejercicio 2: Resolviendo Conflictos de Especificidad

Modifica el siguiente código para que el párrafo tenga color amarillo, sin usar !important .

```html
<div id="box" class="content">
    <p class="text">Texto aquí</p>
</div>
```
```css
#box p {
  color: blue;
}
.content .text {
  color: green;
}
```

La solucion que propuse fue la de crear un selector con un mayor nivel o valor de especificidad (`1 (Body) + 1 (div) + 100 (id) + 10 (class) + 1 (p) + 10 (class) = 123 Puntos de Especificidad`) como lo seria:

```css
body div#caja.contenido p.texto{
    color: yellow;
}
```

![image](https://github.com/user-attachments/assets/0042c76a-bbdd-4952-938b-24bcae4c9fdb)

# **Parte 4: Desafío Final**

### Desafío: Diseñando una Página Completa con Estilos Conflictivos

Dales a los participantes un archivo HTML con múltiples elementos y clases, y pídeles que
agreguen estilos CSS para lograr un diseño específico. Deberán aplicar todo lo aprendido sobre
especificidad para resolver los conflictos y obtener el resultado correcto.

```html
<div class="header" id="top">
  <h1>Bienvenido</h1>
  <p id="intro">Este es el sitio web.</p>
</div>
<div class="content">
  <h2>Contenido principal</h2>
  <p class="highlight">Texto destacado</p>
</div>
<footer id="footer">
  <p>Pie de página</p>
</footer>
```
Desafío CSS:
- El `<h1>` en el `.header` debe ser de color blanco.
- El texto del `<p>` en `.content` debe ser rojo.
- El texto del `<footer>` debe ser gris.

Pistas:
- Usar selectores combinados (clases y etiquetas).
- Resolver conflictos de estilo con la especificidad correcta.

Para poner el `<h1>` en el `.header` de color blanco use el siguiente codigo de css:

```css
body div#top.header h1{
    color: white;
}
```

Para poner el texto del `<p>` en `.content` en color rojo use el siguiente codigo de css:

```css
body div.content p.highlight{
    color: red;
}
```

Para poner el texto del `<footer>` en color gris use el siguiente codigo de css:

```css
footer#footer{
    color: grey;
}
```

Adicional a esto, puse el color del fondo en `#caf3ff` para que el texto en blanco pueda apreciarse. Esto lo hice con el siguiente codigo de css:

```css
body {
    background-color: #caf3ff;
}
```
![image](https://github.com/user-attachments/assets/a8b29204-0927-4ea9-9208-7d6847442635)
