# Herramientas de imágenes | NeuroNova Apps

Este repositorio aloja dos utilidades web independientes bajo una portada común.

## Rutas

- Catálogo: https://neuronova-apps.github.io/qr-generador/
- Generador QR: https://neuronova-apps.github.io/qr-generador/qr/
- Convertidor de imágenes: https://neuronova-apps.github.io/qr-generador/convertidor-imagenes/

## Estructura

- `index.html`: tarjetas de acceso a ambas aplicaciones.
- `qr/index.html`: aplicación QR original, conservada con la adaptación de ruta para su logotipo.
- `assets/crebe-logo.png`: logotipo compartido que continúa utilizando el generador QR.
- `convertidor-imagenes/index.html`: conversión y redimensionamiento local de imágenes.

El convertidor permite seleccionar uno o varios archivos, exportar a PNG, JPEG y WebP, y exportar a AVIF cuando el navegador lo admite. Permite ajustar ancho, alto, proporción y calidad. No envía imágenes a un servidor. En imágenes animadas solo procesa el primer fotograma. La exportación por lotes se descarga como archivos individuales; algunos navegadores solicitan autorización para descargas múltiples.

El generador QR requiere conexión a bibliotecas externas mediante CDN. El convertidor no requiere API ni servicio de conversión externo.

## Cierre funcional de la integración (9 de noviembre de 2026)

**Estado:** cierre funcional satisfactorio, conforme a la comprobación de uso comunicada por el usuario.

Se consolidó una portada con dos tarjetas de acceso, se ubicó el generador QR en `/qr/` y se incorporó el convertidor de imágenes en `/convertidor-imagenes/`, conservando el repositorio `qr-generador` y el logotipo del generador QR. El usuario indicó que utilizó las herramientas y que funcionan correctamente.

**Alcance del cierre:** validación humana de uso. No se atribuyen pruebas automatizadas exhaustivas, compatibilidad universal entre navegadores ni auditorías adicionales que no se hayan realizado. No se requieren nuevas funcionalidades para el alcance actual. Se mantienen como mejoras opcionales futuras las descargas ZIP, formatos adicionales o edición avanzada.

**Mantenimiento:** preservar las rutas públicas y el comportamiento validado; cualquier cambio posterior debe verificarse antes de publicarse.

## Antecedentes y cierre histórico del generador QR

El texto siguiente conserva el registro de la versión de QR validada antes de esta reorganización.

---

# Generador de QR personalizados

Aplicación web independiente de **NeuroNova Apps (NN)** para crear códigos QR a partir de enlaces HTTP(S), personalizar su apariencia y validar la decodificación del archivo renderizado antes de habilitar las descargas.

## Versión 1.0.0 — cierre funcional

**Fecha del cierre:** 30 de octubre de 2026.

**Estado:** primera versión funcional, con confirmación satisfactoria de funcionamiento comunicada por el usuario. Se registra esa validación humana sin atribuirle pruebas automatizadas, de laboratorio o de múltiples dispositivos que no hayan sido documentadas.

**Alcance:** generador QR independiente, sin modificaciones a EVA ni a sus repositorios.

### Funciones incluidas

- Enlaces de destino HTTP(S) editables.
- Colores y degradados personalizados.
- Módulos cuadrados, redondeados y puntos; patrones de esquina diferenciados.
- Logotipo CREBE predeterminado, opción sin logotipo y subida de logotipos PNG, JPEG o WebP (máximo 3 MB).
- Tamaño de logotipo configurable entre 5 % y 35 %, ajustable automáticamente si es necesario para la lectura.
- Margen blanco y resolución de exportación configurables.
- Pruebas de diferentes tamaños de logo y niveles de corrección de errores para conservar la imagen y buscar la menor densidad compatible con la decodificación.
- Decodificación mediante jsQR de la representación PNG renderizada, con comparación exacta del enlace; las descargas se bloquean si no se logra verificar.
- Descarga PNG y SVG.

### Validación y criterios de cierre

El usuario confirmó que el generador funciona correctamente después de revisar el diseño y los ajustes realizados. Se considera completado el cierre funcional de la primera versión. No se afirma una certificación universal de escaneabilidad ni pruebas automáticas externas no registradas.

### Precauciones

La validación en el navegador no sustituye las comprobaciones con cámaras físicas, diferentes distancias de lectura o condiciones reales de impresión. Es posible que un enlace más extenso requiera más módulos; no se reduce artificialmente el patrón a costa de perder información. El logotipo se procesa en el navegador y no se carga a un servicio propio.

## Uso y despliegue

Página de referencia: https://neuronova-apps.github.io/qr-generador/

Abrir `index.html` en el navegador. Las bibliotecas `qr-code-styling` y `jsQR` se cargan desde CDN, por lo que se necesita conexión a Internet al menos para cargar dichas dependencias. La publicación mediante GitHub Pages utiliza la rama `main` y la carpeta raíz.

## Mantenimiento posterior

La versión 1.0.0 se considera una línea de referencia funcional. Las mejoras posteriores deben realizarse de manera controlada, sin modificar innecesariamente el funcionamiento validado. Para conservar una referencia inmutable en GitHub, se recomienda crear una etiqueta Git `v1.0.0` que apunte al commit de cierre documental. La existencia de esa etiqueta deberá verificarse por separado; esta documentación no constituye una etiqueta Git.
