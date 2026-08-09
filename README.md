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

## Pendientes

- Dominio sin registrar. Los correos de contacto son provisionales.
- Los formularios no tienen backend; avisan en pantalla al enviar.
- Varias cuentas de la sección "el colectivo" están marcadas como *por confirmar*.
- El retrato de Calvin viene de su Instagram, recomprimido. Reemplazar por el original.

## Archivos no versionados

`brand/` contiene el kit original de JAPI (`.ai`, `.eps`, PDF y el ZIP recibido). Son archivos propietarios del cliente y están excluidos en `.gitignore`.

Las tipografías bajo `assets/fonts/` llegaron dentro de ese kit **sin archivos de licencia**. Antes de publicar el sitio hay que verificar que su licencia permita incrustarlas en web.
