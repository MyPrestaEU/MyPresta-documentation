---
title: "Cupones para Fans de Facebook - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Cupones para Fans de Facebook de MyPresta.eu."
sidebar:
  label: "Cupones para Fans de Facebook - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Fan Coupons en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-coupons.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-fan-coupons/)
>
> ---


# Cupones para Fans de Facebook

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Tu servidor debe poder comunicarse con la API de Facebook.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo Cupones para Fans de Facebook, donde defines cómo se generan los cupones y cómo se comporta el módulo.

#### Ajustes Generales

- **Qué hace este ajuste:** Estos ajustes controlan el comportamiento general del módulo, incluyendo actualizaciones y funcionalidad básica.
- **Efecto de cambiar este ajuste:**
  - `mypresta_updates`, `update_`, `updatev_`: Estos son ajustes internos relacionados con las actualizaciones del módulo y las comprobaciones de versión por parte de MyPresta.eu. Generalmente no necesitas cambiarlos.
- **Valor recomendado:** Deja estos valores por defecto.
- **Escenario / ejemplo de comerciante:** Estos ajustes aseguran que tu módulo esté actualizado y sea compatible con los servicios de MyPresta.eu.

#### Ajustes de Generación de Cupones

- **FANCOUPON\_FONTSTYLE**

  - **Qué hace este ajuste:** Define el estilo de fuente utilizado para el código de cupón generado que se muestra al cliente en tu pestaña de Facebook. Esto es puramente para presentación visual.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece una fuente específica:* El código de cupón se mostrará en esa fuente, haciéndolo más atractivo visualmente o coincidiendo con tu marca.
    - *Cuando se deja por defecto:* Se utilizará una fuente estándar y legible.
  - **Valor recomendado:** Elige una fuente clara y legible que coincida con la estética de tu marca.
  - **Escenario / ejemplo de comerciante:** Si tu marca utiliza una fuente elegante específica, puedes introducir su nombre aquí (por ejemplo, "Arial Black", "Verdana") para que el cupón se vea más integrado.
- **FANCOUPON\_VOUCHERCODE**

  - **Qué hace este ajuste:** Este es el *prefijo* para los códigos de vale generados automáticamente. Cada código comenzará con este texto, seguido de caracteres aleatorios.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "FANCOUPON":* Todos los códigos generados se verán como "FANCOUPONABCD123".
    - *Cuando se establece en "FBPROMO":* Todos los códigos generados se verán como "FBPROMOXYZ789".
  - **Valor recomendado:** Un prefijo corto y memorable relacionado con Facebook o tu promoción (por ejemplo, "FBPROMO", "FAN2024", "MYFAN").
  - **Escenario / ejemplo de comerciante:** Usar "FBPROMO" te ayuda a identificar fácilmente qué pedidos provienen de esta campaña de Facebook en tu historial de pedidos de PrestaShop.
- **FANCOUPON\_MODE**

  - **Qué hace este ajuste:** Determina el tipo de descuento que proporcionará el código de vale generado (por ejemplo, porcentaje, cantidad fija, envío gratuito).
  - **Efecto de cambiar este ajuste:**
    - *Descuento porcentual:* El cupón reducirá el total del pedido en un porcentaje (por ejemplo, 10% de descuento).
    - *Descuento de cantidad fija:* El cupón reducirá el total del pedido en un valor monetario fijo (por ejemplo, $10 de descuento).
    - *Envío gratuito:* El cupón hará que el envío sea gratuito para el pedido.
  - **Valor recomendado:** Esto depende de tu estrategia de marketing. Los descuentos porcentuales suelen ser populares para promociones generales.
  - **Escenario / ejemplo de comerciante:** Para ofrecer un 15% de descuento a los nuevos fans de Facebook, seleccionarías "Descuento porcentual" aquí y luego especificarías "15" en el campo de valor correspondiente (que aparece después de seleccionar el modo).
- **FANCOUPON\_CHARS**

  - **Qué hace este ajuste:** Especifica los tipos de caracteres (letras, números) que se utilizarán en la *parte aleatoria* del código de vale generado.
  - **Efecto de cambiar este ajuste:**
    - *Letras y Números:* Los códigos serán una mezcla de caracteres alfanuméricos (por ejemplo, "ABC123").
    - *Solo Números:* Los códigos solo contendrán dígitos (por ejemplo, "123456").
    - *Solo Letras:* Los códigos solo contendrán letras (por ejemplo, "ABCDEF").
  - **Valor recomendado:** "Letras y Números" para máxima unicidad y seguridad.
  - **Escenario / ejemplo de comerciante:** Para hacer los códigos más fáciles de leer, podrías elegir "Solo Letras", pero esto reduce el número de combinaciones únicas posibles para una longitud dada.
- **FANCOUPON\_LENGTH**

  - **Qué hace este ajuste:** Define la longitud de la *parte aleatoria* del código de vale generado (excluyendo el prefijo).
  - **Efecto de cambiar este ajuste:**
    - *Longitud más corta (por ejemplo, 4):* Los códigos son más rápidos de escribir pero menos únicos (por ejemplo, "FBPROMOABCD").
    - *Longitud más larga (por ejemplo, 8):* Los códigos son más seguros y únicos pero tardan más en escribirse (por ejemplo, "FBPROMOABCD12345").
  - **Valor recomendado:** 6-8 caracteres para un buen equilibrio entre unicidad y usabilidad.
  - **Escenario / ejemplo de comerciante:** Si esperas un volumen muy alto de generaciones de cupones, una longitud mayor asegura que cada código sea verdaderamente único y evita duplicados accidentales.
- **FANCOUPON\_VOUCHER\_CAT**

  - **Qué hace este ajuste:** Te permite restringir el código de vale generado para que se aplique solo a productos dentro de categorías específicas en tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan categorías específicas:* El cupón solo funcionará si el cliente tiene productos de esas categorías en su carrito.
    - *Cuando no se seleccionan categorías:* El cupón se aplicará a todos los productos de la tienda.
  - **Valor recomendado:** Déjalo vacío si el cupón debe aplicarse a toda la tienda. Selecciona categorías si deseas promocionar líneas de productos específicas.
  - **Escenario / ejemplo de comerciante:** Si estás ejecutando una promoción específicamente para tu "Colección de Verano", seleccionarías esa categoría aquí para que el cupón solo funcione en esos artículos.
- **PS\_LANG\_DEFAULT**

  - **Qué hace este ajuste:** Este es el ID de idioma predeterminado de tu tienda PrestaShop. Es utilizado internamente por el módulo para asegurar que las descripciones de los cupones y otros elementos dependientes del idioma se creen correctamente.
  - **Efecto de cambiar este ajuste:** Cambiar esto incorrectamente podría provocar problemas con la forma en que se crean los cupones en el idioma predeterminado de tu tienda.
  - **Valor recomendado:** Déjalo como el valor predeterminado detectado automáticamente por PrestaShop.
  - **Escenario / ejemplo de comerciante:** Esto asegura que cuando se genera un cupón, su descripción interna (por ejemplo, "Cupón para Fan de Facebook") se establezca correctamente en el idioma principal de tu tienda.

#### Ajustes de Bloques de Publicidad (Opcional)

- **FANCOUPON\_ADV\_POS1**

  - **Qué hace este ajuste:** Controla la imagen/banner que se muestra en la **columna izquierda** de tu tienda PrestaShop para promocionar la oferta de cupones de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce una URL de imagen:* La imagen especificada aparecerá en la columna izquierda.
    - *Cuando se deja vacío:* No se mostrará ninguna imagen en la columna izquierda.
  - **Valor recomendado:** Una imagen de banner atractiva (por ejemplo, 200px de ancho) que anuncie claramente la oferta "¡Danos Me Gusta en Facebook, obtén un cupón!".
  - **Escenario / ejemplo de comerciante:** Subes una imagen de banner personalizada a tu servidor (por ejemplo, `img/cms/fb-coupon-left.jpg`) e introduces su URL completa aquí.
- **FANCOUPON\_ADV\_POS2**

  - **Qué hace este ajuste:** Controla la imagen/banner que se muestra en la **columna derecha** de tu tienda PrestaShop para promocionar la oferta de cupones de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce una URL de imagen:* La imagen especificada aparecerá en la columna derecha.
    - *Cuando se deja vacío:* No se mostrará ninguna imagen en la columna derecha.
  - **Valor recomendado:** Similar a `FANCOUPON_ADV_POS1`, una imagen de banner atractiva (por ejemplo, 200px de ancho).
  - **Escenario / ejemplo de comerciante:** Podrías usar un diseño diferente para el banner de la columna derecha o simplemente duplicar el de la columna izquierda.
- **FANCOUPON\_ADV\_POS3**

  - **Qué hace este ajuste:** Controla la imagen/banner que se muestra en el **pie de página (footer)** de tu tienda PrestaShop para promocionar la oferta de cupones de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce una URL de imagen:* La imagen especificada aparecerá en el pie de página.
    - *Cuando se deja vacío:* No se mostrará ninguna imagen en el pie de página.
  - **Valor recomendado:** Una imagen de banner atractiva adecuada para el área del pie de página.
  - **Escenario / ejemplo de comerciante:** Un banner más ancho y corto (por ejemplo, 900px de ancho, 100px de alto) que encaje bien en el pie de página.
- **FANCOUPON\_ADV\_URL**

  - **Qué hace este ajuste:** Esta es la URL a la que enlazarán todos los banners publicitarios (`FANCOUPON_ADV_POS1`, `POS2`, `POS3`) cuando se haga clic en ellos. Esta debe ser la URL directa a la pestaña de tu Página de Fans de Facebook donde se puede generar el cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece la URL de tu pestaña de Facebook:* Al hacer clic en cualquiera de los banners, el cliente será llevado directamente a la pestaña de generación de cupones en tu página de Facebook.
    - *Cuando se deja vacío o incorrecto:* Los banners no serán clicables o llevarán a una página incorrecta.
  - **Valor recomendado:** La URL exacta de la pestaña de tu Página de Fans de Facebook donde está incrustado el módulo de cupones.
  - **Escenario / ejemplo de comerciante:** Después de configurar la pestaña de Facebook, obtendrás una URL única para ella (por ejemplo, `https://www.facebook.com/TU_PAGINA/app_1234567890`). Introduce esa URL aquí.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | `FANCOUPON_FONTSTYLE` | Fuente del sistema predeterminada | Estilo de fuente para el código de cupón mostrado en Facebook. |
| Configuración del Módulo | `FANCOUPON_VOUCHERCODE` | `FANCOUPON` | Prefijo para los códigos de vale generados. Ayuda a identificar la campaña. |
| Configuración del Módulo | `FANCOUPON_MODE` | Descuento porcentual | Tipo de descuento (porcentaje, fijo, envío gratuito). |
| Configuración del Módulo | `FANCOUPON_CHARS` | Letras y Números | Conjunto de caracteres para la parte aleatoria del código. |
| Configuración del Módulo | `FANCOUPON_LENGTH` | 6-8 caracteres | Longitud de la parte aleatoria del código. Afecta la unicidad. |
| Configuración del Módulo | `FANCOUPON_VOUCHER_CAT` | Vacío (todos los productos) | Restringe el uso del cupón a categorías de productos específicas. |
| Configuración del Módulo | `FANCOUPON_ADV_POS1` | Vacío | URL de la imagen del banner para la columna izquierda. |
| Configuración del Módulo | `FANCOUPON_ADV_POS2` | Vacío | URL de la imagen del banner para la columna derecha. |
| Configuración del Módulo | `FANCOUPON_ADV_POS3` | Vacío | URL de la imagen del banner para el pie de página. |
| Configuración del Módulo | `FANCOUPON_ADV_URL` | Vacío | URL de destino para todos los banners publicitarios (tu pestaña de Facebook). |

## 3. Resolución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis cupones no funcionan después de la generación.**
R: Comprueba lo siguiente:
1. **Reglas de Carrito de PrestaShop:** Ve a **Catálogo > Descuentos > Reglas de carrito** en tu back office de PrestaShop. Busca cupones con el prefijo que definiste (`FANCOUPON_VOUCHERCODE`). Asegúrate de que estén activos y no hayan caducado. El módulo los crea automáticamente, pero a veces puede ocurrir una intervención manual o un conflicto.
2. **Configuración del Módulo:** Vuelve a verificar tus ajustes `FANCOUPON_MODE` y `FANCOUPON_VOUCHER_CAT`. Si restringiste el cupón a una categoría, asegúrate de que el cliente esté intentando usarlo en productos de esa categoría.
3. **Caché:** Borra la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento**) y la caché de tu navegador.

**P: Los banners publicitarios no aparecen en mi tienda.**
R:
1. **Hooks del Módulo:** Asegúrate de que el módulo esté enganchado correctamente. En **Módulos > Gestor de Módulos**, busca "Cupones para Fans de Facebook" y haz clic en "Configurar". Revisa la pestaña "Posiciones" (o "Hooks" en versiones anteriores) para ver si está asignado a `displayLeftColumn`, `displayRightColumn` o `displayFooter`. Si no, es posible que debas engancharlo manualmente a través de **Diseño > Posiciones** (o **Módulos > Posiciones**).
2. **URLs de Imágenes:** Verifica que las URLs introducidas para `FANCOUPON_ADV_POS1`, `POS2`, `POS3` sean correctas y que las imágenes existan en esas ubicaciones.
3. **Compatibilidad del Tema:** Algunos temas personalizados pueden anular las posiciones de los hooks estándar. Si los banners aún no aparecen, es posible que necesites que un webmaster revise los archivos de plantilla de tu tema.

**P: La pestaña de Facebook no funciona o no muestra el generador de cupones.**
R: Este módulo proporciona la lógica de backend para la generación de cupones. La configuración real de la pestaña de Facebook se realiza *dentro de las herramientas para desarrolladores de Facebook* o una aplicación de terceros que incrusta contenido personalizado.
1. **Configuración de la Aplicación de Facebook:** Asegúrate de haber configurado correctamente una Aplicación de Facebook y de haberla vinculado a tu Página de Fans, apuntando a la URL del módulo (que suele ser el dominio de tu tienda PrestaShop con una ruta específica, o una página dedicada que hayas configurado para alojar la salida del módulo). Este módulo proporciona la *lógica* para el cupón, pero la *visualización en Facebook* requiere una configuración adecuada de la Aplicación de Facebook.
2. **Permisos de la Página de Facebook:** Asegúrate de que tu página de Facebook tenga los permisos necesarios para pestañas personalizadas.
3. **Conexión Segura (HTTPS):** Facebook requiere que todas las aplicaciones incrustadas se ejecuten a través de HTTPS. Asegúrate de que tu tienda PrestaShop esté completamente protegida con un certificado SSL.

**P: ¿Cómo traduzco el texto del módulo?**
R: Puedes traducir las frases del módulo a través del back office de PrestaShop:
1. Ve a **Internacional > Traducciones** (o **Localización > Traducciones** en versiones anteriores).
2. Selecciona "Traducciones de módulos instalados".
3. Elige tu tema, tu idioma y luego selecciona "Cupones para Fans de Facebook" de la lista de módulos.
4. Luego podrás editar cualquier cadena traducible utilizada por el módulo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo Cupones para Fans de Facebook (`fancoupon`) es un módulo estándar de PrestaShop centrado principalmente en la lógica de backend para la generación de cupones y la publicidad básica en el front-office. Aprovecha la clase `Module` y la clase `Configuration` de PrestaShop para almacenar la configuración. La funcionalidad principal implica la creación dinámica de objetos `CartRule` (vales) basados en la interacción del usuario en una pestaña de Facebook (que es externa a PrestaShop pero interactúa con la lógica del módulo). Los componentes del front-office se limitan a simples banners de imagen enganchados en posiciones de visualización estándar.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador dedicado de front-office o back-office. Toda la configuración se maneja a través del método `getContent()` de la clase principal del módulo. Cualquier interacción para la generación de cupones se manejaría típicamente mediante una aplicación externa de Facebook que apunta a una URL en el sitio de PrestaShop, lo que luego activa la lógica del módulo (probablemente a través de un hook o un punto de entrada personalizado no definido explícitamente como `ModuleFrontController` en el inventario proporcionado, sino manejado por la lógica central del módulo cuando se llama).

### 4.3 Clases y Modelos Centrales (`classes/`)

Este módulo **no** contiene ninguna clase o modelo personalizado en el directorio `classes/`. Utiliza directamente las clases centrales `CartRule` y `Configuration` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

- `fancoupon/lib/voucherengine/script.js`
  - **Alcance:** Probablemente Front-office (destinado a la interfaz de la pestaña de Facebook).
  - **Responsabilidad:** Se espera que este script maneje la lógica del lado del cliente para el proceso de generación de cupones. Esto incluiría:
    - Detectar si un usuario ha dado "Me gusta" a la página de Facebook (a través de la API de Facebook).
    - Activar una solicitud AJAX al backend de PrestaShop (o al punto de entrada del módulo) para generar un cupón.
    - Mostrar el código de cupón generado al usuario.
    - Potencialmente manejar elementos de la interfaz de usuario como spinners de carga o mensajes de éxito/error.
- `fancoupon/views/js/voucherengine/script.js`
  - **Alcance:** Probablemente Front-office (destinado a la interfaz de la pestaña de Facebook).
  - **Responsabilidad:** Esto parece ser un duplicado o una versión del script en `lib/`. Serviría para el mismo propósito descrito anteriormente, manejando los elementos interactivos de la generación de cupones en la pestaña de Facebook. Los desarrolladores deben verificar qué `script.js` se carga y utiliza realmente.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `fancoupon/lib/voucherengine/ps16.css`
  - **Alcance:** Estilo del cliente del Front-office.
  - **Responsabilidad:** Proporciona un estilo básico para la interfaz de generación de cupones, probablemente dentro de la pestaña de Facebook. El `ps16` en el nombre del archivo sugiere que podría contener estilos específicamente adaptados para la estructura del tema predeterminado de PrestaShop 1.6, pero debería ser generalmente compatible o fácilmente adaptable.
  - **Selectores de clase CSS clave:** Típicamente incluiría estilos para botones, campos de entrada, áreas de visualización de texto para el código de cupón y el diseño general del generador de cupones. Los desarrolladores pueden inspeccionar el HTML renderizado en la pestaña de Facebook para identificar selectores específicos para anular.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/advert-*.tpl`)**:
  - `fancoupon/views/templates/advert-footer.tpl`
    - **Hook:** `displayFooter` (o `footer` en versiones anteriores).
    - **Salida:** Renderiza un banner/imagen publicitaria en el pie de página de la tienda, enlazando a la pestaña de la Página de Fans de Facebook. Utiliza `FANCOUPON_ADV_POS3` como fuente de la imagen y `FANCOUPON_ADV_URL` para el enlace.
  - `fancoupon/views/templates/advert-left.tpl`
    - **Hook:** `displayLeftColumn` (o `leftcolumn` en versiones anteriores).
    - **Salida:** Renderiza un banner/imagen publicitaria en la columna izquierda de la tienda, enlazando a la pestaña de la Página de Fans de Facebook. Utiliza `FANCOUPON_ADV_POS1` como fuente de la imagen y `FANCOUPON_ADV_URL` para el enlace.
  - `fancoupon/views/templates/advert-right.tpl`
    - **Hook:** `displayRightColumn` (o `rightcolumn` en versiones anteriores).
    - **Salida:** Renderiza un banner/imagen publicitaria en la columna derecha de la tienda, enlazando a la pestaña de la Página de Fans de Facebook. Utiliza `FANCOUPON_ADV_POS2` como fuente de la imagen y `FANCOUPON_ADV_URL` para el enlace.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna identificada.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna identificada. La interfaz de usuario central de generación de cupones probablemente se renderiza dinámicamente a través de JavaScript o directamente dentro de la lógica de `fancoupon.php` cuando se llama desde Facebook.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  - Este módulo no crea tablas SQL personalizadas.
  - Almacena sus ajustes de configuración en la tabla `ps_configuration` de PrestaShop utilizando claves como `FANCOUPON_FONTSTYLE`, `FANCOUPON_VOUCHERCODE`, etc.
  - Crea entradas en `ps_cart_rule` y tablas relacionadas (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, etc.) para cada cupón generado.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda de la tienda. | Muestra el banner publicitario de la columna izquierda. |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha de la tienda. | Muestra el banner publicitario de la columna derecha. |
| `displayFooter` | Renderiza contenido en la sección del pie de página de la tienda. | Muestra el banner publicitario del pie de página. |
| `leftcolumn` | (PrestaShop 1.6.x y anteriores) Renderiza contenido en la barra lateral izquierda. | Hook heredado para el banner publicitario de la columna izquierda. |
| `rightcolumn` | (PrestaShop 1.6.x y anteriores) Renderiza contenido en la barra lateral derecha. | Hook heredado para el banner publicitario de la columna derecha. |
| `footer` | (PrestaShop 1.6.x y anteriores) Renderiza contenido en la sección del pie de página. | Hook heredado para el banner publicitario del pie de página. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, soporte técnico y cualquier consulta relacionada con el módulo Cupones para Fans de Facebook, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte dedicado está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta.
