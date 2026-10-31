# Generador de QR personalizados

Aplicación web independiente de NeuroNova Apps para generar códigos QR de enlaces HTTP(S), personalizarlos y comprobar automáticamente su decodificación antes de habilitar la descarga.

## Funciones iniciales
- Enlace editable, colores y degradado.
- Módulos cuadrados, redondeados o puntos.
- Logo PNG/JPEG/WebP opcional (máximo 3 MB), limitado al 20 %.
- Selección de resolución y margen blanco.
- Decodificación automática en navegador mediante jsQR, con comprobación de coincidencia exacta.
- Recuperación de diseño mediante intento sin logo y luego módulos cuadrados negros si no se decodifica.
- Descarga PNG y SVG solo después de validar la vista renderizada.

## Uso
Abrir `index.html` en un navegador con acceso a Internet. El generador carga `qr-code-styling` y `jsQR` desde CDN. En GitHub Pages publicar desde la rama `main`, carpeta `/ (root)`.

## Precauciones
La validación automática no garantiza lectura en todos los dispositivos o condiciones de impresión: verificar también mediante cámara real antes de difundir. El enlace de MEA es un ejemplo inicial editable; no hay dependencia de EVA ni de sus módulos. La herramienta procesa el logotipo en el navegador, sin subida a servidor.

## Estado
Primera versión técnica. Pendiente validación humana de lectura con teléfono, comprobación de exportaciones y activación de GitHub Pages. No se afirma que la implementación haya pasado pruebas de navegador real.
