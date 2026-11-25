# Análisis de rendimiento con Lighthouse

**Sitio analizado:** https://rockys-garage.infinityfree.me (página de inicio, en producción)
**Herramienta:** «COMPLETAR: Lighthouse en Chrome o PageSpeed Insights»
**Dispositivo:** móvil
**Fecha del análisis:** 25 de noviembre de 2026

## 1. Resultados (1 pt)

| Categoría | Puntaje (0 a 100) |
|---|---|
| Rendimiento | 75 |
| Accesibilidad | 100 |
| Buenas prácticas | 100 |
| SEO | 92 |

**Evidencia:** `lighthouse-movil.png`

## 2. Análisis (1 pt)

- **Qué significan mis puntajes:**
  - **Rendimiento** mide qué tan rápido carga y se vuelve usable la página en el celular: cuánto tarda en mostrar el contenido principal, si el diseño se mueve mientras carga y cuánto pesa lo que descarga.
  - **Accesibilidad** mide si personas con dificultades visuales, motrices u otras pueden usar el sitio: contraste de colores, textos alternativos en las imágenes, nombres en los enlaces y los botones.
  - **Buenas prácticas** revisa aspectos técnicos de calidad y seguridad, como usar HTTPS, no tener errores en la consola del navegador y cargar imágenes con proporciones correctas.
  - **SEO** revisa lo básico para que Google pueda entender la página: título, descripción meta, enlaces rastreables y que se vea bien en móvil.
  - «COMPLETAR: cómo te fue en cada una, con tus palabras, mirando tus puntajes»
- **Mi mejor categoría y por qué:** «COMPLETAR: la de puntaje más alto y la razón»
- **Mi categoría más débil y por qué:** «COMPLETAR: la de puntaje más bajo y la razón»
- **Problemas que encontré en el informe:** «COMPLETAR: copia 3 o 4 de la sección "Oportunidades" y "Diagnóstico" del informe; por ejemplo imágenes pesadas, texto sin contraste suficiente, falta de descripción meta, JavaScript sin usar»

**Límites del hosting gratuito:** InfinityFree tiene recursos compartidos y poco control del servidor (por ejemplo, la caché de código de PHP está desactivada y no hay CDN), por lo que el tiempo de respuesta puede ser más lento de lo que sería en un hosting de pago. Esto influye en mi puntaje de rendimiento y no depende solo de mi tema.

## 3. Mejoras (1 pt)

| Mejora | Qué problema resuelve | ¿Aplicada o propuesta? | Resultado (si la aplicaste) |
|---|---|---|---|
| Comprimir y redimensionar las imágenes, sobre todo la foto del motor de la página de inicio | Imágenes muy pesadas que retrasan la carga en móvil | «COMPLETAR: Aplicada o Propuesta» | «COMPLETAR: puntaje antes y después, o "—"» |
| Activar la caché con W3 Total Cache (ya instalado) | Cada visita regenera la página; la caché sirve una copia ya lista | «COMPLETAR: Aplicada o Propuesta» | «COMPLETAR: puntaje antes y después, o "—"» |
| «COMPLETAR: una tercera mejora según tu informe, por ejemplo agregar descripción meta a las páginas, subir el contraste del texto, o agregar texto alternativo a las imágenes» | «COMPLETAR» | «COMPLETAR» | «COMPLETAR» |
| Pasar a un hosting de pago con PHP optimizado | Tiempo de respuesta lento del servidor gratuito | Propuesta (etapa 2, ver `plan-de-continuidad.md`) | — |
