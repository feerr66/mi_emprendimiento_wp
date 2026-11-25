# Análisis de rendimiento con Lighthouse

**Sitio analizado:** https://rockys-garage.infinityfree.me (página de inicio, en producción)
**Herramienta:** Lighthouse en Chrome (DevTools, F12)
**Dispositivo:** móvil
**Fecha del análisis:** 25 de noviembre de 2026

## 1. Resultados (1 pt)

| Categoría | Puntaje (0 a 100) |
|---|---|
| Rendimiento | 75 |
| Accesibilidad | 100 |
| Buenas prácticas | 100 |
| SEO | 92 |

**Evidencia:** captura del informe en `lighthouse-movil.png` (misma carpeta `proyecto/`).

![Informe de Lighthouse](lighthouse-movil.png)

## 2. Análisis (1 pt)

- **Qué significan mis puntajes:**
  - **Rendimiento** mide qué tan rápido carga y se vuelve usable la página en el celular: cuánto tarda en mostrar el contenido principal, si el diseño se mueve mientras carga y cuánto pesa lo que descarga.
  - **Accesibilidad** mide si personas con dificultades visuales, motrices u otras pueden usar el sitio: contraste de colores, textos alternativos en las imágenes, nombres en los enlaces y los botones.
  - **Buenas prácticas** revisa aspectos técnicos de calidad y seguridad, como usar HTTPS, no tener errores en la consola del navegador y cargar imágenes con proporciones correctas.
  - **SEO** revisa lo básico para que Google pueda entender la página: título, descripción meta, enlaces rastreables y que se vea bien en móvil.
  - En mi caso, Accesibilidad y Buenas prácticas salieron en 100, SEO en 92 y Rendimiento en 75, que es el resultado más bajo.
- **Mi mejor categoría y por qué:** Accesibilidad y Buenas prácticas, con 100. El sitio usa HTTPS y no muestra errores técnicos, y el tema tiene buen contraste y textos legibles.
- **Mi categoría más débil y por qué:** Rendimiento, con 75. La carga en móvil depende de lo que pesan las imágenes (la foto grande del motor en el inicio) y de la velocidad del servidor gratuito.
- **Problemas que encontré en el informe:** «COMPLETAR: 3 o 4 de las secciones Oportunidades y Diagnóstico de Rendimiento, y 1 de SEO (por qué no llegó a 100)». Además, Lighthouse avisó que la URL `/?i=1` fue redirigida a `/?i=2`.

**Límites del hosting gratuito:** InfinityFree tiene recursos compartidos y poco control del servidor (por ejemplo, la caché de código de PHP está desactivada y no hay CDN), por lo que el tiempo de respuesta puede ser más lento de lo que sería en un hosting de pago. Esto influye en mi puntaje de rendimiento y no depende solo de mi tema. Además, la protección anti-bots de InfinityFree agrega `?i=1` o `?i=2` a la URL y redirige la visita, y Lighthouse avisó que esto puede afectar la medición, por lo que el puntaje puede variar entre ejecuciones.

## 3. Mejoras (1 pt)

| Mejora | Qué problema resuelve | ¿Aplicada o propuesta? | Resultado (si la aplicaste) |
|---|---|---|---|
| Comprimir y redimensionar las imágenes, sobre todo la foto del motor de la página de inicio | Imágenes muy pesadas que retrasan la carga en móvil | Propuesta | — |
| Activar la caché con W3 Total Cache (ya instalado) | Cada visita regenera la página; la caché sirve una copia ya lista | Propuesta | — |
| Corregir el ítem de SEO que quitó puntos en el informe (por ejemplo, agregar una descripción meta a las páginas) | SEO en 92 en vez de 100 | Propuesta | — |
| Pasar a un hosting de pago con PHP optimizado | Tiempo de respuesta lento del servidor gratuito | Propuesta (etapa 2, ver `plan-de-continuidad.md`) | — |
