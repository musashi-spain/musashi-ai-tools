# AGENTS.md

Portal de herramientas internas de **Musashi AI** (visión artificial / inspección automatizada). Sitio 100 % estático, sin build ni dependencias, publicado con GitHub Pages.

## Estructura

```
index.html              Portal: lista las herramientas
simulador-lentes/       Simulador de lentes y cámaras (HTML+CSS+JS en un solo archivo)
.nojekyll               Evita el procesado de Jekyll en Pages
```

## Reglas

- Cada herramienta vive en su propia subcarpeta con un `index.html` **autocontenido** (CSS y JS embebidos, sin dependencias externas salvo fuentes de Google).
- Enlaza las herramientas desde el portal con **ruta relativa explícita** (`herramienta/index.html`, no `herramienta/`), o el navegador lista el directorio en local.
- Mantén la **identidad Musashi AI**: Poppins, azul `#008cc5`/`#054cd9`/`#20beff`, Space Cadet `#2e324f`, y estilo **sin tarjetas** (filas con líneas finas).
- Verifica siempre en navegador antes de dar algo por terminado: abre el `index.html` y comprueba que renderiza sin errores de consola.

## Añadir una herramienta

1. `nueva-herramienta/index.html`
2. Un bloque `<a class="tool">` nuevo en el `index.html` raíz, copiando el del simulador.

## Especificaciones técnicas

Los datos de catálogo (cámaras, lentes) deben venir de **documentación oficial del fabricante**, nunca inventados. Indica el modelo exacto y verifica coherencia entre resolución, tamaño de píxel y dimensiones del sensor.
