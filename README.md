# Taller-EspecificidadJF
Parte 1: Introducción Teórica a la Especificidad

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

Parte 2: Ejemplos Prácticos

![image](https://github.com/user-attachments/assets/e115e7f5-f2fc-4631-93cf-533ffc39e8a3)

El resultado esperado de esta versión del código es el de mostrar el texto dentro de la etiqueta p en color rojo, debido a que el selector id = "parrafo" es el que tiene un mayor valor de especificidad (100 puntos).
