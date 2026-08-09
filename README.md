# JAPI · Calvin Parra

Sitios web estáticos para **JAPI** — colectivo de house de Bogotá — y para **Calvin Parra**, DJ y miembro del colectivo.

| Ruta | Qué es |
|---|---|
| `index.html` | Web de JAPI |
| `calvin/index.html` | Web de Calvin Parra |
| `calvin/marca.html` | Manual de marca de Calvin, v01 |

Sin dependencias ni build. Se sirve como estático.

```bash
python -m http.server 5173
```

## Sistemas de marca

**JAPI** — Cyber Yellow `#FDD20E` sobre Midnight Sky `#16151D`. Tipografías Audiowide, Phenomena y digital display tfb. Logo y retícula de construcción a 45° vienen del manual original del cliente.

**Calvin Parra** — Tinta `#0C0C0E`, dorado `#C6A462`, papel `#ECE7DD`. Instrument Serif + Inter, vía Google Fonts. Monograma CP y símbolo del destello creados para este proyecto; los SVG están en `calvin/assets/brand/`.

Los dos sistemas son deliberadamente distintos: Calvin no debe leerse como sub-marca de JAPI.

## Formularios

No hay backend. Al enviar, ambos formularios componen el mensaje y abren el cliente de correo del visitante por `mailto:`. La dirección de destino está en una sola constante `DESTINO` al final de cada `index.html`; cambiarla es una línea.

## Pendientes

- Dominio sin registrar. Los correos de destino (`hola@japi.fm`, `hola@calvinparra.com`) son provisionales.
- El retrato de Calvin viene de su Instagram, recomprimido a 1440 px. Reemplazar por el original.
- `@royandi2` aparece en la info de JAPI pero su perfil es privado; queda solo el handle, sin datos.

## Archivos no versionados

`brand/` contiene el kit original de JAPI (`.ai`, `.eps`, PDF y el ZIP recibido) más la tipografía de uso personal. Son archivos propietarios o no redistribuibles, excluidos en `.gitignore`.

Las licencias de las tres tipografías están verificadas y documentadas en [FUENTES.md](FUENTES.md).
