# Licencias de las tipografías

Las tres tipografías del manual de JAPI llegaron dentro del ZIP del cliente **sin archivos de licencia**. Esto es lo que se verificó antes de publicar el sitio.

| Tipografía | Autor | Licencia | ¿Se distribuye en este repo? |
|---|---|---|---|
| Audiowide | Astigmatic (Google Fonts) | SIL Open Font License 1.1 | Sí |
| Phenomena | Fontfabric | Gratuita para uso personal y comercial | Sí |
| digital display tfb | Kaiser Zhar Khan, 2012 | **Solo uso personal** | **No** |

## digital display tfb

Es la única con problema. Su licencia cubre uso personal; el uso comercial requiere comprarla al autor. Como este es el sitio de una marca, el archivo:

- se sacó de `assets/fonts/` y vive en `brand/`, que está fuera del repositorio;
- ya no se incrusta por `@font-face`;
- los bloques que la usaban (el ticker del hero y el espécimen tipográfico) caen a **Audiowide**, la tipografía principal del manual.

Si se compra la licencia comercial, para reponerla basta con devolver el `.ttf` a `assets/fonts/` y restaurar el bloque `@font-face` en `assets/css/japi.css`, donde quedó el comentario indicándolo.

## Calvin Parra

Instrument Serif e Inter se cargan desde Google Fonts, ambas bajo SIL Open Font License. No se distribuyen archivos en este repo.
