---
title: "Galería de Fotos de Clientes - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Galería de Fotos de Clientes de MyPresta.eu."
sidebar:
  label: "Galería de Fotos de Clientes - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customer Photo Gallery en MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-photo-gallery.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/customer-photo-gallery/)
>
> ---


# Galería de Fotos de Clientes

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y cualquier interacción del módulo. Asegúrese de que su servidor tenga suficiente espacio en disco para almacenar las fotos y videos subidos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo Galería de Fotos de Clientes, donde controla todas sus características y cómo aparece en su tienda.

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- |
| **Permitir Subidas JPEG** | SÍ | **Qué hace este ajuste:** Controla si los clientes pueden subir imágenes en formato JPEG.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los clientes pueden subir archivos .jpg y .jpeg.   *Cuando está deshabilitado:* Los archivos JPEG serán rechazados durante la subida.   **Valor recomendado:** SÍ (JPEG es un formato de imagen muy común).   **Escenario del comerciante:** Si desea restringir los tipos de imagen por razones específicas de calidad o marca, podría deshabilitar algunos formatos. |
| **Permitir Subidas GIF** | SÍ | **Qué hace este ajuste:** Controla si los clientes pueden subir imágenes en formato GIF.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los clientes pueden subir archivos .gif.   *Cuando está deshabilitado:* Los archivos GIF serán rechazados.   **Valor recomendado:** SÍ (los GIF pueden ser útiles para animaciones simples o fondos transparentes). |
| **Permitir Subidas PNG** | SÍ | **Qué hace este ajuste:** Controla si los clientes pueden subir imágenes en formato PNG.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los clientes pueden subir archivos .png.   *Cuando está deshabilitado:* Los archivos PNG serán rechazados.   **Valor recomendado:** SÍ (PNG es excelente para imágenes con transparencia y alta calidad). |
| **Permitir Subidas BMP** | NO | **Qué hace este ajuste:** Controla si los clientes pueden subir imágenes en formato BMP.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los clientes pueden subir archivos .bmp.   *Cuando está deshabilitado:* Los archivos BMP serán rechazados.   **Valor recomendado:** NO (los archivos BMP suelen ser muy grandes y sin comprimir, no ideales para uso web).   **Escenario del comerciante:** Habilite solo si tiene una necesidad específica de imágenes sin comprimir, pero tenga en cuenta el impacto en el almacenamiento del servidor y los tiempos de carga de la página. |
| **Habilitar Paginación** | SÍ | **Qué hace este ajuste:** Determina si las páginas de la galería usarán paginación (por ejemplo, "Página 1 de 5").   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* El contenido de la galería se divide en varias páginas, mejorando los tiempos de carga para galerías grandes.   *Cuando está deshabilitado:* Todo el contenido de la galería se carga en una sola página, lo que puede ser lento para muchas fotos.   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Esencial para gestionar galerías grandes y proporcionar una experiencia de usuario fluida. |
| **Permitir Subidas a Usuarios No Registrados** | NO | **Qué hace este ajuste:** Permite a los visitantes que no han iniciado sesión en una cuenta de cliente subir fotos.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los invitados pueden subir fotos. Esto puede aumentar las contribuciones, pero también podría llevar a más spam o contenido irrelevante.   *Cuando está deshabilitado:* Solo los clientes que han iniciado sesión pueden subir fotos, asegurando cierto nivel de responsabilidad.   **Valor recomendado:** NO (a menos que tenga una fuerte moderación implementada).   **Escenario del comerciante:** Si desea maximizar las contribuciones y está preparado para moderar, habilite esto. De lo contrario, manténgalo deshabilitado para mantener el control de calidad. |
| **Tamaño Máximo de Archivo (MB)** | 5 | **Qué hace este ajuste:** Establece el tamaño máximo (en megabytes) para la subida de un solo archivo de imagen.   **Efecto de cambiar este ajuste:**   *Cuando se establece un valor más alto:* Los clientes pueden subir imágenes más grandes, potencialmente de mayor calidad, pero esto consume más espacio en el servidor y ancho de banda.   *Cuando se establece un valor más bajo:* Restringe el tamaño del archivo, ahorrando recursos del servidor pero potencialmente limitando la calidad de la imagen.   **Valor recomendado:** 5-10 MB suele ser suficiente para imágenes optimizadas para la web.   **Escenario del comerciante:** Equilibre la calidad de la imagen con los recursos del servidor. Demasiado bajo, y los clientes podrían frustrarse; demasiado alto, y sus costos de alojamiento podrían aumentar. |
| **Habilitar Pestaña de Producto** | NO | **Qué hace este ajuste:** Muestra una pestaña dedicada "Fotos de Clientes" en las páginas de productos.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparece una nueva pestaña en las páginas de productos, mostrando fotos específicamente relacionadas con ese producto.   *Cuando está deshabilitado:* No hay una pestaña dedicada para las fotos de clientes en las páginas de productos.   **Valor recomendado:** SÍ (si desea mostrar CGU específico del producto).   **Escenario del comerciante:** Ideal para productos donde los testimonios visuales tienen un gran impacto, como moda o decoración del hogar. |
| **Posición de la Pestaña de Producto (Hook del Módulo)** | displayProductExtraContent | **Qué hace este ajuste:** Determina dónde se engancha la pestaña del producto en la página del producto.   **Efecto de cambiar este ajuste:** Cambia la ubicación visual de la pestaña "Fotos de Clientes" en la página del producto.   **Valor recomendado:** `displayProductExtraContent` o `displayProductTab`.   **Escenario del comerciante:** Pruebe diferentes hooks para encontrar la mejor integración visual con su tema. |
| **Mostrar en el Pie de Página del Producto** | NO | **Qué hace este ajuste:** Muestra un bloque de fotos de clientes en el área del pie de página de las páginas de productos.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparece un pequeño bloque de galería en la parte inferior de las páginas de productos.   *Cuando está deshabilitado:* No hay fotos de clientes en el pie de página del producto.   **Valor recomendado:** NO (a menos que tenga una necesidad de diseño específica).   **Escenario del comerciante:** Se puede usar para fomentar la navegación o la venta cruzada mostrando fotos de clientes relacionadas. |
| **Mostrar en la Cuenta del Cliente** | SÍ | **Qué hace este ajuste:** Añade un enlace a "Mis Fotos" en el panel de control de la cuenta del cliente.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los clientes que han iniciado sesión ven un enlace para administrar sus fotos subidas.   *Cuando está deshabilitado:* Los clientes no pueden acceder fácilmente a su área de gestión de fotos desde su cuenta.   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Esencial para que los clientes administren sus contribuciones. |
| **Mostrar en el Bloque Mi Cuenta** | SÍ | **Qué hace este ajuste:** Añade un enlace a "Mis Fotos" en el bloque "Mi Cuenta" (normalmente en la columna izquierda/derecha o pie de página).   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparece un enlace en el bloque de acceso rápido "Mi Cuenta".   *Cuando está deshabilitado:* No hay enlace en el bloque "Mi Cuenta".   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Proporciona otro punto de acceso conveniente para que los clientes administren sus fotos. |
| **Altura de Miniatura (px)** | 100 | **Qué hace este ajuste:** Establece la altura de las miniaturas generadas para las imágenes de la galería.   **Efecto de cambiar este ajuste:**   *Cuando se establece un valor más alto:* Miniaturas más grandes, potencialmente más claras pero ocupan más espacio.   *Cuando se establece un valor más bajo:* Miniaturas más pequeñas, ahorrando espacio pero con menos detalle.   **Valor recomendado:** 100-150px.   **Escenario del comerciante:** Ajuste para adaptarse al diseño de su tema y asegurar un diseño de galería visualmente atractivo. |
| **Ancho de Miniatura (px)** | 100 | **Qué hace este ajuste:** Establece el ancho de las miniaturas generadas para las imágenes de la galería.   **Efecto de cambiar este ajuste:**   *Cuando se establece un valor más alto:* Miniaturas más grandes.   *Cuando se establece un valor más bajo:* Miniaturas más pequeñas.   **Valor recomendado:** 100-150px.   **Escenario del comerciante:** Ajuste para adaptarse al diseño de su tema y asegurar un diseño de galería visualmente atractivo. |
| **Habilitar Formulario de Subida de Fotos** | SÍ | **Qué hace este ajuste:** Controla la visibilidad del formulario de subida de fotos en la página de la galería.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los clientes pueden ver y usar el formulario de subida.   *Cuando está deshabilitado:* El formulario de subida está oculto, impidiendo nuevas publicaciones.   **Valor recomendado:** SÍ (a menos que desee detener temporalmente nuevas subidas).   **Escenario del comerciante:** Deshabilite si está realizando un concurso con una fecha límite de envío o necesita pausar las subidas por mantenimiento. |
| **Mostrar Enlace a la Galería** | SÍ | **Qué hace este ajuste:** Añade un enlace a la página principal de la galería de fotos en la navegación de su tienda.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparece un enlace (por ejemplo, "Galería de Clientes") en el hook elegido.   *Cuando está deshabilitado:* El enlace a la página principal de la galería está oculto.   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Esencial para que los clientes encuentren y naveguen por la galería. |
| **Mostrar en Columna Derecha** | NO | **Qué hace este ajuste:** Muestra un bloque con fotos recientes de clientes en la columna derecha de su tienda.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparece un bloque en la columna derecha.   *Cuando está deshabilitado:* No hay bloque en la columna derecha.   **Valor recomendado:** NO (puede saturar el diseño, pero depende de su tema).   **Escenario del comerciante:** Útil si su tema tiene amplio espacio en la columna derecha y desea destacar las contribuciones recientes. |
| **Mostrar en Columna Izquierda** | NO | **Qué hace este ajuste:** Muestra un bloque con fotos recientes de clientes en la columna izquierda de su tienda.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparece un bloque en la columna izquierda.   *Cuando está deshabilitado:* No hay bloque en la columna izquierda.   **Valor recomendado:** NO (puede saturar el diseño, pero depende de su tema).   **Escenario del comerciante:** Similar a la columna derecha, use si su tema lo soporta bien. |
| **Habilitar Notificaciones** | SÍ | **Qué hace este ajuste:** Envía notificaciones por correo electrónico al administrador de la tienda cuando se suben nuevas fotos.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Recibe un correo electrónico por cada nueva subida, permitiendo una moderación rápida.   *Cuando está deshabilitado:* No hay notificaciones por correo electrónico.   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Crucial para una moderación oportuna y para asegurar que solo se muestre contenido apropiado. |
| **Número de Fotos en la Página de Inicio** | 8 | **Qué hace este ajuste:** Establece cuántas fotos de clientes se muestran en el bloque de la página de inicio.   **Efecto de cambiar este ajuste:** Cambia la cantidad de fotos mostradas en la página de inicio.   **Valor recomendado:** 6-12, dependiendo del diseño de su página de inicio.   **Escenario del comerciante:** Ajuste para adaptarse al diseño de su página de inicio sin sobrecargar la página. |
| **Orden de Fotos en la Página de Inicio** | Más Recientes Primero | **Qué hace este ajuste:** Determina el orden de clasificación de las fotos mostradas en la página de inicio.   **Efecto de cambiar este ajuste:** Las fotos se pueden ordenar por más recientes, más antiguas, más populares, etc.   **Valor recomendado:** Más Recientes Primero o Más Populares.   **Escenario del comerciante:** "Más Recientes Primero" mantiene el contenido fresco; "Más Populares" destaca el contenido atractivo. |
| **Habilitar Modo Concurso de Fotos** | NO | **Qué hace este ajuste:** Activa funciones para realizar un concurso de fotos, que potencialmente incluye mecanismos de votación y premios.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Podrían aparecer opciones adicionales relacionadas con el concurso, y la galería podría enfatizar la votación.   *Cuando está deshabilitado:* Modo de galería estándar.   **Valor recomendado:** NO (a menos que esté ejecutando activamente un concurso).   **Escenario del comerciante:** Use esto cuando quiera ejecutar una campaña específica para recopilar fotos e involucrar a los usuarios con la votación. |
| **Excluir Productos de la Galería** | (IDs de Producto) | **Qué hace este ajuste:** Le permite especificar IDs de productos que NO deben mostrar fotos de clientes en sus páginas de productos.   **Efecto de cambiar este ajuste:** Las fotos de estos productos específicos no aparecerán en la pestaña/pie de página del producto, incluso si la configuración principal de la pestaña del producto está habilitada.   **Valor recomendado:** Dejar vacío a menos que sea necesario.   **Escenario del comerciante:** Si tiene productos sensibles o productos donde las fotos de clientes son irrelevantes o inapropiadas, puede excluirlos. |
| **Visibilidad del Enlace de la Cuenta del Cliente** | SÍ | **Qué hace este ajuste:** Controla la visibilidad del enlace "Mis Fotos" dentro del panel de control de la cuenta del cliente.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* El enlace es visible.   *Cuando está deshabilitado:* El enlace está oculto.   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Mantener habilitado para la comodidad del cliente. |
| **Visibilidad del Enlace del Bloque Mi Cuenta** | SÍ | **Qué hace este ajuste:** Controla la visibilidad del enlace "Mis Fotos" dentro del bloque "Mi Cuenta" (por ejemplo, en columnas).   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* El enlace es visible.   *Cuando está deshabilitado:* El enlace está oculto.   **Valor recomendado:** SÍ.   **Escenario del comerciante:** Mantener habilitado para la comodidad del cliente. |
| **Habilitar Votación para Fotos** | SÍ | **Qué hace este ajuste:** Permite a los clientes (y opcionalmente a los invitados) votar las fotos subidas.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Aparecen botones/estrellas de votación junto a las fotos.   *Cuando está deshabilitado:* No hay funcionalidad de votación.   **Valor recomendado:** SÍ (aumenta la participación).   **Escenario del comerciante:** Use para identificar fotos populares, realizar concursos o simplemente fomentar la interacción. |
| **Tipo de Sistema de Votación** | Estrellas | **Qué hace este ajuste:** Elige el estilo visual del sistema de votación (por ejemplo, estrellas, pulgares arriba/abajo).   **Efecto de cambiar este ajuste:** Cambia el aspecto del mecanismo de votación.   **Valor recomendado:** Estrellas (generalmente más intuitivo).   **Escenario del comerciante:** Seleccione el estilo que mejor se adapte a la estética de su tienda. |
| **Permitir Votación a Usuarios No Registrados** | NO | **Qué hace este ajuste:** Permite a los visitantes que no han iniciado sesión votar las fotos.   **Efecto de cambiar este ajuste:**   *Cuando está habilitado:* Los invitados pueden votar. Esto puede aumentar la participación, pero podría ser susceptible de abuso.   *Cuando está deshabilitado:* Solo los clientes que han iniciado sesión pueden votar.   **Valor recomendado:** NO (para evitar la manipulación de votos).   **Escenario del comerciante:** Habilite solo si prioriza la máxima participación sobre la estricta integridad del voto. |

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | CG\_ALLOW\_JPEG | SÍ | Permitir subidas de imágenes JPEG. |
| Configuración del Módulo | CG\_ALLOW\_GIF | SÍ | Permitir subidas de imágenes GIF. |
| Configuración del Módulo | CG\_ALLOW\_PNG | SÍ | Permitir subidas de imágenes PNG. |
| Configuración del Módulo | CG\_ALLOW\_BMP | NO | Permitir subidas de imágenes BMP (archivos grandes). |
| Configuración del Módulo | CG\_PAGINATION | SÍ | Habilitar paginación para las páginas de la galería. |
| Configuración del Módulo | CG\_ALLOW\_UNLOGGED | NO | Permitir a los invitados subir fotos. |
| Configuración del Módulo | CG\_MAX\_FILE\_SIZE | 5 MB | Tamaño máximo de archivo para subidas. |
| Configuración del Módulo | CG\_PRODUCTTAB | NO | Mostrar fotos de clientes en una pestaña de producto. |
| Configuración del Módulo | cg\_productTabM | displayProductExtraContent | Hook para la ubicación de la pestaña de producto. |
| Configuración del Módulo | CG\_PRODUCTFOOTER | NO | Mostrar fotos en el pie de página del producto. |
| Configuración del Módulo | CG\_CUSTOMERACCOUNT | SÍ | Mostrar enlace "Mis Fotos" en la cuenta del cliente. |
| Configuración del Módulo | CG\_MYACCOUNTBLOCK | SÍ | Mostrar enlace "Mis Fotos" en el bloque Mi Cuenta. |
| Configuración del Módulo | CG\_THUMBHEIGHT | 100 | Altura de las miniaturas generadas. |
| Configuración del Módulo | CG\_THUMBWIDTH | 100 | Ancho de las miniaturas generadas. |
| Configuración del Módulo | CG\_FUPLOADON | SÍ | Habilitar el formulario de subida de fotos. |
| Configuración del Módulo | CG\_GALLERY | SÍ | Mostrar enlace a la página principal de la galería. |
| Configuración del Módulo | CG\_RIGHTCOL | NO | Mostrar fotos en la columna derecha. |
| Configuración del Módulo | CG\_LEFTCOL | NO | Mostrar fotos en la columna izquierda. |
| Configuración del Módulo | CG\_NTF | SÍ | Enviar notificaciones por correo electrónico al administrador para nuevas subidas. |
| Configuración del Módulo | cg\_hpg\_nb | 8 | Número de fotos en la página de inicio. |
| Configuración del Módulo | cg\_hpg\_o | Más Recientes Primero | Orden de las fotos en la página de inicio. |
| Configuración del Módulo | cg\_contest | NO | Habilitar modo concurso de fotos. |
| Configuración del Módulo | cg\_excludeproduct | (vacío) | IDs de productos a excluir de la galería. |
| Configuración del Módulo | CG\_CUSTOMERACCOUNTV | SÍ | Visibilidad del enlace "Mis Fotos" en la cuenta del cliente. |
| Configuración del Módulo | CG\_MYACCOUNTBLOCKV | SÍ | Visibilidad del enlace "Mis Fotos" en el bloque Mi Cuenta. |
| Configuración del Módulo | CG\_voting | SÍ | Habilitar votación para fotos. |
| Configuración del Módulo | CG\_VOTE\_STAR | Estrellas | Estilo visual del sistema de votación. |
| Configuración del Módulo | cg\_unl\_voting | NO | Permitir a los usuarios no registrados votar. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis fotos subidas no aparecen en la galería.**
**R:**

-   **Verifique la Configuración del Módulo:** Asegúrese de que "Habilitar Formulario de Subida de Fotos" (`CG_FUPLOADON`) esté configurado en SÍ.
-   **Tipo y Tamaño de Archivo:** Verifique que el tipo de archivo subido (JPEG, PNG, GIF, BMP) esté permitido en la configuración del módulo y que el tamaño del archivo esté dentro del límite de "Tamaño Máximo de Archivo" (`CG_MAX_FILE_SIZE`).
-   **Moderación:** El módulo podría tener una cola de moderación interna (aunque no se enumera explícitamente como una configuración, muchos módulos de galería lo hacen). Verifique si hay una sección de administración para aprobar/rechazar fotos.
-   **Permisos:** Asegúrese de que el directorio `img/customersgallery/` (o una ruta similar donde se almacenan las imágenes) en su servidor tenga permisos de escritura (generalmente 755 o 777, aunque 777 es menos seguro).
-   **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** en su Back Office de PrestaShop y borre la caché de Smarty, la caché del navegador y la caché del módulo.

**P2: El enlace o bloque de la galería no aparece en mi tienda.**
**A:**

-   **Hooks del Módulo:** Verifique la página de configuración del módulo. Asegúrese de que "Mostrar Enlace a la Galería" (`CG_GALLERY`), "Mostrar en Columna Derecha" (`CG_RIGHTCOL`), "Mostrar en Columna Izquierda" (`CG_LEFTCOL`), etc., estén habilitados para las ubicaciones que espera.
-   **Gestión de Hooks:** Vaya a **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores) en su Back Office de PrestaShop. Busque el módulo ("Galería de Fotos de Clientes") y asegúrese de que esté enganchado a las posiciones `display` correctas (por ejemplo, `displayHeader`, `displayHome`, `displayRightColumn`). Si no lo está, "Trasplantar un módulo" al hook deseado.
-   **Compatibilidad del Tema:** Algunos temas personalizados pueden anular las posiciones de hook estándar. Si el módulo no aparece a pesar de estar enganchado correctamente, podría requerir pequeños ajustes en el tema. Póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.
-   **Borrar Caché:** Siempre borre la caché de PrestaShop después de realizar cambios en las posiciones o configuraciones del módulo.

**P3: Las fotos en las páginas de productos no aparecen en una pestaña.**
**A:**

-   **Habilitar Pestaña de Producto:** Asegúrese de que `CG_PRODUCTTAB` esté configurado en SÍ en la configuración del módulo.
-   **Hook de la Pestaña de Producto:** Verifique que `cg_productTabM` esté configurado en un hook apropiado como `displayProductExtraContent` o `displayProductTab`.
-   **Exclusión de Producto:** Verifique `cg_excludeproduct` para asegurarse de que el producto que está viendo no esté listado allí.
-   **Fotos Asociadas:** Asegúrese de que realmente haya fotos subidas y asociadas con ese producto específico.
-   **Borrar Caché:** Borre todas las cachés.

**P4: El sistema de votación no funciona o no es visible.**
**A:**

-   **Habilitar Votación:** Asegúrese de que "Habilitar Votación para Fotos" (`CG_voting`) esté configurado en SÍ.
-   **Usuarios No Registrados:** Si los invitados no pueden votar, verifique "Permitir Votación a Usuarios No Registrados" (`cg_unl_voting`).
-   **Conflictos de CSS:** A veces, el CSS del tema puede ocultar o distorsionar elementos del módulo. Use las herramientas de desarrollo de su navegador (F12) para inspeccionar el área y buscar estilos conflictivos.
-   **Errores de JavaScript:** Verifique la consola de su navegador (F12 > pestaña Consola) en busca de errores de JavaScript que puedan estar impidiendo que la funcionalidad de votación funcione.

**Q5: ¿Cómo traduzco el texto del módulo a otros idiomas?**
**A:**

-   Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
-   Seleccione "Traducciones de módulos instalados".
-   Elija su tema, el idioma al que desea traducir y luego seleccione "Galería de Fotos de Clientes" de la lista de módulos.
-   Luego podrá traducir todas las cadenas del front-office y back-office del módulo.
-   Recuerde guardar sus cambios y borrar la caché.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Galería de Fotos de Clientes sigue una arquitectura estándar de módulo de PrestaShop, aprovechando principalmente los Controladores Frontales para la interacción del usuario y las plantillas Smarty para la renderización. Se integra con varios hooks de visualización para incrustar las características de la galería en toda la tienda. Aunque no define explícitamente clases `ObjectModel` personalizadas en el inventario proporcionado, es probable que use `Configuration` para la configuración e interactúe directamente con la base de datos para el almacenamiento y la gestión de fotos/videos. Se utiliza AJAX para la carga dinámica de contenido y las interacciones como la votación.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores manejan todas las interacciones y el procesamiento de datos orientados al cliente para la galería.

-   **`customersgallery/controllers/front/ajax.php`**

    -   **Nombre de la Clase:** `CustomersGalleryAjaxModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador es la columna vertebral de las interacciones dinámicas sin recargas completas de página. Maneja las solicitudes AJAX para acciones como:
        -   Envío de nuevas fotos/videos.
        -   Procesamiento de votos (por ejemplo, calificaciones por estrellas).
        -   Carga de más elementos de la galería (paginación/desplazamiento infinito).
        -   Potencialmente acciones de moderación si un usuario no registrado sube y requiere aprobación.
        -   Devuelve respuestas JSON al JavaScript del lado del cliente.
-   **`customersgallery/controllers/front/gallery.php`**

    -   **Nombre de la Clase:** `CustomersGalleryGalleryModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador es responsable de mostrar la página principal de la galería de fotos y videos de clientes.
        -   Obtiene todas las fotos/videos aprobados de la base de datos.
        -   Aplica la lógica de paginación basada en la configuración del módulo (`CG_PAGINATION`).
        -   Prepara los datos para la plantilla `gallery.tpl`, incluyendo rutas de imagen, títulos, descripciones y datos de votación.
        -   Maneja la clasificación (por ejemplo, por más recientes, más populares).
-   **`customersgallery/controllers/front/index.php`**

    -   **Nombre de la Clase:** `CustomersGalleryIndexModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador podría servir como un punto de entrada predeterminado o un redirigidor para la sección de front-office del módulo. También podría usarse para una página de aterrizaje simple o para redirigir a la galería principal. En muchos módulos, `index.php` en un directorio de controlador frontal es un respaldo o una simple redirección a la función principal.
-   **`customersgallery/controllers/front/myphotos.php`**

    -   **Nombre de la Clase:** `CustomersGalleryMyPhotosModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador gestiona la sección "Mis Fotos" dentro de la cuenta de un cliente.
        -   Autentica al cliente que ha iniciado sesión.
        -   Recupera todas las fotos subidas por el cliente actual.
        -   Permite a los clientes ver, editar (por ejemplo, título, descripción) o eliminar sus propias publicaciones.
        -   Prepara los datos para la plantilla `my-photos.tpl`.
-   **`customersgallery/controllers/front/myvideos.php`**

    -   **Nombre de la Clase:** `CustomersGalleryMyVideosModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   **Responsabilidad:** Similar a `myphotos.php`, pero específicamente para gestionar videos subidos por el cliente actual.
        -   Autentica al cliente que ha iniciado sesión.
        -   Recupera todos los videos subidos por el cliente actual.
        -   Permite a los clientes ver, editar o eliminar sus propias publicaciones de video.
        -   Prepara los datos para la plantilla `my-videos-16.tpl`.

#### Controladores de Administración del Back-Office

El dossier del módulo no indica controladores de administración dedicados. Toda la configuración del back-office se maneja a través del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo probablemente gestiona sus datos directamente dentro del archivo `customersgallery.php` o utiliza métodos genéricos de interacción con la base de datos de PrestaShop.

-   **Almacenamiento de Datos:** Los metadatos de fotos y videos (rutas, títulos, IDs de usuario, IDs de producto, estado de aprobación, votos) probablemente se almacenan en tablas de base de datos personalizadas creadas durante la instalación del módulo. El archivo PHP principal del módulo (`customersgallery.php`) contendría las consultas SQL para estas tablas.

### 4.4 Activos JavaScript (`views/js/`)

-   **`customersgallery/js/customersgallery.js`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Este es probablemente el archivo JavaScript personalizado principal para la galería. Contendría:
        -   Detectores de eventos para subidas de fotos/videos (por ejemplo, envío de formulario, cambios de entrada de archivo).
        -   Llamadas AJAX a `ajax.php` para subidas, votación y carga de más contenido.
        -   Validación del lado del cliente para tipos y tamaños de archivo.
        -   Actualizaciones dinámicas de la visualización de la galería (por ejemplo, agregar nuevas fotos sin actualizar la página).
        -   Interacción con la biblioteca Fancybox para lightboxes de imágenes.
-   **`customersgallery/js/fancybox.js`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Una biblioteca de terceros (Fancybox) para crear lightboxes elegantes y responsivos para imágenes y multimedia. Este script habilita la funcionalidad de "clic para ampliar" para las fotos de la galería.
-   **`customersgallery/js/script.js`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Este podría ser un script de utilidad general o un script heredado. Podría contener:
        -   Funciones de ayuda para interacciones de la interfaz de usuario.
        -   Controladores de eventos adicionales no específicos de la lógica central de la galería.
        -   Potencialmente scripts relacionados con el mecanismo de votación u otros elementos interactivos.
-   **`customersgallery/lib/voucherengine/script.js`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Esto sugiere la integración con un "motor de vales" o un sistema de recompensas similar. Este script manejaría:
        -   Lógica para otorgar vales o descuentos al enviar fotos/videos con éxito (si `cg_contest` está habilitado o hay un sistema de recompensas similar).
        -   Llamadas AJAX para activar la generación o aplicación de vales.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`customersgallery/css/customersgallery.css`**

    -   **Alcance:** Front-office (estilo principal de la galería).
    -   **Detalle:** Contiene las reglas CSS principales para el diseño, la apariencia y la capacidad de respuesta de la galería de fotos de clientes, incluyendo:
        -   Diseños de cuadrícula para la visualización de fotos.
        -   Estilo para miniaturas, leyendas e información del usuario.
        -   Estilos para el formulario de subida y la paginación.
        -   Ajustes responsivos para diferentes tamaños de pantalla.
    -   **Selectores Clave:** `.customer-gallery-container`, `.gallery-item`, `.gallery-thumbnail`, `.upload-form`, `.pagination`.
-   **`customersgallery/css/fancybox.css`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Hoja de estilo para la biblioteca lightbox Fancybox, que controla la apariencia de las imágenes ampliadas, las flechas de navegación, el botón de cierre y la superposición.
    -   **Selectores Clave:** `.fancybox-container`, `.fancybox-image`, `.fancybox-caption`.
-   **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Estos son diferentes temas de color para el sistema de votación basado en estrellas (`CG_VOTE_STAR`). `star.css` es probablemente el estilo base, y los otros proporcionan anulaciones de color.
    -   **Selectores Clave:** `.star-rating`, `.star-rating-control`, `.star-rating-star`.
-   **`customersgallery/lib/voucherengine/ps16.css`**

    -   **Alcance:** Front-office.
    -   **Detalle:** Esta hoja de estilo es específicamente para la integración del "motor de vales", probablemente proporcionando estilo para cualquier elemento relacionado con la visualización o notificación de vales, potencialmente con anulaciones específicas para temas de PrestaShop 1.6.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas Personalizadas (`views/templates/custom/`)

Estas son probablemente formas o componentes específicos.

-   **`customersgallery/views/templates/custom/upload-form.tpl`**
    -   **Propósito:** Renderiza el formulario HTML para que los clientes suban fotos.
    -   **Variables:** Probablemente incluye campos para la entrada de archivos, título, descripción y potencialmente asociación de productos.
-   **`customersgallery/views/templates/custom/upload-form2.tpl`**
    -   **Propósito:** Podría ser una versión alternativa o actualizada del formulario de subida, posiblemente para subidas de video o un diseño diferente.

#### Plantillas del Front-Office (`views/templates/front/`)

Estas plantillas renderizan las páginas principales de la galería y el contenido específico del usuario.

-   **`customersgallery/views/templates/front/gallery.tpl`**
    -   **Propósito:** Plantilla principal para mostrar la galería de fotos y videos de clientes.
    -   **Variables:** Recorre los arrays `$photos` y `$videos`, mostrando miniaturas, títulos y elementos de votación. Incluye paginación.
-   **`customersgallery/views/templates/front/gallery2.tpl`**
    -   **Propósito:** Podría ser un diseño de galería alternativo o una vista específica para concursos.
-   **`customersgallery/views/templates/front/gallery3.tpl`**
    -   **Propósito:** Otro diseño de galería alternativo.
-   **`customersgallery/views/templates/front/menu.tpl`**
    -   **Propósito:** Renderiza un menú de navegación específico para la galería, potencialmente con enlaces a "Mis Fotos", "Mis Videos", "Subir", etc.
-   **`customersgallery/views/templates/front/my-photos.tpl`**
    -   **Propósito:** Muestra la lista de fotos subidas por el cliente actualmente conectado, con opciones para editar o eliminar.
    -   **Variables:** Array `$customer_photos`.
-   **`customersgallery/views/templates/front/my-videos-16.tpl`**
    -   **Propósito:** Muestra la lista de videos subidos por el cliente actualmente conectado, diseñado específicamente para la compatibilidad con PrestaShop 1.6.
    -   **Variables:** Array `$customer_videos`.
-   **`customersgallery/views/templates/front/video-upload.tpl`**
    -   **Propósito:** Renderiza un formulario específicamente para subir videos, distinto del formulario de subida de fotos.

#### Plantillas de Hook (`views/templates/hook/`)

Estas plantillas están diseñadas para ser renderizadas dentro de hooks específicos de PrestaShop.

-   **`customersgallery/views/templates/hook/column-link.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`
    -   **Propósito:** Renderiza un bloque en la columna izquierda o derecha con un enlace a la página principal de la galería o a algunas fotos recientes.
-   **`customersgallery/views/templates/hook/customer-my-account.tpl`**
    -   **Hook:** `displayCustomerAccount`
    -   **Propósito:** Añade un enlace o bloque dentro del panel de control de la cuenta del cliente, típicamente enlazando a "Mis Fotos" o "Mis Videos".
-   **`customersgallery/views/templates/hook/hookHome.tpl`**
    -   **Hook:** `displayHome`
    -   **Propósito:** Muestra un bloque de fotos de clientes recientes o populares en la página de inicio de la tienda.
    -   **Variables:** Array `$homepage_photos`.
-   **`customersgallery/views/templates/hook/my-account.tpl`**
    -   **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
    -   **Propósito:** Añade un enlace a "Mis Fotos" dentro del bloque "Mi Cuenta", a menudo encontrado en las columnas laterales o el pie de página.
-   **`customersgallery/views/templates/hook/productfooter.tpl`**
    -   **Hook:** `displayProductFooter`
    -   **Propósito:** Renderiza un bloque de fotos de clientes relacionadas con el producto actual en el pie de página de la página del producto.
-   **`customersgallery/views/templates/hook/tab.tpl`**
    -   **Hook:** `displayProductTab`, `displayProductExtraContent`
    -   **Propósito:** Renderiza el encabezado de la pestaña "Fotos de Clientes" en una página de producto.
-   **`customersgallery/views/templates/hook/tabContents.tpl`**
    -   **Hook:** `displayProductTabContent`, `displayProductExtraContent`
    -   **Propósito:** Renderiza el contenido real (la galería de fotos) dentro de la pestaña "Fotos de Clientes" en una página de producto.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo probablemente crea tablas personalizadas durante la instalación. Basado en la funcionalidad, estas incluirían:

-   **`ps_customersgallery_photos`**:

    -   `id_photo` (CLAVE PRIMARIA, INT)
    -   `id_customer` (INT, FK a `ps_customer`)
    -   `id_product` (INT, FK a `ps_product`, NULO)
    -   `filename` (VARCHAR, ruta al archivo de imagen)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT, para el estado de moderación)
    -   `votes` (INT, votos totales)
    -   `rating` (DECIMAL, calificación promedio)
-   **`ps_customersgallery_videos`**:

    -   `id_video` (CLAVE PRIMARIA, INT)
    -   `id_customer` (INT, FK a `ps_customer`)
    -   `id_product` (INT, FK a `ps_product`, NULO)
    -   `url` (VARCHAR, para enlaces de video externos como YouTube/Vimeo)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT)
-   **`ps_customersgallery_votes`**:

    -   `id_vote` (CLAVE PRIMARIA, INT)
    -   `id_photo` (INT, FK a `ps_customersgallery_photos`)
    -   `id_customer` (INT, FK a `ps_customer`, NULO para votos no registrados)
    -   `ip_address` (VARCHAR, para votos no registrados y prevención de abuso)
    -   `vote_value` (INT, por ejemplo, 1-5 para estrellas)
    -   `date_add` (DATETIME)
-   **`ps_configuration`**: La configuración del módulo (por ejemplo, `CG_ALLOW_JPEG`, `CG_MAX_FILE_SIZE`, `CG_PAGINATION`) se almacena aquí.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayProductExtraContent` | Renderiza contenido adicional en la página del producto, a menudo utilizado para pestañas. | Muestra la pestaña "Fotos de Clientes" y su contenido en las páginas de productos. |
| `displayRightColumnProduct` | Renderiza contenido en la columna derecha de una página de producto. | Muestra un bloque de fotos de clientes específicas del producto en la columna derecha. |
| `displayCustomerAccount` | Renderiza contenido dentro del panel de control "Mi Cuenta" del cliente. | Añade un enlace o bloque a "Mis Fotos" y "Mis Videos" para el cliente que ha iniciado sesión. |
| `displayRightColumn` | Renderiza contenido en la columna derecha de las páginas generales de la tienda. | Muestra un bloque de fotos recientes de clientes en la columna derecha. |
| `displayMyAccountBlockFooter` | Renderiza contenido en el pie de página del bloque "Mi Cuenta". | Añade un enlace a "Mis Fotos" en el bloque "Mi Cuenta", a menudo en el pie de página. |
| `displayProductFooter` | Renderiza contenido en el área del pie de página de una página de producto. | Muestra un bloque de fotos de clientes específicas del producto en el pie de página del producto. |
| `displayProductTabContent` | Renderiza el contenido de una pestaña de producto. | Muestra el contenido de la galería dentro de la pestaña "Fotos de Clientes" en las páginas de productos. |
| `displayLeftColumnProduct` | Renderiza contenido en la columna izquierda de una página de producto. | Muestra un bloque de fotos de clientes específicas del producto en la columna izquierda. |
| `displayLeftColumn` | Renderiza contenido en la columna izquierda de las páginas generales de la tienda. | Muestra un bloque de fotos recientes de clientes en la columna izquierda. |
| `displayHome` | Renderiza contenido en la página de inicio de la tienda. | Muestra un bloque de fotos de clientes recientes o populares en la página de inicio. |
| `displayHeader` | Renderiza contenido en la sección `<head>` de todas las páginas. | Inyecta archivos CSS y JavaScript requeridos por el módulo en toda la tienda. |
| `displayMyAccountBlock` | Renderiza contenido dentro del bloque "Mi Cuenta" (por ejemplo, en columnas laterales). | Añade un enlace a "Mis Fotos" en el bloque "Mi Cuenta". |
| `displayProductTab` | Renderiza el encabezado de la pestaña para una pestaña de producto. | Muestra el título de la pestaña "Fotos de Clientes" en las páginas de productos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de sus módulos de PrestaShop.
