---
name: marca-japi-calvin
description: Sistema de marca y reglas de UI de las webs de JAPI (colectivo de house de Bogotá) y Calvin Parra. Úsala siempre que trabajes en este repo y toques diseño, CSS, copy, tipografía, color, logos, contacto o publicación — aunque el encargo suene menor ("cambia este botón", "añade una sección", "arregla el móvil"). Contiene decisiones ya tomadas y restricciones legales y de privacidad que no se pueden re-derivar leyendo el código, y saltárselas rompe la marca o expone al cliente.
---

# Marca JAPI y Calvin Parra

Este repo aloja **dos marcas distintas** que comparten servidor pero no lenguaje visual. La regla que gobierna todo lo demás: **nunca las mezcles**. Calvin es miembro de JAPI, pero su marca personal no debe leerse como sub-marca del colectivo. Si un cambio hace que se parezcan más, va en dirección contraria a lo acordado.

| | JAPI | Calvin Parra |
|---|---|---|
| Archivos | `index.html`, `assets/css/japi.css` | `calvin/`, `calvin/assets/calvin.css` |
| Carácter | Técnico, futurista, club | Editorial, reposado, lujo contenido |
| Base | Midnight Sky `#16151D` | Tinta `#0C0C0E` |
| Acento | Cyber Yellow `#FDD20E` | Dorado `#C6A462` |
| Texto | `#F4F2EE` / atenuado `#9D9AAB` | Papel `#ECE7DD` / atenuado `#8E8A83` |
| Titulares | Audiowide | Instrument Serif (cursiva para el apellido) |
| Texto corrido | Phenomena | Inter |
| Motivo | Retícula a 45° | Ninguno; el aire es el motivo |

## JAPI

Colectivo de **house de Bogotá**, no un DJ solo y no "música electrónica" en abstracto. Su lema propio es *"Los houseros de Bogotá"* y *"uploading 70% the originals"*. 26 mil seguidores en [@japibogota](https://www.instagram.com/japibogota/).

El sistema viene de un manual real del cliente, no lo inventamos: los dos Pantone, las tres tipografías y la retícula inclinada a 45° salen de `brand/japi-logo/` (fuera del repo, ver abajo). Cuando dudes de un criterio de JAPI, la fuente de verdad es ese PDF, no el gusto propio.

Los logos derivados en PNG están en `assets/img/`: `japi-completo-amarillo` es el principal sobre fondo oscuro, `japi-completo-negro` para sobre amarillo, más las versiones de isotipo (`cara`) y logotipo (`letra`).

## Calvin Parra

Marca personal construida sobre los tres pilares que él mismo declara en su bio: **luxury mindset · AI business · DJ soul**. Son tres frentes que se alimentan, no tres carreras sueltas — el copy debe reflejar eso.

El monograma **CP** y el símbolo del destello ✦ los creamos nosotros y viven en `calvin/assets/brand/` como SVG de trazos puros, sin texto, para que no dependan de ninguna fuente. Hay versión dorada, papel y tinta.

Su manual completo está en `calvin/marca.html`: paleta, tipografía, usos y tono. **Si cambias algo del sistema, actualiza también esa página** — es la referencia que se le pasa a quien diseñe piezas suyas, y desincronizarla la vuelve inútil.

Reglas de uso que ya están escritas ahí y conviene respetar en la web: un solo acento dorado por pantalla; cursiva solo en el apellido o una palabra por bloque; nunca bold para enfatizar (el énfasis va por color); el monograma nunca relleno ni con el trazo engrosado.

## Restricciones que no puedes deducir del código

Estas costaron trabajo averiguarlas y romperlas tiene consecuencias reales.

**La tipografía `digital display tfb` es de uso personal únicamente.** No la vuelvas a incrustar ni la devuelvas a `assets/fonts/`. Vive en `brand/`, fuera del repo. Los bloques que la usaban caen a Audiowide a propósito, y en `assets/css/japi.css` quedó el comentario que explica cómo reponerla si algún día se compra la licencia comercial. Audiowide (OFL) y Phenomena (Fontfabric, libre también para uso comercial) sí se distribuyen sin problema. El detalle está en `FUENTES.md`.

**`brand/` no se versiona.** Contiene los `.ai`, `.eps`, el PDF y el ZIP originales del cliente. El `.gitignore` lo excluye con `/brand/` **anclado a la raíz** — sin la barra inicial también capturaría `calvin/assets/brand/`, que sí debe versionarse. Si tocas ese `.gitignore`, verifica que los SVG de Calvin siguen dentro con `git status`.

**@royandi2 aparece en la bio de JAPI pero su perfil es privado.** Se publica el handle y nada más. No pongas su nombre real en la web: que el colectivo liste su cuenta no autoriza a exponer su identidad en una página indexable. Los demás (Calvin, Pipe Rico, Alexander Sánchez) son perfiles públicos que se presentan como artistas, y ahí sí va el nombre.

**El repo es público** en https://github.com/BTCWFD/japi-web y se publica en https://btcwfd.github.io/japi-web/. Todo lo que commitees queda a la vista, incluido el retrato de Calvin.

## Profundidad 3D con CSS puro

JAPI tuvo una tentación real de meter Spline/Three.js para efectos 3D (referencias externas con modelos `.glb` y texturas comprimidas, varios MB de motor WebGL). Se descartó a propósito: rompe la regla de que la marca es ligera y no depende de nada externo. En su lugar hay dos piezas de profundidad simulada solo con CSS, sin librerías:

- **La intro** (`#intro` en `index.html`) — el logo cae con `perspective`/`rotateX` y dos brillos azul/vinotinto que se desvanecen, una sola vez al cargar.
- **El logo del hero y el ticker** (`· house · bogotá · originals · cabina · pista · japi`) — reaccionan de forma continua al cursor: el logo se inclina hacia el puntero, y en el ticker el cursor actúa como foco de enfoque horizontal — las palabras cerca del cursor quedan nítidas y las lejanas se difuminan, con los mismos dos brillos seleccionados.

El azul y el vinotinto **no son colores de marca** — no los actualices en la tabla de arriba ni los uses en botones o texto. Se justifican solo como "luz de club" sobre el Midnight Sky, en manchas muy difuminadas (`blur` alto) y baja opacidad, nunca como color plano. Si se necesita un tercer sitio para este mismo efecto, reutiliza esos mismos dos tonos — no inventes otro color ahí.

Patrón técnico a seguir si tocas o repites esto: todo cálculo por cursor va con **el mismo `dist` normalizado (0 a 1)** aplicado a escala, blur, opacidad y giro — un bug real de esta implementación fue dejar el `rotateY` sin acotar (crecía con la distancia en píxeles sin tope), mientras las demás propiedades sí estaban entre 0 y 1; una palabra lejana o aún fuera de pantalla en el carrusel podía girar 50°+. El efecto se desactiva por completo (no se degrada, se corta de raíz con un `return` temprano) bajo `prefers-reduced-motion: reduce` y en dispositivos sin `hover:hover`+`pointer:fine` — en esos casos el estado de reposo sin JS ya se ve bien y no debe depender de que el script corra.

**Para verificar esto en el navegador de vista previa:** la herramienta de automatización sí dispara `pointermove` real con `hover`, pero si lees el valor inline (`el.style.transform`) en la misma llamada, puede seguir vacío por leer antes de que corra el primer `requestAnimationFrame` — espera un `setTimeout` corto o dos `requestAnimationFrame` encadenados antes de comprobar el resultado.

## Contacto

Ambas webs contactan por **WhatsApp**, no por correo. El número es de Calvin y atiende las dos marcas. Está en una constante `WHATSAPP` al final de cada `index.html`; cambiarlo es una línea por archivo.

**No publiques direcciones de correo hasta que exista el dominio.** Se retiraron `hola@japi.fm` y `hola@calvinparra.com` justamente porque mandaban a buzones muertos. `japi.com` está en venta por 149.999 USD, descartado; la vía prevista es `japi.fm`, todavía libre.

Los formularios no tienen backend: validan nombre y correo, componen el texto y abren `wa.me`. Si añades campos, súmalos al cuerpo del mensaje o se pierden en silencio.

## Cómo verificar los cambios

Levanta el servidor con la configuración que ya existe en `.claude/launch.json`:

```
preview_start con name "japi-web"   →   http://localhost:5173
```

**El CSS se cachea con fuerza.** Recargar la página no basta: si tocas un `.css`, o bien subes el `?v=N` del `<link>` en el HTML, o compruebas el valor real con `getComputedStyle` antes de dar nada por bueno. Varias veces pareció que un arreglo no funcionaba cuando en realidad se estaba sirviendo la hoja vieja.

Revisa siempre en móvil además de escritorio: las dos webs tienen menú hamburguesa y reordenan columnas por debajo de 900 px.

Para publicar: commit, `git push origin main`, y GitHub Pages reconstruye solo. Tarda un par de minutos; puedes seguirlo con `gh api repos/BTCWFD/japi-web/pages/builds/latest --jq '.status'` y confirmar el resultado con `curl` contra la URL pública antes de decirle al usuario que está listo.

## Cosas que siguen abiertas

No las presentes como resueltas: el dominio no está comprado, y el retrato de Calvin es el de su Instagram recomprimido a 1440 px, pendiente de sustituir por el original.
