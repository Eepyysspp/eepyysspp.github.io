---
title: "Tutorial: crea tu portafolio y vincúlalo a la orquesta"
date: 2026-09-24 20:50:00 -0300
categories: [Tutoriales]
tags: [portafolio, github, tutorial]
pin: true
---

Cada integrante de la Orquesta de Laptops UC puede tener un blog propio, como este, hecho con el tema [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) y publicado gratis en GitHub Pages. Después se muestra dentro del sitio de la orquesta, en `orquestalaptopsuc.github.io/portafolios/Nombre_Apellido/`.

Todo se hace desde el navegador, sin instalar nada. Toma unos 20 minutos.

> En los ejemplos, reemplaza `USUARIO` por tu usuario de GitHub (en minúsculas) y `NOMBRE APELLIDO` por tu nombre.
{: .prompt-info }

## 1. Crea tu cuenta de GitHub

Si no tienes cuenta, créala en [github.com/signup](https://github.com/signup). Tu nombre de usuario será parte de la dirección de tu blog: `https://USUARIO.github.io`.

Luego pide a quien administra la organización **OrquestaLaptopsUC** en GitHub que te agregue como colaborador, para que puedas subir tu carpeta al repositorio de la orquesta (paso 6).

## 2. Crea tu blog desde la plantilla Chirpy

1. Entra a [github.com/cotes2020/chirpy-starter](https://github.com/cotes2020/chirpy-starter) con tu sesión iniciada.
2. Haz clic en **Use this template → Create a new repository**.
3. En *Repository name* escribe exactamente `USUARIO.github.io`. Ejemplo: `eepyysspp.github.io`.
4. Déjalo **Public** y haz clic en **Create repository**.

## 3. Activa GitHub Pages

1. En tu repositorio nuevo ve a **Settings → Pages**.
2. En *Build and deployment → Source* elige **GitHub Actions**.
3. Ve a la pestaña **Actions**. Cada vez que cambies algo se ejecuta "Build and Deploy". Cuando aparece el tic verde (1 a 3 minutos), tu blog está publicado en `https://USUARIO.github.io`.

> Si la primera ejecución falló o no partió, entra a **Actions**, abre "Build and Deploy" y usa **Run workflow**.
{: .prompt-tip }

## 4. Personaliza `_config.yml`

Abre el archivo `_config.yml` de tu repositorio y haz clic en el lápiz (✏️) para editarlo. Busca cada una de estas líneas y cámbiala. No pegues el bloque completo encima del archivo.

```yaml
# Cambios para el archivo _config.yml de TU blog (repositorio USUARIO.github.io).
# No copies este archivo entero: busca cada línea en tu _config.yml y cámbiala.

lang: es-ES
timezone: America/Santiago

title: NOMBRE APELLIDO
tagline: Bitácora Orquesta de Laptops UC
description: >-
  Registro de ideas, trabajo y varios.

url: "https://USUARIO.github.io"

github:
  username: USUARIO

social:
  name: NOMBRE APELLIDO
  email: tucorreo@uc.cl
  links:
    - https://github.com/USUARIO

# Tu foto: súbela a assets/img/ de tu repositorio, o usa una URL completa
avatar: /assets/img/avatar.jpg

# IMPORTANTE para que el sitio de la orquesta muestre siempre la versión nueva:
pwa:
  enabled: true
  cache:
    enabled: false
```
{: file="_config.yml" }

> **No te saltes `cache: enabled: false`.** Si queda en `true`, tu blog se guarda en caché en el navegador y el sitio de la orquesta sigue mostrando la versión antigua aunque publiques cambios.
{: .prompt-warning }

Cuando termines, haz clic en **Commit changes**. Se vuelve a publicar solo.

## 5. Escribe tu primera entrada

1. En tu repositorio entra a la carpeta `_posts`.
2. **Add file → Create new file**. Nómbralo `AAAA-MM-DD-titulo.md`, por ejemplo `2026-09-24-mi-idea.md`.
3. Pega esta plantilla, cambia el título, la fecha y el texto, y haz **Commit changes**.

```markdown
---
title: "Mi primera entrada"
date: 2026-01-01 12:00:00 -0300
categories: [Ideas]
tags: [orquesta]
---

<!--
PLANTILLA DE ENTRADA (post) para un blog Chirpy.
- Guárdala en la carpeta _posts/ de TU repositorio (USUARIO.github.io).
- El nombre del archivo debe ser AAAA-MM-DD-titulo.md (ej: 2026-09-24-mi-idea.md).
- La fecha de arriba no puede estar en el futuro, o la entrada no aparece.
- Borra las secciones que no uses (y este comentario).
-->

Escribe aquí el texto de tu entrada. Puedes usar **negrita**, *cursiva* y [enlaces](https://orquestalaptopsuc.github.io/).

### Un video de YouTube
<!-- En YouTube: Compartir → Insertar, copia el src del iframe -->
<iframe width="100%" height="315" src="https://www.youtube.com/embed/ID_DEL_VIDEO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Un audio (sample)
<!-- Sube el audio a tu carpeta en el repo de la orquesta: portafolios/Nombre_Apellido/Samples/ -->
<audio controls preload="none" style="width:100%">
  <source src="https://orquestalaptopsuc.github.io/portafolios/Nombre_Apellido/Samples/mi-sample.wav" type="audio/wav">
  Tu navegador no puede reproducir este audio. <a href="https://orquestalaptopsuc.github.io/portafolios/Nombre_Apellido/Samples/mi-sample.wav">Descargar</a>.
</audio>

### Una imagen
<!-- Sube la imagen a assets/img/ de tu repositorio -->
![Descripción de la imagen](/assets/img/mi-imagen.png)

### Conclusión:
Cierra con lo que aprendiste o lo que propones para la orquesta.
```
{: file="_posts/2026-01-01-primera-entrada.md" }

> La `date` de la entrada debe ser la de hoy o una anterior, con `-0300` (hora de Chile). Si queda en el futuro, la entrada no aparece.
{: .prompt-warning }

## 6. Vincula tu blog al sitio de la orquesta

1. Abre el repositorio [OrquestaLaptopsUC.github.io → portafolios](https://github.com/OrquestaLaptopsUC/OrquestaLaptopsUC.github.io/tree/main/portafolios).
2. **Add file → Create new file** y escribe como nombre `Nombre_Apellido/index.html`, con el formato de siempre (ej: `Alan_Brito/index.html`). Al escribir la `/` se crea tu carpeta.
3. Pega esta plantilla y reemplaza `USUARIO` (3 veces) y `NOMBRE APELLIDO` (3 veces).
4. **Commit changes**. En uno o dos minutos tu blog se verá en `https://orquestalaptopsuc.github.io/portafolios/Nombre_Apellido/`.

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- PLANTILLA: reemplaza NOMBRE APELLIDO y USUARIO (tu usuario de GitHub, en minúsculas) -->
  <title>NOMBRE APELLIDO · Portafolio · Orquesta de Laptops UC</title>
  <style>
    html, body { margin: 0; height: 100%; background: #1b1b1e; }
    iframe { display: block; width: 100%; height: 100%; border: 0; }
    .fallback { position: fixed; right: 12px; bottom: 12px; font: 13px/1.2 system-ui, sans-serif;
      background: rgba(0,0,0,.65); color: #fff; padding: 6px 10px; border-radius: 6px; text-decoration: none; }
    .fallback:hover { background: rgba(0,0,0,.85); }
  </style>
</head>
<body>
  <!-- Muestra tu blog https://USUARIO.github.io/ dentro del sitio de la orquesta -->
  <iframe src="https://USUARIO.github.io/" title="Portafolio de NOMBRE APELLIDO"
          allow="autoplay; encrypted-media; picture-in-picture; fullscreen" allowfullscreen></iframe>
  <a class="fallback" href="https://USUARIO.github.io/" target="_blank" rel="noopener">Abrir en pestaña nueva ↗</a>
  <noscript><p><a href="https://USUARIO.github.io/">Ir al portafolio de NOMBRE APELLIDO</a></p></noscript>
</body>
</html>
```
{: file="portafolios/Nombre_Apellido/index.html" }

Como ejemplo, mira [este mismo blog dentro del sitio de la orquesta](https://orquestalaptopsuc.github.io/portafolios/Felipe_Osorio/). Las plantillas también están en la carpeta [`portafolios/_plantilla`](https://github.com/OrquestaLaptopsUC/OrquestaLaptopsUC.github.io/tree/main/portafolios/_plantilla) del repositorio.

> ¿No eres colaborador todavía? Haz un *fork* del repositorio, crea tu archivo ahí y abre un *Pull request*. Alguien del equipo lo aprueba.
{: .prompt-tip }

## 7. (Opcional) Sube samples de audio

1. En el repo de la orquesta, entra a tu carpeta `portafolios/Nombre_Apellido/` y usa **Add file → Upload files**. Si quieres ordenarlos, crea antes una subcarpeta `Samples/`.
2. En una entrada de tu blog, pon un reproductor por archivo:

```html
<audio controls preload="none" style="width:100%">
  <source src="https://orquestalaptopsuc.github.io/portafolios/Nombre_Apellido/Samples/mi-sample.wav" type="audio/wav">
</audio>
```

> GitHub acepta archivos de hasta 25 MB cuando los subes desde la web. Si tus audios son grandes, conviértelos a `.mp3` y cambia `type="audio/wav"` por `type="audio/mpeg"`. Respeta mayúsculas y minúsculas: `Samples` no es lo mismo que `samples`.
{: .prompt-warning }

Puedes ver un ejemplo en la entrada [Samples](https://eepyysspp.github.io/posts/Samples/) de este blog.

## Problemas frecuentes

**Mi blog muestra una página 404.**
Revisa que el repositorio se llame exactamente `USUARIO.github.io`, que en *Settings → Pages* diga **GitHub Actions** y que la última ejecución en *Actions* tenga tic verde.

**La pestaña Actions muestra una ✗ roja.**
Abre la ejecución fallida y lee el paso marcado en rojo. Lo más común es un error de formato en `_config.yml`: una sangría mal puesta o un `:` sin espacio después. Corrige y vuelve a hacer commit.

**Mi entrada nueva no aparece.**
Revisa que el archivo esté dentro de `_posts/`, que el nombre empiece con la fecha (`AAAA-MM-DD-`), que termine en `.md` y que la `date` no esté en el futuro.

**El sitio de la orquesta muestra una versión antigua de mi blog.**
Pon `cache: enabled: false` en `_config.yml` (paso 4). Si la versión antigua sigue en tu navegador, bórrala una vez: en Chrome, candado de la barra de dirección → Configuración del sitio → Borrar datos, en `orquestalaptopsuc.github.io`.

**El audio no suena.**
Abre la dirección del archivo directo en el navegador. Si da 404, revisa la ruta y las mayúsculas. Los cambios del repo de la orquesta tardan uno o dos minutos en publicarse.
