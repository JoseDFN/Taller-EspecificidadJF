# Taller-EspecificidadJF
Parte 1: Introducción Teórica a la Especificidad

1. ¿Qué es la especificidad?
La especificidad son las reglas que el navegador usa para determinar los estilos a aplicar a una etiqueta, clase o id cuando este tiene varias "reaglas" o estilos sobre este. Siguiendo esto, el navegador decide que estilos aplicar dependiendo del valor de especificidad que tiene determinada regla. Este valor es la suma de diferentes valores otorgados a cada selector usado al definir la regla de estilo, los distintos tipos de selectores con sus respectivos valores y algunas reglas son:
  -Selectores de estilo en línea (atributo style directamente en el HTML): Valor de especificidad de 1000 puntos.
  -Selectores de ID: Valor de especificidad de 100 puntos.
  -Selectores de clase, pseudoclases y atributos: Valor de especificidad de 10 puntos.
  -Selectores de elementos y pseudoelementos: Valor de especificidad de 1 punto.
   **Los selectores universales (\*), combinadores (+,>,~) y las pseudoclases negadas (::not()) no afectan la especificidad.**
   **(!important) marcador que sobre escribe otras reglas sin importar la especificidad.**
