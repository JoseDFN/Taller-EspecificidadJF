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

![image](https://github.com/user-attachments/assets/cf381259-f150-4711-a34c-07250eabc5bf)

El resultado esperado de esta versión del código es el de mostrar el texto dentro de la etiqueta p en color rojo, esto debido a que el selector id = "parrafo" es el que tiene un mayor valor de especificidad (100 puntos).

![image](https://github.com/user-attachments/assets/e9a5b3c4-7ba5-4b66-b5c1-a81a2cdd4651)

El resultado esperado en esta version del codigo es el de mostrar el texto dento de la etiqueta p en color azul, esto debido a que se le agrego el marcador !important dentro de los estilos definidos para la etiqueta en el archivo CSS (Forzando el uso de este estilo).

# **Parte 3: Ejercicios Prácticos**

Ejercicio 1: Calculando la Especificidad

![image](https://github.com/user-attachments/assets/ec9dae13-e8d4-4af3-8d4d-e7f2a9e6f4fd)

Pregunta: ¿Qué color tendrá el título `<h1>`?

El título `<h1>` tendría color rojo, ya que el estilo aplicado con mayor especificidad es el id `estiloMain` con el elemento `<h1>`, el cual tiene un valor de especificidad de 101, y se le aplica el estilo de color de letra rojo.

Ejercicio 2: Resolviendo Conflictos de Especificidad

