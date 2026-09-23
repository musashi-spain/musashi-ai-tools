# Musashi AI · Herramientas

Portal de utilidades internas de **Musashi AI**.

**Enlace público:** <https://musashi-spain.github.io/musashi-ai-tools/>

## Estructura

```
musashi-ai-tools/
├── index.html                  Portal: lista las herramientas disponibles
├── simulador-lentes/
│   └── index.html              Simulador de lentes y cámaras (autocontenido)
├── .nojekyll                   Evita el procesado de Jekyll en GitHub Pages
├── LICENSE                     Licencia MIT
└── README.md
```

## Herramientas

### Simulador de lentes y cámaras

Calculadora visual de visión artificial. Relaciona sensor, distancia focal, distancia de trabajo (WD),
campo de visión (FOV) y profundidad de campo (DoF).

- Catálogo multi-marca verificado: **Basler, FLIR/Teledyne, The Imaging Source, IDS, Allied Vision**
  (cámaras) y **Basler, Computar, Kowa, Fujinon** (lentes).
- Autoajuste de formato y sensor según la lente, con comprobación de cobertura del círculo de imagen.
- Simulación de **anillos separadores** (extension tubes) con la física de Gauss completa.
- Pieza circular opcional para verificar que el FOV la cubre.
- Vistas esquemáticas en vivo (plano horizontal y vertical) con cono de visión y franja de DoF.
- Criterio de nitidez (CoC) seleccionable: 1, 2 o 3 px.
- Exportación de la configuración al portapapeles.

Abre `simulador-lentes/index.html` directamente en el navegador o entra desde el portal.

## Añadir una nueva herramienta

1. Crea una subcarpeta con su propio `index.html`:
   ```
   nueva-herramienta/index.html
   ```
2. Añade un bloque `<a class="tool">` en el `index.html` raíz, siguiendo el ejemplo del simulador.
3. Mantén las **rutas relativas** para que funcione tanto en local como en GitHub Pages.

## Publicar en GitHub Pages

1. Sube el contenido a un repositorio de GitHub.
2. En **Settings → Pages**, selecciona:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` · carpeta `/ (root)`
3. La web quedará en `https://musashi-spain.github.io/musashi-ai-tools/`.

El archivo `.nojekyll` ya está incluido para que GitHub Pages sirva los archivos tal cual,
sin intentar procesarlos con Jekyll.

## Desarrollo local

No requiere servidor ni compilación: abre `index.html` en el navegador.
Si el navegador bloquea alguna función (por ejemplo el portapapeles), puedes servir la carpeta
con cualquier servidor estático:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## Notas

- Las especificaciones del catálogo están tomadas de la documentación oficial de cada fabricante.
- La herramienta es una ayuda de dimensionado; valida siempre los cálculos con la MTF de la lente
  y el modelo de desenfoque real de tu aplicación.

## Licencia

Publicado bajo licencia **MIT**. Consulta [LICENSE](LICENSE).
