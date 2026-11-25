# Plan de continuidad · Etapa 2 de mi sitio

**Emprendimiento:** Rocky's Garage (servicio automotriz, Villa Alemana)
**Sitio de la etapa 1:** https://rockys-garage.infinityfree.me
**Fecha:** 25 de noviembre de 2026

La etapa 1 dejó un sitio publicado con Inicio, Blog (3 entradas), Nosotros y Contacto con formulario. La etapa 2 busca convertir esas visitas en clientes: que puedan agendar, preguntar y confiar, desde un servidor más estable que el hosting gratuito.

## 1. Qué quedó fuera de la etapa 1 y por qué (3 pts)

| Funcionalidad | Por qué quedó fuera (tiempo, recursos, costo, conocimientos) | Qué aporta a mi emprendimiento |
|---|---|---|
| Tienda online de repuestos y fluidos (WooCommerce) | **Tiempo y conocimientos:** requiere cargar productos, configurar pagos, envíos e inventario. **Recursos:** WooCommerce y un hosting gratuito con límites de CPU y RAM no se llevan bien. | Vender fluidos y repuestos sin que el cliente vaya al taller, y generar ingresos fuera de las horas de atención. |
| Reserva de horas online con calendario (Booking Calendar) | **Tiempo y recursos:** pasé varios días resolviendo errores del hosting (500/429) y del formulario de contacto, y no alcancé a probar la reserva con calma. | Que el cliente elija su hora de revisión y yo ordene la agenda sin llamadas ni mensajes cruzados. |
| Preguntas Frecuentes (garantías y tiempos de reparación) | **Tiempo:** prioricé tener el sitio funcionando, el formulario y las 3 entradas del blog. | Responder dudas antes de que lleguen por mensaje y generar confianza. |
| Botón flotante de WhatsApp (Joinchat) | **Tiempo:** quedó detrás de lo obligatorio (formulario y contenido). | Cotizar rápido por el canal que más usan mis clientes. |
| Envío confiable de correos del formulario (SMTP) | **Recursos:** el hosting gratuito limita el envío de correos y las conexiones SMTP. | Que ningún mensaje de un cliente se pierda. |
| Catálogo de servicios con precios referenciales (página Servicios) | **Tiempo:** definir precios y fotos de cada servicio requiere conversarlo con el taller. | Mostrar frenos, embrague, culatas y mantenciones con precio claro, que es mi promesa de marca. |

## 2. Recursos que necesito (2 pts)

> Los costos son aproximados y hay que verificarlos al momento de contratar.

| Funcionalidad | Plugin o herramienta | Gratis o de pago | Costo aproximado | Qué tendría que aprender |
|---|---|---|---|---|
| Tienda online | WooCommerce | Gratis | US$ 0 el plugin | Cargar productos y categorías, configurar impuestos, envíos y stock |
| Pagos en la tienda | Webpay Plus (Transbank) o Mercado Pago, para WooCommerce | Gratis el plugin, con comisión por venta | Comisión por transacción (según el contrato con el proveedor) | Crear la cuenta comercial y probar pagos en modo prueba |
| Reserva de horas | Booking Calendar (u otra alternativa como Simply Schedule Appointments) | Versión gratuita con funciones limitadas; la versión Pro es de pago | US$ 0 a algunas decenas de dólares | Definir horarios, duración de cada servicio y correos automáticos |
| Preguntas frecuentes | Bloque de acordeón de Gutenberg o un plugin de FAQ | Gratis | US$ 0 | Redactar las preguntas con la gente del taller |
| WhatsApp | Joinchat | Gratis | US$ 0 | Configurar el número y el mensaje inicial |
| Correo confiable | WP Mail SMTP con un servicio como Brevo | Gratis (con límite de envíos diarios) | US$ 0 | Configurar el servicio y autenticar el dominio |
| Dominio propio | Dominio .cl | De pago (anual) | Del orden de CLP 10.000 al año (verificar en NIC Chile al contratar) | Apuntar el dominio al hosting |
| Velocidad | W3 Total Cache (ya instalado) y optimización de imágenes (Smush o similar) | Gratis | US$ 0 | Configurar caché y compresión sin romper el sitio |

**Servidor:** para la etapa 2 necesitaría un hosting de pago para WordPress, con PHP 8.x (hoy uso 8.4), base de datos MySQL/MariaDB, certificado SSL gratuito incluido, al menos 2 GB de espacio para imágenes y una tienda, y sin los límites de CPU y RAM del plan gratuito. Los errores 500 y 429 que tuve en InfinityFree, el correo poco confiable y un entorno con caché de código desactivado son las razones. Un plan compartido básico, con costo mensual de unos pocos dólares, bastaría al inicio. Si la tienda crece, pasaría a un plan con más recursos.

## 3. Priorización y cronograma (2 pts)

| Prioridad | Qué hago | Cuándo (mes o semana) | Resultado esperado |
|---|---|---|---|
| 1 | Contratar hosting de pago y dominio, y migrar el sitio con All-in-One WP Migration (siguiendo el README) | Semana 1 de diciembre | Sitio estable con dominio propio y HTTPS, sin errores 500/429 |
| 2 | Configurar correo confiable (SMTP) y probar el formulario de contacto | Semana 1 de diciembre | Todos los mensajes de clientes llegan al correo del taller |
| 3 | Reserva de horas online y botón de WhatsApp | Semanas 2 y 3 de diciembre | El cliente agenda su revisión sin llamar |
| 4 | Páginas Servicios y Preguntas Frecuentes | Semana 4 de diciembre | El cliente entiende qué ofrece el taller y qué garantía tiene |
| 5 | Mejoras de velocidad según el análisis de Lighthouse (imágenes, caché) | Enero de 2027 | Mejor puntaje de rendimiento en móvil |
| 6 | Tienda online con WooCommerce y pasarela de pago, primero con pocos productos | Febrero a marzo de 2027 | Primeras ventas de fluidos y repuestos |

## 4. Riesgos y mitigación (1 pt)

| Riesgo | Qué haría | Cuándo se activa |
|---|---|---|
| El hosting de pago cuesta más de lo previsto | Elegir un plan más básico, postergar la tienda y priorizar reserva y WhatsApp, que no necesitan tanto servidor | Si el costo mensual supera lo que el taller puede pagar |
| La migración rompe el sitio (enlaces, imágenes o formulario) | Restaurar desde el respaldo `.wpress`, probar primero en un entorno local y repetir la importación | Si tras migrar hay errores o faltan imágenes |
| El plugin de reservas o de pagos falla o es incompatible con mi versión de WordPress | Cambiar a una alternativa equivalente (como me pasó con el formulario, que reemplacé por Forminator) | Al detectar errores o incompatibilidad al activarlo |
| El taller no tiene tiempo para actualizar productos o contestar mensajes | Empezar con la tienda pequeña y una persona a cargo de responder en horarios fijos | Si pasan más de dos semanas sin actualizar el sitio |
| Los correos del formulario no llegan o caen en spam | Usar SMTP con un servicio dedicado y avisar en la página que también pueden escribir por WhatsApp | Si una prueba mensual no llega a la bandeja de entrada |
