---
title: "Fotos de productos de clientes - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Fotos de productos de clientes' de MyPresta.eu."
sidebar:
  label: "Fotos de productos de clientes - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customer product photos en MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-product-photos.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/customer-product-photos/)
>
> ---


# Fotos de productos de clientes

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo "Fotos de productos de clientes". Aquí encontrará una variedad de ajustes para controlar cómo se comporta y aparece el módulo en su tienda.

#### Ajustes generales

- **¿Permitir archivos JPEG?**
  - **Qué hace este ajuste:** Determina si los clientes pueden subir imágenes en formato JPEG.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden subir archivos `.jpg` o `.jpeg`.
    - *Cuando está deshabilitado:* Los archivos JPEG serán rechazados durante la carga.
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo del comerciante:** La mayoría de las fotos se toman en JPEG. Mantener esto habilitado garantiza la máxima compatibilidad para las cargas de los clientes.
- **¿Permitir archivos GIF?**
  - **Qué hace este ajuste:** Determina si los clientes pueden subir imágenes en formato GIF.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden subir archivos `.gif`.
    - *Cuando está deshabilitado:* Los archivos GIF serán rechazados durante la carga.
  - **Valor recomendado:** SÍ (a menos que tenga una razón específica para no permitir imágenes animadas)
  - **Escenario/ejemplo del comerciante:** Los GIF pueden ser útiles para mostrar animaciones cortas de un producto, pero también pueden ser archivos más grandes. Habilítelo si desea admitirlos.
- **¿Permitir archivos PNG?**
  - **Qué hace este ajuste:** Determina si los clientes pueden subir imágenes en formato PNG.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden subir archivos `.png`.
    - *Cuando está deshabilitado:* Los archivos PNG serán rechazados durante la carga.
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo del comerciante:** Los PNG son excelentes para imágenes con transparencia o gráficos nítidos. Es un formato común, por lo que habilitarlo es generalmente una buena idea.
- **¿Permitir archivos BMP?**
  - **Qué hace este ajuste:** Determina si los clientes pueden subir imágenes en formato BMP.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden subir archivos `.bmp`.
    - *Cuando está deshabilitado:* Los archivos BMP serán rechazados durante la carga.
  - **Valor recomendado:** NO (a menos que sea específicamente requerido)
  - **Escenario/ejemplo del comerciante:** Los archivos BMP suelen ser muy grandes y sin comprimir, lo que los hace inadecuados para uso web. Deshabilitar esto ayuda a mantener su galería eficiente.
- **¿Permitir que los clientes no registrados suban fotos?**
  - **Qué hace este ajuste:** Controla si los visitantes que no han iniciado sesión en una cuenta de cliente pueden subir fotos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los invitados pueden subir fotos. Es posible que se les pida una dirección de correo electrónico o un nombre.
    - *Cuando está deshabilitado:* Solo los clientes registrados y con sesión iniciada pueden subir fotos.
  - **Valor recomendado:** SÍ (si desea la máxima generación de contenido), NO (si desea vincular el contenido a cuentas de cliente específicas)
  - **Escenario/ejemplo del comerciante:** Si desea maximizar el contenido generado por el usuario, permitir a los invitados es beneficioso. Si desea rastrear quién sube qué y potencialmente recompensarlos, requiera el inicio de sesión.
- **Tamaño máximo de archivo (en MB)**
  - **Qué hace este ajuste:** Establece el límite superior para el tamaño de un archivo de imagen que un cliente puede subir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 5:* Los clientes no pueden subir archivos de más de 5 MB.
    - *Cuando se establece en 0:* Sin límite (aunque los límites del servidor PHP seguirán aplicándose).
  - **Valor recomendado:** 2-5 MB
  - **Escenario/ejemplo del comerciante:** Un límite razonable evita que los clientes suban archivos excesivamente grandes que podrían ralentizar su sitio o consumir demasiado espacio en el servidor. 2-5 MB suele ser suficiente para imágenes web de alta calidad.
- **Altura de la miniatura (px)**
  - **Qué hace este ajuste:** Define la altura de las imágenes en miniatura generadas para la galería.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 100:* Todas las miniaturas tendrán 100 píxeles de alto.
    - *Cuando se establece en 200:* Todas las miniaturas tendrán 200 píxeles de alto.
  - **Valor recomendado:** 150-250px (ajuste según el diseño de su tema)
  - **Escenario/ejemplo del comerciante:** Los tamaños de miniatura consistentes garantizan un diseño de galería limpio y organizado. Ajuste esto para que se adapte a la estética de su tema.
- **Ancho de la miniatura (px)**
  - **Qué hace este ajuste:** Define el ancho de las imágenes en miniatura generadas para la galería.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 100:* Todas las miniaturas tendrán 100 píxeles de ancho.
    - *Cuando se establece en 200:* Todas las miniaturas tendrán 200 píxeles de ancho.
  - **Valor recomendado:** 150-250px (ajuste según el diseño de su tema)
  - **Escenario/ejemplo del comerciante:** Similar a la altura, un ancho consistente ayuda a mantener una galería visualmente atractiva.
- **Fotos por página en la galería** (CG\_PAGINATION)
  - **Qué hace este ajuste:** Controla cuántas fotos de clientes se muestran en una sola página en la vista de galería principal antes de que se active la paginación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 12:* La galería mostrará 12 fotos por página.
    - *Cuando se establece en 24:* La galería mostrará 24 fotos por página.
  - **Valor recomendado:** 12-24
  - **Escenario/ejemplo del comerciante:** Un número moderado evita abrumar al usuario y mantiene los tiempos de carga de la página razonables. Demasiadas pocas significa más clics, demasiadas pueden ralentizar la página.
- **¿Habilitar votación para fotos?** (CG\_voting)
  - **Qué hace este ajuste:** Permite a los clientes votar las fotos subidas, normalmente con un simple "me gusta" o una calificación por estrellas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los controles de votación (por ejemplo, estrellas, pulgares arriba) aparecerán junto a cada foto.
    - *Cuando está deshabilitado:* No se mostrarán opciones de votación.
  - **Valor recomendado:** SÍ (fomenta la interacción)
  - **Escenario/ejemplo del comerciante:** Habilitar la votación puede resaltar las fotos populares y fomentar un mayor compromiso de su comunidad.
- **¿Permitir que los clientes no registrados voten?** (cg\_unl\_voting)
  - **Qué hace este ajuste:** Determina si los visitantes que no han iniciado sesión pueden emitir votos en las fotos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los invitados pueden votar las fotos.
    - *Cuando está deshabilitado:* Solo los clientes registrados pueden votar.
  - **Valor recomendado:** NO (para evitar el spam/votación de bots y garantizar un compromiso más significativo)
  - **Escenario/ejemplo del comerciante:** Restringir la votación a los usuarios registrados ayuda a garantizar que los votos provengan de clientes reales y reduce el riesgo de manipulación.
- **Estilo de votación** (CG\_VOTE\_STAR, CGV\_voting)
  - **Qué hace este ajuste:** Selecciona el estilo visual para el mecanismo de votación (por ejemplo, diferentes colores de estrellas).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 'Estrellas negras':* La votación usará iconos de estrellas negras.
    - *Cuando se establece en 'Estrellas doradas':* La votación usará iconos de estrellas doradas.
  - **Valor recomendado:** Estrellas doradas (a menudo asociadas con la calidad y las reseñas)
  - **Escenario/ejemplo del comerciante:** Elija un estilo que mejor se adapte a la marca y la estética de su tienda.
- **¿Habilitar modo concurso?** (cg\_contest)
  - **Qué hace este ajuste:** Activa funciones que admiten la ejecución de un concurso de fotos, como la visualización de ganadores o reglas de concurso específicas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Pueden aparecer opciones o pantallas adicionales relacionadas con el concurso.
    - *Cuando está deshabilitado:* Comportamiento de galería estándar.
  - **Valor recomendado:** NO (a menos que esté ejecutando activamente un concurso)
  - **Escenario/ejemplo del comerciante:** Si planea ejecutar un concurso de "la mejor foto", habilite esto para aprovechar las funciones de concurso del módulo.

#### Ubicaciones de visualización en el Front-Office

Estos ajustes controlan dónde aparecen la galería de fotos de clientes y las opciones de carga en su tienda.

- **¿Mostrar formulario de carga en la página del producto?** (CG\_FUPLOADON)
  - **Qué hace este ajuste:** Determina si el formulario de carga de fotos es directamente visible en la página del producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán un formulario para subir fotos directamente en la página del producto.
    - *Cuando está deshabilitado:* El formulario de carga no aparecerá en la página del producto; los clientes podrían necesitar ir a su cuenta o a una página de galería dedicada para subir.
  - **Valor recomendado:** SÍ (para máxima comodidad y generación de contenido)
  - **Escenario/ejemplo del comerciante:** Hacer que el formulario de carga sea fácilmente accesible en la página del producto anima a más clientes a compartir sus fotos justo después de ver el producto.
- **¿Mostrar galería en la página del producto como una pestaña?** (CG\_PRODUCTTAB, cg\_productTabM)
  - **Qué hace este ajuste:** Integra la galería de fotos de clientes como una nueva pestaña en la página del producto (por ejemplo, junto a "Descripción" o "Ficha técnica").
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una nueva pestaña en las páginas de productos, mostrando fotos de clientes para ese producto específico.
    - *Cuando está deshabilitado:* La galería no aparecerá como una pestaña.
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo del comerciante:** Esta es una forma muy prominente y efectiva de mostrar contenido generado por el usuario, haciéndolo fácilmente descubrible para los compradores.
- **¿Mostrar galería en la página del producto en el pie de página?** (CG\_PRODUCTFOOTER)
  - **Qué hace este ajuste:** Muestra una sección de fotos de clientes en el área del pie de página de la página del producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un bloque de fotos de clientes debajo del contenido principal del producto.
    - *Cuando está deshabilitado:* No aparecerán fotos en el pie de página del producto.
  - **Valor recomendado:** SÍ (como un punto de visualización adicional)
  - **Escenario/ejemplo del comerciante:** Esto proporciona otra oportunidad para mostrar fotos de clientes sin saturar el área de información principal del producto.
- **¿Mostrar galería en la cuenta del cliente?** (CG\_CUSTOMERACCOUNT, CG\_CUSTOMERACCOUNTV)
  - **Qué hace este ajuste:** Crea una sección dedicada "Mis fotos" dentro del área de cuenta personal del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes registrados verán un nuevo enlace y página en su cuenta para gestionar sus fotos subidas.
    - *Cuando está deshabilitado:* Los clientes no pueden gestionar sus fotos desde su cuenta.
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo del comerciante:** Es esencial para que los clientes vean y gestionen sus contribuciones, fomentando un sentido de propiedad y comunidad.
- **¿Mostrar enlace a la galería en el bloque "Mi cuenta"?** (CG\_MYACCOUNTBLOCK, CG\_MYACCOUNTBLOCKV)
  - **Qué hace este ajuste:** Añade un enlace a la sección "Mis fotos" (o a la galería principal) en el bloque "Mi cuenta", que a menudo se encuentra en la columna izquierda o derecha o en el pie de página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un enlace rápido para los usuarios registrados.
    - *Cuando está deshabilitado:* El enlace no estará presente en el bloque.
  - **Valor recomendado:** SÍ (para una fácil navegación)
  - **Escenario/ejemplo del comerciante:** Facilita mucho a los clientes el acceso a su galería de fotos o la carga de nuevas fotos desde casi cualquier página.
- **¿Mostrar galería en la columna derecha?** (CG\_RIGHTCOL)
  - **Qué hace este ajuste:** Muestra un bloque de fotos de clientes en la columna derecha de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un bloque dinámico de fotos en la barra lateral derecha.
    - *Cuando está deshabilitado:* No aparecerán fotos en la columna derecha.
  - **Valor recomendado:** NO (puede ser una distracción, considere solo si su tema tiene espacio suficiente)
  - **Escenario/ejemplo del comerciante:** Útil si tiene un diseño amplio y desea mostrar constantemente contenido de clientes, pero a veces puede saturar la página.
- **¿Mostrar galería en la columna izquierda?** (CG\_LEFTCOL)
  - **Qué hace este ajuste:** Muestra un bloque de fotos de clientes en la columna izquierda de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un bloque dinámico de fotos en la barra lateral izquierda.
    - *Cuando está deshabilitado:* No aparecerán fotos en la columna izquierda.
  - **Valor recomendado:** NO (similar a la columna derecha, úselo con moderación)
  - **Escenario/ejemplo del comerciante:** Similar a la columna derecha, úselo si el diseño de su tema lo permite sin comprometer la legibilidad.
- **¿Mostrar galería en la página de inicio?** (CG\_GALLERY, cg\_hpg\_nb, cg\_hpg\_o)
  - **Qué hace este ajuste:** Muestra una selección de fotos de clientes directamente en la página de inicio de su tienda. También puede tener opciones para controlar el número de fotos (cg\_hpg\_nb) y su orden (cg\_hpg\_o).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una sección con fotos de clientes en la página de inicio.
    - *Cuando está deshabilitado:* No se mostrarán fotos de clientes en la página de inicio.
  - **Valor recomendado:** SÍ (muy recomendado para el compromiso)
  - **Escenario/ejemplo del comerciante:** La página de inicio es un espacio privilegiado. Mostrar fotos de clientes aquí transmite inmediatamente confianza y comunidad a los nuevos visitantes.
- **¿Excluir productos específicos de la galería?** (cg\_excludeproduct)
  - **Qué hace este ajuste:** Le permite especificar los ID de productos que no deben mostrar fotos de clientes ni permitir su carga.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce el ID de producto 123:* El producto 123 no mostrará fotos de clientes y las cargas para él estarán deshabilitadas.
    - *Cuando se deja vacío:* Todos los productos son elegibles para fotos de clientes.
  - **Valor recomendado:** Dejar vacío a menos que tenga productos sensibles o no visuales.
  - **Escenario/ejemplo del comerciante:** Si vende productos o servicios digitales que no tienen un componente visual, o productos para los que no desea contenido generado por el usuario, puede excluirlos aquí.

#### Notificaciones y actualizaciones

- **¿Habilitar notificaciones por correo electrónico para nuevas cargas?** (CG\_NTF)
  - **Qué hace este ajuste:** Envía una notificación por correo electrónico al administrador de la tienda cada vez que se sube una nueva foto de cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Recibirá un correo electrónico por cada nueva carga, lo que le permitirá moderar rápidamente.
    - *Cuando está deshabilitado:* No se enviarán notificaciones por correo electrónico.
  - **Valor recomendado:** SÍ (esencial para la moderación y el control de calidad)
  - **Escenario/ejemplo del comerciante:** Mantenerse al tanto de las nuevas cargas le ayuda a garantizar que todo el contenido sea apropiado y de alta calidad antes de que sea ampliamente visible.
- **Actualizaciones de MyPresta.eu** (mypresta\_updates, update\_, updatev\_)
  - **Qué hace este ajuste:** Este es un ajuste estándar en los módulos de MyPresta.eu para buscar actualizaciones disponibles.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo buscará periódicamente nuevas versiones en MyPresta.eu.
    - *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente.
  - **Valor recomendado:** SÍ (manténgase siempre actualizado para seguridad y funciones)
  - **Escenario/ejemplo del comerciante:** Mantener esto habilitado garantiza que se le notifique sobre nuevas funciones, correcciones de errores y parches de seguridad, lo que ayuda a que su tienda se mantenga actualizada y segura.

#### Ajustes internos/avanzados (Normalmente dejar como predeterminado)

- **CG\_LAST\_TAB**: Ajuste interno para recordar la última pestaña activa en la configuración del módulo.
- **cg\_altered1, cg\_altered2**: Banderas internas, generalmente relacionadas con actualizaciones del módulo o migraciones de datos.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | ¿Permitir archivos JPEG? | SÍ | Permite a los clientes subir imágenes JPEG. |
| Configuración del módulo | ¿Permitir archivos GIF? | SÍ | Permite a los clientes subir imágenes GIF. |
| Configuración del módulo | ¿Permitir archivos PNG? | SÍ | Permite a los clientes subir imágenes PNG. |
| Configuración del módulo | ¿Permitir archivos BMP? | NO | No permite imágenes BMP grandes y sin comprimir. |
| Configuración del módulo | ¿Permitir que los clientes no registrados suban fotos? | SÍ / NO (Elección del comerciante) | Controla las cargas de invitados. |
| Configuración del módulo | Tamaño máximo de archivo (en MB) | 2-5 MB | Limita el tamaño de carga para evitar archivos grandes. |
| Configuración del módulo | Altura de la miniatura (px) | 150-250px | Establece una altura consistente para las miniaturas de la galería. |
| Configuración del módulo | Ancho de la miniatura (px) | 150-250px | Establece un ancho consistente para las miniaturas de la galería. |
| Configuración del módulo | Fotos por página en la galería | 12-24 | Controla la paginación de la galería principal. |
| Configuración del módulo | ¿Habilitar votación para fotos? | SÍ | Permite a los clientes votar las fotos. |
| Configuración del módulo | ¿Permitir que los clientes no registrados voten? | NO | Evita el spam/votación de bots. |
| Configuración del módulo | Estilo de votación | Estrellas doradas | Establece el estilo visual de los iconos de votación. |
| Configuración del módulo | ¿Habilitar modo concurso? | NO | Activa funciones específicas del concurso. |
| Configuración del módulo | ¿Mostrar formulario de carga en la página del producto? | SÍ | Muestra el formulario de carga directamente en las páginas de productos. |
| Configuración del módulo | ¿Mostrar galería en la página del producto como una pestaña? | SÍ | Añade una pestaña dedicada para fotos en las páginas de productos. |
| Configuración del módulo | ¿Mostrar galería en la página del producto en el pie de página? | SÍ | Muestra fotos debajo del contenido del producto. |
| Configuración del módulo | ¿Mostrar galería en la cuenta del cliente? | SÍ | Crea una sección "Mis fotos" en las cuentas de los clientes. |
| Configuración del módulo | ¿Mostrar enlace a la galería en el bloque "Mi cuenta"? | SÍ | Añade un enlace rápido a la galería en el bloque Mi cuenta. |
| Configuración del módulo | ¿Mostrar galería en la columna derecha? | NO | Muestra fotos en la barra lateral derecha. |
| Configuración del módulo | ¿Mostrar galería en la columna izquierda? | NO | Muestra fotos en la barra lateral izquierda. |
| Configuración del módulo | ¿Mostrar galería en la página de inicio? | SÍ | Muestra fotos en la página de inicio de la tienda. |
| Configuración del módulo | ¿Excluir productos específicos de la galería? | Dejar vacío | Evita fotos para productos especificados. |
| Configuración del módulo | ¿Habilitar notificaciones por correo electrónico para nuevas cargas? | SÍ | Envía un correo electrónico al administrador sobre nuevas cargas de fotos. |
| Configuración del módulo | Actualizaciones de MyPresta.eu | SÍ | Habilita las comprobaciones automáticas de actualizaciones. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis fotos de clientes no aparecen después de la carga, o la galería parece vacía.**
**R1:**

-   **Verifique la configuración del módulo:** Asegúrese de que las opciones de visualización (por ejemplo, "¿Mostrar galería en la página del producto como una pestaña?", "¿Mostrar galería en la página de inicio?") estén habilitadas en la configuración del módulo.
-   **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" y "Borrar caché" si son opciones separadas). Esto a menudo resuelve problemas de visualización.
-   **Moderación de imágenes:** Algunos módulos tienen un proceso de aprobación. Verifique si hay una sección de administración (aunque este módulo no tiene un controlador de administración dedicado, podría tener un estado de aprobación interno) donde las fotos deben ser aprobadas antes de publicarse.
-   **Permisos de archivo:** Asegúrese de que su carpeta `img/customersgallery` (o una ruta similar donde se almacenan las imágenes) tenga los permisos de escritura correctos (generalmente 755 o 775). Su proveedor de alojamiento puede ayudarle con esto.

**P2: Los clientes tienen problemas para subir fotos, o reciben un mensaje de error.**
**R2:**

-   **Verifique el tipo de archivo y los límites de tamaño:** Revise los ajustes "¿Permitir archivos JPEG/GIF/PNG/BMP?" y "Tamaño máximo de archivo (en MB)" en la configuración del módulo. Asegúrese de que el archivo del cliente coincida con los tipos permitidos y esté dentro del límite de tamaño.
-   **Límites de PHP del servidor:** Incluso si el módulo permite un tamaño de archivo grande, la configuración de PHP de su servidor (por ejemplo, `upload_max_filesize`, `post_max_size` en `php.ini`) podría estar imponiendo un límite más estricto. Póngase en contacto con su proveedor de alojamiento para verificar y, si es necesario, aumentar estos límites.
-   **Compatibilidad del navegador:** Pida al cliente que pruebe con un navegador diferente o que borre la caché de su navegador.
-   **Errores de JavaScript:** Abra la consola de desarrollador de su navegador (F12) y busque cualquier error de JavaScript durante el proceso de carga. Esto podría indicar un conflicto con otro módulo o tema.

**P3: Las fotos de los clientes se ven distorsionadas o con un tamaño incorrecto en la galería.**
**R3:**

-   **Dimensiones de las miniaturas:** Ajuste los ajustes "Altura de la miniatura (px)" y "Ancho de la miniatura (px)" en la configuración del módulo. Experimente con diferentes valores para encontrar lo que mejor se adapte a su tema. Recuerde borrar la caché de PrestaShop después de realizar cambios.
-   **Conflictos de CSS:** El CSS de su tema podría estar anulando el estilo del módulo. Utilice las herramientas de desarrollador de su navegador (F12) para inspeccionar los elementos e identificar cualquier regla CSS conflictiva. Es posible que necesite un webmaster para añadir CSS personalizado a su tema para corregir esto.

**P4: El enlace "Mis fotos" no aparece en la cuenta del cliente o en el bloque "Mi cuenta".**
**R4:**

-   **Enganche del módulo:** Asegúrese de que el módulo esté correctamente enganchado a `displayCustomerAccount` y `displayMyAccountBlock` (o `displayMyAccountBlockFooter` según su tema). Puede verificar esto en **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores) y buscar el módulo. Si no está enganchado, intente reinstalar el módulo o engancharlo manualmente.
-   **Configuración del módulo:** Verifique que "¿Mostrar galería en la cuenta del cliente?" y "¿Mostrar enlace a la galería en el bloque 'Mi cuenta'?" estén habilitados en la configuración del módulo.
-   **Inicio de sesión del cliente:** El enlace "Mis fotos" solo es visible para los clientes que han iniciado sesión. Asegúrese de haber iniciado sesión al realizar la prueba.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Fotos de productos de clientes", diseñada para desarrolladores y webmasters que necesitan comprender su funcionamiento interno, personalizar su comportamiento o solucionar problemas avanzados.

### 4.1 Descripción general de la arquitectura

El módulo "Fotos de productos de clientes" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los Controladores Frontales para la interacción del usuario y las plantillas Smarty para la renderización. Utiliza la clase principal del módulo (`customersgallery.php`) para la gestión de la configuración y el registro de hooks. Aunque no extiende `ObjectModel` para sus datos principales, interactúa directamente con la base de datos para almacenar metadatos de fotos y se basa en el sistema de archivos de PrestaShop para el almacenamiento de imágenes. AJAX se utiliza en gran medida para la carga dinámica de contenido y la carga de fotos, proporcionando una experiencia de usuario fluida sin recargas completas de la página.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan todas las interacciones orientadas al cliente, incluida la visualización de galerías, la gestión de fotos de usuario y el procesamiento de solicitudes AJAX.

-   **`controllers/front/ajax.php`**
    -   **Nombre de la clase:** `CustomersGalleryAjaxModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este es el punto final principal para todas las operaciones asíncronas (AJAX). Maneja:
        -   Carga de fotos desde la página del producto o la cuenta del cliente.
        -   Acciones de votación (dar "me gusta"/calificar fotos).
        -   Potencialmente solicitudes de eliminación o moderación de imágenes desde la sección "Mis fotos" del cliente.
        -   Devuelve respuestas JSON que indican éxito o fracaso, junto con datos relevantes.
-   **`controllers/front/gallery.php`**
    -   **Nombre de la clase:** `CustomersGalleryGalleryModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Renderiza la página principal y dedicada de la galería de fotos de clientes. Esta página suele mostrar todas las fotos de clientes aprobadas, posiblemente con opciones de paginación y filtrado. Obtiene datos de fotos de la base de datos y los asigna a la plantilla `gallery.tpl`.
-   **`controllers/front/index.php`**
    -   **Nombre de la clase:** `CustomersGalleryIndexModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador probablemente sirve como un punto de entrada predeterminado o de respaldo para las rutas de front-office del módulo. Podría redirigir a la galería principal o al controlador `myphotos` si se accede directamente sin parámetros específicos.
-   **`controllers/front/myphotos.php`**
    -   **Nombre de la clase:** `CustomersGalleryMyPhotosModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Maneja la sección "Mis fotos" dentro de la cuenta del cliente. Muestra las fotos subidas por el cliente actualmente conectado, les permite gestionar (por ejemplo, eliminar) sus propias fotos y, potencialmente, proporciona una interfaz de carga. Requiere autenticación del cliente.
-   **`controllers/front/myvideos.php`**
    -   **Nombre de la clase:** `CustomersGalleryMyVideosModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Aunque el nombre del módulo es "Fotos de productos de clientes", este controlador sugiere una característica potencial (o planificada) para la carga de videos de clientes. Probablemente funcionaría de manera similar a `myphotos.php` pero para contenido de video.

#### Controladores de administración de Back-Office

El módulo no tiene ningún controlador de administración dedicado. Toda la configuración se gestiona a través del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no parece definir clases personalizadas que extiendan `ObjectModel` en un directorio `classes/` dedicado. Toda la lógica central para la interacción con la base de datos, el procesamiento de imágenes y las reglas de negocio probablemente está encapsulada dentro del archivo principal `customersgallery.php` y los controladores frontales. Esto significa que las operaciones de la base de datos se manejan directamente a través de llamadas a `Db::getInstance()`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`customersgallery/js/customersgallery.js`**
    -   **Alcance:** Front-office
    -   **Detalles:** Este es el JavaScript personalizado principal para el módulo. Probablemente maneja:
        -   Llamadas AJAX para la carga de fotos (por ejemplo, vinculación a envíos de formularios).
        -   Llamadas AJAX para mecanismos de votación.
        -   Carga dinámica de contenido de la galería.
        -   Validación del lado del cliente para tipos y tamaños de archivo antes de la carga.
        -   Interacción con la biblioteca Fancybox para lightboxes de imágenes.
        -   Detectores de eventos para paginación, filtrado y otras interacciones de la galería.
-   **`customersgallery/js/fancybox.js`**
    -   **Alcance:** Front-office
    -   **Detalles:** Esta es una biblioteca de terceros (Fancybox) utilizada para mostrar imágenes en una superposición de lightbox elegante y responsiva cuando un usuario hace clic en una miniatura. Maneja el zoom de la imagen, la navegación entre las imágenes de la galería y la presentación modal.
-   **`customersgallery/js/script.js`**
    -   **Alcance:** Front-office
    -   **Detalles:** Este podría ser un script complementario, potencialmente para mejoras generales de la interfaz de usuario, animaciones específicas o manejo de eventos adicionales no cubiertos por `customersgallery.js`. También podría contener rutinas de inicialización para otros componentes JS.
-   **`customersgallery/lib/voucherengine/script.js`**
    -   **Alcance:** Front-office (potencialmente)
    -   **Detalles:** La presencia de `voucherengine` sugiere una posible integración o una característica separada para generar/gestionar vales, posiblemente como recompensa por la carga de fotos o la participación en concursos. Este script manejaría la lógica del lado del cliente para dicho sistema.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`customersgallery/css/customersgallery.css`**
    -   **Alcance:** Estilo del cliente de Front-office
    -   **Detalles:** Esta es la hoja de estilo principal para los componentes de front-office del módulo. Estiliza:
        -   El diseño de la galería de fotos (cuadrícula, flexbox).
        -   Contenedores de fotos individuales y miniaturas.
        -   Formularios y botones de carga.
        -   Controles de paginación.
        -   Elementos de votación (si no se manejan con CSS de estrellas específico).
        -   Ajustes responsivos para diferentes tamaños de pantalla.
    -   **Selectores de clase CSS clave:** `.customer-photo-gallery`, `.cg-item`, `.cg-thumbnail`, `.cg-upload-form`, `.cg-vote-stars`
-   **`customersgallery/css/fancybox.css`**
    -   **Alcance:** Estilo del cliente de Front-office
    -   **Detalles:** Hoja de estilo para la biblioteca lightbox Fancybox, asegurando que la superposición de la imagen, las flechas de navegación, el botón de cierre y los subtítulos sean visualmente consistentes y atractivos.
-   **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**
    -   **Alcance:** Estilo del cliente de Front-office
    -   **Detalles:** Estas son hojas de estilo específicas para el sistema de votación basado en estrellas. Cada archivo proporciona un esquema de color o estilo visual diferente para los iconos de estrellas, lo que permite al comerciante elegir un diseño que coincida con su tema. `star.css` es probablemente el estilo base, y los demás proporcionan anulaciones de color.
-   **`customersgallery/lib/voucherengine/ps16.css`**
    -   **Alcance:** Front-office (potencialmente)
    -   **Detalles:** Esta hoja de estilo, que se encuentra dentro del directorio `voucherengine`, sugiere un estilo específicamente para las funciones relacionadas con los vales, potencialmente optimizado para temas de PrestaShop 1.6, pero probablemente compatible o adaptable para versiones más nuevas.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

Estas plantillas están diseñadas para ser renderizadas cuando se ejecutan hooks específicos de PrestaShop, integrando el contenido del módulo en varias partes de la tienda.

-   **`customersgallery/views/templates/hook/column-link.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`
    -   **Salida:** Un enlace o bloque que dirige a los usuarios a la galería principal de fotos de clientes o a su sección "Mis fotos", normalmente colocado en las barras laterales.
-   **`customersgallery/views/templates/hook/customer-my-account.tpl`**
    -   **Hook:** `displayCustomerAccount`
    -   **Salida:** Un enlace o bloque dentro de la página "Mi cuenta" del cliente, que lleva a su sección dedicada "Mis fotos".
-   **`customersgallery/views/templates/hook/hookHome.tpl`**
    -   **Hook:** `displayHome`
    -   **Salida:** Un bloque o sección que muestra una selección de fotos de clientes en la página de inicio de la tienda, a menudo con las cargas más recientes o populares.
-   **`customersgallery/views/templates/hook/my-account.tpl`**
    -   **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
    -   **Salida:** Un enlace a la sección "Mis fotos", integrado en el bloque estándar "Mi cuenta" que aparece en las columnas o el pie de página para los usuarios registrados.
-   **`customersgallery/views/templates/hook/productfooter.tpl`**
    -   **Hook:** `displayProductFooter`, `displayProductExtraContent`
    -   **Salida:** Una sección que muestra fotos de clientes para el producto actual, ubicada debajo del contenido principal del producto en la página del producto.
-   **`customersgallery/views/templates/hook/tab.tpl`**
    -   **Hook:** `displayProductTab`
    -   **Salida:** El HTML para un nuevo encabezado de pestaña (por ejemplo, "Fotos de clientes") que aparece en la página del producto.
-   **`customersgallery/views/templates/hook/tabContents.tpl`**
    -   **Hook:** `displayProductTabContent`
    -   **Salida:** El contenido real que se muestra cuando la pestaña "Fotos de clientes" está activa en la página del producto, mostrando la galería y potencialmente el formulario de carga para ese producto específico.

#### Plantillas personalizadas (`views/templates/custom/`)

Estas plantillas se utilizan probablemente para formularios específicos o partes del proceso de carga.

-   **`customersgallery/views/templates/custom/upload-form.tpl`**
    -   **Propósito:** Renderiza el formulario HTML que los clientes utilizan para subir sus fotos de productos. Esta podría ser una versión más simple o una iteración anterior.
-   **`customersgallery/views/templates/custom/upload-form2.tpl`**
    -   **Propósito:** Probablemente una versión actualizada o alternativa del formulario de carga, potencialmente con diferentes estilos, características o compatibilidad para versiones más nuevas de PrestaShop.

#### Plantillas de Front-Office (`views/templates/front/`)

Estas plantillas suelen ser utilizadas por los controladores frontales del módulo para renderizar páginas completas o secciones significativas de la funcionalidad del módulo.

-   **`customersgallery/views/templates/front/gallery.tpl`**
    -   **Propósito:** La plantilla principal para la página de la galería de fotos de clientes dedicada, que muestra todas las fotos con paginación.
-   **`customersgallery/views/templates/front/gallery2.tpl`**
    -   **Propósito:** Una versión alternativa o actualizada de la plantilla de la galería principal, que potencialmente ofrece diferentes diseños o características.
-   **`customersgallery/views/templates/front/gallery3.tpl`**
    -   **Propósito:** Otra versión alternativa o actualizada de la plantilla de la galería principal. El módulo podría cambiar entre estas según la configuración o la versión de PrestaShop.
-   **`customersgallery/views/templates/front/menu.tpl`**
    -   **Propósito:** Renderiza un menú de navegación específico para la galería de fotos de clientes, potencialmente para filtrar, ordenar o navegar entre "Mis fotos" y la galería principal.
-   **`customersgallery/views/templates/front/my-photos.tpl`**
    -   **Propósito:** Renderiza la página "Mis fotos" dentro de la cuenta del cliente, mostrando sus imágenes subidas y opciones de gestión.
-   **`customersgallery/views/templates/front/my-videos-16.tpl`**
    -   **Propósito:** Plantilla para la sección "Mis videos", diseñada u optimizada específicamente para PrestaShop 1.6, si la función de carga de videos está habilitada.
-   **`customersgallery/views/templates/front/video-upload.tpl`**
    -   **Propósito:** Renderiza el formulario para que los clientes suban videos, si esta función está activa.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo no define explícitamente archivos SQL personalizados, pero basándose en su funcionalidad, interactuará con la base de datos.

-   **Tablas personalizadas (probablemente creadas durante `install()`):**
    -   `_customersgallery`: Almacena metadatos para cada foto subida (por ejemplo, `id_customersgallery`, `id_customer`, `id_product`, `filename`, `date_add`, `approved`, `votes`, `active`).
    -   `_customersgallery_vote`: Almacena registros de votos de clientes (por ejemplo, `id_customersgallery_vote`, `id_customersgallery`, `id_customer`, `ip_address`, `date_add`).
-   **Registros de configuración (almacenados en `ps_configuration`):**
    -   `CG_LAST_TAB`, `CG_ALLOW_JPEG`, `CG_ALLOW_GIF`, `CG_ALLOW_PNG`, `CG_ALLOW_BMP`, `mypresta_updates`, `CG_PAGINATION`, `CG_ALLOW_UNLOGGED`, `CG_MAX_FILE_SIZE`, `CG_PRODUCTTAB`, `cg_productTabM`, `CG_PRODUCTFOOTER`, `CG_CUSTOMERACCOUNT`, `CG_MYACCOUNTBLOCK`, `CG_THUMBHEIGHT`, `CG_THUMBWIDTH`, `CG_FUPLOADON`, `CG_GALLERY`, `CG_RIGHTCOL`, `CG_LEFTCOL`, `CG_NTF`, `update_`, `updatev_`, `cg_altered1`, `cg_altered2`, `cg_hpg_nb`, `cg_hpg_o`, `cg_contest`, `cg_excludeproduct`, `CG_CUSTOMERACCOUNTV`, `CG_MYACCOUNTBLOCKV`, `CG_voting`, `CG_VOTE_STAR`, `CGV_voting`, `cg_unl_voting`.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta activos CSS y JavaScript requeridos por el módulo (por ejemplo, `customersgallery.css`, `fancybox.js`, `customersgallery.js`). |
| `displayMyAccountBlock` | En el bloque "Mi cuenta" del cliente (a menudo en la columna izquierda/derecha o pie de página). | Añade un enlace a la sección "Mis fotos" del cliente. |
| `displayLeftColumn` | En la barra lateral izquierda de la tienda. | Muestra un bloque de fotos de clientes o un enlace a la galería. |
| `displayRightColumn` | En la barra lateral derecha de la tienda. | Muestra un bloque de fotos de clientes o un enlace a la galería. |
| `displayHome` | En la página de inicio de la tienda. | Muestra una sección de fotos de clientes (las más recientes, las más populares). |
| `displayProductTab` | En la página del producto, para añadir nuevas pestañas. | Añade el encabezado de la pestaña "Fotos de clientes". |
| `displayProductTabContent` | En la página del producto, para el contenido de una pestaña. | Muestra la galería de fotos de clientes y el formulario de carga dentro de la pestaña "Fotos de clientes". |
| `displayProductFooter` | En la parte inferior de la página del producto. | Muestra una sección de fotos de clientes para el producto actual. |
| `displayProductExtraContent` | Otro hook para contenido extra en la página del producto. | Puede usarse como una ubicación alternativa o adicional para contenido fotográfico específico del producto. |
| `displayCustomerAccount` | En la página "Mi cuenta" del cliente. | Añade un enlace a la sección "Mis fotos" para el cliente registrado. |
| `displayLeftColumnProduct` | En la columna izquierda específicamente en las páginas de productos. | Muestra un bloque de fotos de clientes o un enlace a la galería en las páginas de productos. |
| `displayRightColumnProduct` | En la columna derecha específicamente en las páginas de productos. | Muestra un bloque de fotos de clientes o un enlace a la galería en las páginas de productos. |
| `displayMyAccountBlockFooter` | En la versión del pie de página del bloque "Mi cuenta". | Añade un enlace a la sección "Mis fotos" del cliente en el pie de página. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | (Potencial) Podría usarse para enviar un correo electrónico al cliente animando a subir fotos de los productos comprados. |

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier asistencia adicional relacionada con el módulo "Fotos de productos de clientes", consulte su cuenta de cliente de MyPresta.eu. Puede iniciar sesión en [MyPresta.eu Historial de pedidos y descargas](https://mypresta.eu/my-account/orders/) para acceder a las últimas versiones y enviar tickets de soporte.
