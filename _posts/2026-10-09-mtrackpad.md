---
title: "MTrackpad: un instrumento para tocar con el trackpad"
date: 2026-10-09 16:30:00 -0300
categories: [Instrumentos]
tags: [mtrackpad, instrumento, web audio, sintesis, granular, luces]
---

**MTrackpad** (*musical trackpad*) es un instrumento que se toca con el trackpad, el mouse o una pantalla táctil, directamente en el navegador. Un recuadro XY, un eje Z y los gestos que se hacen sobre él controlan un sintetizador, cuatro ranuras de muestras, una cadena de efectos y luces para proyectar. Lo central es que **todo lo que controla cada eje se puede reasignar**: el mismo gesto puede abrir un filtro, tocar una melodía, mover una nube de granos o cambiar el color de la luz.

Nació del controlador de "ambiente" de la [propuesta de obra]({% post_url 2026-09-25-propuesta-obra-genesis %}), que me pareció lo bastante interesante como para sacarlo de la obra y convertirlo en un instrumento independiente, que se puede usar en cualquier pieza.

## Pruébalo

Presiona **Encender** (o `Espacio`) y arrastra en el recuadro. Arriba a la derecha hay presets para empezar. Se escucha mejor con audífonos.

<iframe src="https://eepyysspp.github.io/MTrackpad/" title="MTrackpad" width="100%" height="820" style="border:1px solid rgba(127,127,127,.3);border-radius:10px" allow="autoplay; fullscreen"></iframe>

**[Abrir MTrackpad en una pestaña nueva →](https://eepyysspp.github.io/MTrackpad/)** · [Código en GitHub](https://github.com/Eepyysspp/MTrackpad)

## Cómo se toca

| Tecla | Acción |
|---|---|
| `Espacio` | encender / apagar (en modo «al tocar», mantener para que suene) |
| `←` `→` / `↑` `↓` | mover X / Y (`Shift` = pasos finos) |
| `Q` `E` o rueda del mouse sobre el recuadro | eje Z |
| `1`–`4` | disparar las muestras |
| `F` | destello (sonido y luz) |
| `V` | luces a pantalla completa, para proyectar |
| `G` | grabar lo que suena |

## Fuentes de control

No solo importa *dónde* está el dedo, también *cómo* se mueve:

| Fuente | Qué mide |
|---|---|
| **X**, **Y** | posición en el recuadro |
| **Z** | deslizador auxiliar (rueda del mouse o `Q`/`E`) |
| **R** | distancia al centro: 0 en el centro, 1 en las esquinas |
| **A** | ángulo alrededor del centro: girar el dedo recorre un círculo |
| **V** | velocidad del gesto: sube al moverse rápido y vuelve sola a 0 al quedarse quieto |
| **P** | presión del lápiz o del toque |

Cada **asignación** une una fuente con un parámetro y define su mínimo, su máximo y una curva: lineal, x², √x, S, exponencial (la mejor para frecuencias, porque cada tramo del eje es el mismo intervalo musical) o en 5 escalones. Si varias fuentes controlan el mismo parámetro, se promedian, y todo lo que no está asignado queda en un valor fijo.

## El sonido

- **Osciladores:** cuatro, cada uno con su forma de onda (sierra, cuadrada, triángulo o seno) y su intervalo en semitonos, más ruido. Se pueden desafinar en abanico y abrir en estéreo.
- **Altura:** un parámetro de ±24 semitonos que se puede ajustar a una escala (mayor, menor, pentatónicas, blues, dórica). Asignado a un eje, el instrumento se toca como un theremin; el *glide* decide qué tan ligadas suenan las notas.
- **Puerta:** suena encendido/apagado, o solo mientras se toca el recuadro, con ataque y suelta.
- **Muestras:** cuatro ranuras para cargar audios propios o generar ejemplos (pad, campana, viento, bombo, vocal). Cada ranura puede sonar como:
  - **loop**, que sigue la altura;
  - **nube granular**: pedacitos de la grabación de 10 a 600 ms, cuya posición, tamaño, densidad y dispersión se pueden asignar a los ejes;
  - **disparo**: suena entera con una tecla o al tocar el recuadro.
- **Efectos, en orden:** filtro (con barrido automático), distorsión `tanh` en paralelo, trémolo, chorus estéreo, eco sincronizado al tempo, reverb y compresor.

## Las luces

El fondo de la página es un sistema de luces pensado para proyectarse durante una presentación, con cuatro dibujos: manchas de color, anillos que pulsan con los golpes, el espectro del sonido y una cortina de color plano. El color, la saturación, la intensidad, la velocidad, el tamaño y la reacción al sonido son parámetros como cualquier otro, así que también se pueden poner en los ejes. Por ejemplo, el ángulo **A** asignado al color da una rueda cromática al girar alrededor del centro.

## Presets

Vienen nueve incluidos: *Drone filtrado*, *Theremin*, *Filtro resonante*, *Respiración*, *Muro de distorsión*, *Nube granular*, *Coro y eco*, *Oleaje* y *Gesto*. Se pueden guardar presets propios y pasar la configuración completa a otro computador como texto o archivo `.json`, útil para que varias laptops de la orquesta toquen con la misma configuración.

## Declaración de uso de IA

Claude fue utilizado para los siguientes propósitos:

- **Separar el controlador de ambiente de la obra y ampliar sus opciones.**

  > "Del proyecto y pagina del cover de genesis quiero que me generes una nueva pagina por si sola que contenga solo el controlador de "🌊 Ambiente · Teclados bajos permanentes", con mas opciones de customizar que parametros controlan los distintos ejes en el panel."

  > "Quiero que quede como un repositorio aparte"

- **Convertirlo en un instrumento propio.**

  > "Elimina todo lo que lo relacione a la obra Genesis, que sea su propio instrumento llamado MTrackpad (Musical trackpad). Que permita modificar el audio, cargar samples controlar la luz, efectos. Etc"

- **Escribir este post.**

  > "Quiero que me generes un post de este instrumento en mi pagina"
