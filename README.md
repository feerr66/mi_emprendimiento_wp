# Rocky's Garage · Sitio WordPress

- **Sitio en producción:** https://rockys-garage.infinityfree.me
- **Prototipo en Stitch:** https://stitch.google.com/projects/1726645708207365365
- **Repo del Parcial 02:** https://github.com/feerr66/mi-emprendimiento.git
- **Autor/a:** Fernanda Ubeda 001D

## Contexto de la web

Rocky's Garage es un taller de servicio automotriz de Villa Alemana que ofrece mantenciones generales, frenos, embrague, culatas y mecánica ligera. El sitio está pensado para personas que tienen un problema con su auto y quieren entenderlo antes de decidir dónde repararlo. Resuelve la falta de claridad y de precios previos en los talleres: explica cada falla en palabras sencillas y muestra las piezas cambiadas. Quiero que quien llega conozca el taller, lea algún consejo del blog y escriba por el formulario de Contacto para pedir una cotización o una hora de revisión.

## Mi tema

- [x] **Tema propio:** `Rocky Garage Theme` (construido a partir de `tema-base/`)
- [ ] **Tema descargado:** (no aplica)

### Instrucciones para instalar mi tema en un WordPress limpio

1. **Descarga el tema:** comprime la carpeta del tema (`Rocky Garage Theme`, dentro de `proyecto/`) en un `.zip`.
2. **Instálalo:** en WordPress, **Apariencia > Temas > Añadir nuevo > Subir tema**, elige el `.zip` y pulsa **Instalar ahora**.
3. **Actívalo:** pulsa **Activar**.
4. **Configura la portada:** **Ajustes > Lectura > Una página estática** y elige la página *Inicio*.
5. **Crea el menú:** **Apariencia > Menús** (o Editor > Navegación) con Inicio, Blog, Nosotros y Contacto, y asígnalo al menú principal.
6. **Instala los plugins** que necesita (ver tabla más abajo).
7. **Crea las páginas y entradas** (ver más abajo).

**Qué debe tener el servidor:** WordPress 7.0.2 y PHP 8.4.28 (las versiones con que probé el sitio), con Apache y enlaces permanentes activados.

## Cómo llevé mi sitio de Local a producción

- **Plugin de migración que uso:** All-in-One WP Migration https://es.wordpress.org/plugins/all-in-one-wp-migration/. Gratis. Límites: en mi servidor el tamaño máximo de subida de archivos es de 20 MB (`post_max_size` de 30 MB), así que el archivo `.wpress` que importe debe pesar menos que eso; además la versión gratuita del plugin tiene su propio límite de importación.
- **Qué se exporta:** entradas, páginas, imágenes (medios), menús, plugins, tema y configuración.

Pasos:

1. **En Local:** en el sitio de desarrollo (LocalWP) voy a **All-in-One WP Migration > Exportar a > Archivo** y descargo el archivo `.wpress`.
2. **En producción:** instalo un WordPress limpio en InfinityFree, e instalo el mismo plugin de migración.
3. **Importa:** voy a **All-in-One WP Migration > Importar**, cargo el archivo `.wpress` y confirmo la importación.
4. **Revisa:** enlaces permanentes (Ajustes > Enlaces permanentes > Guardar), menú, página de inicio, imágenes y formulario de contacto con un mensaje de prueba.
5. **Problemas que tuve y cómo los resolví:**
   - **Error 500 al instalar plugins desde mi copia local:** instalé los plugins directamente en el sitio de producción.
   - **Bloqueo de acceso al admin** («Has superado el máximo de intentos de acceso»): lo causó el plugin Loginizer, que bloquea tras varios intentos fallidos. Esperé los 15 minutos del bloqueo antes de volver a intentar. «COMPLETAR: cómo recuperaste la contraseña realmente».
   - **`?i=1` en la URL:** lo agrega InfinityFree para protegerse de bots. No es un error.

## Respaldo y reinstalación en otro servidor

**Qué respaldar:**

- Los archivos de WordPress (tema, plugins, imágenes subidas).
- La base de datos (páginas, entradas, menús, configuración).

**Cómo respaldo mi sitio:** con All-in-One WP Migration, en **Exportar a > Archivo**. El archivo `.wpress` incluye archivos y base de datos, y queda en mi computador antes de cada cambio grande.

**Cómo lo reinstalo en un servidor nuevo:**

1. **Requisitos del servidor:** PHP 8.4 (probado con 8.4.28), WordPress 7.0.2, MySQL/MariaDB «COMPLETAR: Herramientas > Salud del sitio > Información > Base de datos»; memoria PHP de 512 MB y espacio suficiente para el archivo de respaldo y las imágenes.
2. **Instalar WordPress limpio:** desde el panel del hosting (instalador de WordPress) o subiendo WordPress manualmente y creando una base de datos.
3. **Restaurar el respaldo:** instalo All-in-One WP Migration, voy a **Importar**, subo el `.wpress` y confirmo.
4. **Ajustar:** guardo los enlaces permanentes (estructura «día y nombre»: `/%year%/%monthnum%/%day%/%postname%/`), reviso que la URL del sitio sea la del nuevo servidor (Ajustes > Generales), y compruebo menú y página de inicio.
5. **Probar:** reviso el sitio, las imágenes y envío un mensaje de prueba por el formulario de contacto para confirmar que llega al correo.

**Problemas que tuve y cómo los resolví:** ver la sección anterior.

## Plugins instalados

| Plugin | Para qué lo uso | Gratis o de pago | Versión |
|---|---|---|---|
| Yoast SEO (SEO) | Títulos meta, descripciones y sitemap XML | Gratis | «COMPLETAR: solo si lo tienes instalado» |
| Forminator (Contacto) | Formulario de contacto con confirmación y aviso por correo | Gratis | 1.58.6 |
| WP Mail SMTP | Mejorar el envío de correos del formulario | Gratis | 4.10.4 |
| All-in-One WP Migration | Exportar e importar el sitio (respaldo y migración) | Gratis | 7.113 |
| Loginizer | Seguridad: bloquea intentos repetidos de acceso al admin | Gratis | 2.1.2 |
| W3 Total Cache | Caché para mejorar la velocidad | Gratis | 2.11.0 |

> Versiones tomadas de **Plugins > Plugins instalados**. Si tienes otros plugins activos (por ejemplo Yoast SEO), agrégalos con su versión.

## Páginas y entradas

- **Páginas:** Inicio, Blog, Nosotros y Contacto. 
- **Entradas del blog:**
  1. ¿Qué significa la luz check engine y cuándo es urgente?
  2. 5 señales de que tu embrague está fallando
  3. ¿Cada cuántos kilómetros cambiar el aceite?

## Cómo me organicé

Mi plan y mi plan B están en [`decisiones.md`](proyecto/decisiones.md). Cambié el plugin del formulario: pasé de WPForms a Forminator porque WPForms falló y Contact Form 7 salió incompatible con la versión de WordPress del hosting (el detalle y las capturas están en `decisiones.md`).

## Plan de continuidad y rendimiento

- **Plan de continuidad (etapa 2 de mi web):** [`plan-de-continuidad.md`](proyecto/plan-de-continuidad.md)
- **Análisis de rendimiento con Lighthouse:** [`lighthouse.md`](proyecto/lighthouse.md)

## Uso de IA

- **Claude (Anthropic):** lo usé para ordenar los pasos de la entrega, entender errores (500 al instalar plugins, bloqueo de acceso, plugin incompatible) y redactar borradores de documentación. «COMPLETAR: qué ajusté yo, por ejemplo, textos, colores, elección de Forminator, pruebas del formulario».
