# luis-abogado

Web personal de Luis de Francisco Morales, publicada en GitHub Pages.

## Cómo añadir un nuevo artículo

Todo el contenido de la sección "Artículos" se lee desde [`assets/posts.json`](assets/posts.json).
**No hay que tocar `index.html` para publicar algo nuevo.**

### Añadir una reflexión de LinkedIn

Abre `assets/posts.json` y añade un nuevo objeto **al principio** de la lista `"posts"` (el más reciente siempre va primero):

```json
{
  "date": "5 sep 2026",
  "title": "Título del post",
  "excerpt": "Resumen breve, 2-3 frases.",
  "tags": ["Etiqueta 1", "Etiqueta 2"],
  "url": "https://www.linkedin.com/in/luis-de-francisco-morales-828704b8/recent-activity/all/"
}
```

Si tienes el enlace directo al post de LinkedIn, úsalo en `"url"`; si no, deja el enlace genérico a la actividad reciente.

### Cambiar la publicación destacada (portada del blog)

Edita el objeto `"featured"` en el mismo archivo. Admite una etiqueta `<em>...</em>` en el título si quieres una palabra en cursiva.

### Añadir un artículo de Gaceta Fiscal

Añade un objeto a la lista `"gaceta"`:

```json
{ "label": "Gaceta Fiscal · Nº 460", "desc": "Artículo en la revista jurídico-tributaria", "year": "2026" }
```

### Publicar el cambio

```bash
git add assets/posts.json
git commit -m "Nuevo artículo: <título>"
git push
```

GitHub Pages se actualiza solo a los pocos minutos de hacer `push` a `main`.

### Previsualizar en local antes de publicar

`posts.json` se carga con `fetch`, así que abrir `index.html` directamente como archivo (`file://`) no funciona en todos los navegadores. Sirve la carpeta con un servidor local:

```bash
python -m http.server 8000
```

Y abre `http://localhost:8000/`.
