# Juego de la Vida en C++ (Win32, sin librerías)

El [Juego de la Vida de Conway](https://es.wikipedia.org/wiki/Juego_de_la_vida) en C++ usando solo la API de Windows: la ventana, la entrada de teclado y el dibujado (un renderizador por software que pinta píxel a píxel, con texto y números) están hechos a mano, sin SDL ni OpenGL.

> Proyecto personal (septiembre 2024). La base de la ventana Win32 y del renderizador sigue el tutorial [*How to make a game in C++*](https://www.youtube.com/playlist?list=PL7Ej6SUky135IAAR3PFCFyiVwanauRqj3) de Dan Zaidan; la simulación y la interfaz son mías.

<!-- TODO: añade un GIF de la simulación. -->

## Controles

**Configuración**
- `W` / `S`: sube o baja las filas (y luego las columnas) de 100 en 100.
- `Enter`: confirma las filas, luego las columnas y empieza. El tablero inicial es aleatorio.

**Simulación**
- Mantén `F`: congela la simulación.
- `R`: vuelve a la pantalla de configuración.
- `Esc`: salir.

## Ejecutarlo

Windows con Visual Studio: abre `TutorialF.sln` y ejecuta.

## Archivos

| Archivo | Qué hace |
|---|---|
| `windows32_plataform.cpp` | Ventana Win32, bucle principal y entrada |
| `renderer.cpp` | Dibujado por software: rectángulos, texto y números |
| `game.cpp` | Configuración y reglas del Juego de la Vida |

## Mejoras pendientes

- Usar dos tableros (origen y destino). Ahora el tablero se actualiza sobre sí mismo, así que algunas celdas ven el estado nuevo de sus vecinas en vez del anterior.
- Esta versión prioriza que funcione; la versión optimizada en C (tiling, OpenMP, análisis de caché) está en [Game-of-Life-optimization](https://github.com/jaimeamse/Game-of-Life-optimization).
