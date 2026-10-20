---
title: "Aumentar el límite de caracteres en la descripción del producto - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Aumentar el límite de caracteres en la descripción del producto' de MyPresta.eu."
sidebar:
  label: "Aumentar el límite de caracteres en la descripción del producto - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Increase characters limit in product description en MyPresta.eu](https://mypresta.eu/modules/administration-tools/increase-characters-limit-in-product-description.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/increase-characters-limit-in-product-description/)
>
> ---


# Aumentar el límite de caracteres en la descripción del producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5 (Siempre extendiéndose a PHP 8.5 para futuras pruebas)
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes. Esta es la pantalla de configuración principal y única para este módulo.

#### Ajustes y opciones:

1. **Longitud de la descripción del producto**

   - **Qué hace este ajuste:** Este campo controla el número máximo de caracteres permitidos en el campo principal "Descripción" para todos sus productos en el Back Office de PrestaShop. El límite predeterminado de PrestaShop es de 21.844 caracteres.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en un número mayor:* Podrá introducir más caracteres en el campo de descripción del producto al editar productos. Esto permite un contenido más detallado.
     - *Cuando se establece en un número menor (no recomendado):* Restringiría su capacidad para añadir contenido detallado, truncando potencialmente descripciones existentes más largas.
   - **Valor recomendado:** Un número significativamente mayor como `65535` o `16777215` (que corresponde a los límites `MEDIUMTEXT` o `LONGTEXT` de MySQL, eliminando efectivamente los límites prácticos para la mayoría del contenido). También puede establecerlo en `0` o dejarlo vacío para eliminar el límite por completo y usar el máximo posible.
   - **Escenario / ejemplo de comerciante:** Vende aparatos de alta tecnología y necesita incluir especificaciones técnicas extensas, listas de compatibilidad y guías de usuario directamente en la descripción del producto. Establecer esto en `65535` le asegura un amplio espacio.
2. **Longitud del nombre del producto**

   - **Qué hace este ajuste:** Este campo controla el número máximo de caracteres permitidos para el campo "Nombre del producto" para todos sus productos. El límite predeterminado de PrestaShop suele ser de 128 o 255 caracteres, dependiendo de la versión.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en un número mayor:* Puede usar nombres de producto más largos, lo que puede ser útil para productos muy específicos, incluyendo números de modelo, o para fines de SEO donde los títulos más largos y descriptivos son beneficiosos.
     - *Cuando se establece en un número menor (no recomendado):* Restringiría la denominación del producto, lo que podría causar problemas con los productos existentes o dificultar la diferenciación de los artículos.
   - **Valor recomendado:** Un número mayor como `512` o `1024` si necesita nombres de producto muy largos. Para la mayoría de las tiendas, el valor predeterminado es suficiente, pero si tiene necesidades específicas (por ejemplo, incluir números de pieza completos o descripciones detalladas del modelo), aumentar esto es útil.
   - **Escenario / ejemplo de comerciante:** Vende equipos industriales, y los nombres de los productos a menudo incluyen el fabricante, el modelo, las características específicas y los números de versión (por ejemplo, "Mezcladora Industrial de Alta Resistencia Modelo 5000-A de XYZ Corp. con Control de Velocidad Variable y Tolva de Acero Inoxidable"). Aumentar este límite a `512` le permite incluir el nombre completo y descriptivo.
3. **PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG** (Este es un ajuste estándar de PrestaShop, no controlado directamente por el módulo, pero a menudo relevante para la edición de contenido)

   - **Qué hace este ajuste:** Este ajuste central de PrestaShop determina si los empleados pueden seleccionar el idioma para un campo de formulario directamente dentro del formulario, o si el idioma del formulario está determinado por el idioma del back office del empleado. No es un ajuste del módulo, pero a menudo es visible o relevante cuando se trata de contenido multilingüe.
   - **Efecto de cambiar este ajuste:**
     - *Cuando está habilitado:* Los empleados pueden cambiar el idioma de los campos de texto (como las descripciones de productos) directamente en la página de edición del producto, lo que les permite introducir contenido para diferentes idiomas sin cambiar todo el idioma de su back office.
     - *Cuando está deshabilitado:* El idioma de los campos de texto coincidirá con el idioma actual del back office del empleado. Para editar contenido en otro idioma, el empleado debe cambiar el idioma de su back office.
   - **Valor recomendado:** Generalmente **SÍ** para tiendas multilingües con varios editores de contenido, ya que mejora el flujo de trabajo.
   - **Escenario / ejemplo de comerciante:** Tiene un editor de contenido de habla francesa y un editor de contenido de habla inglesa. Si esto está habilitado, el editor francés puede escribir la descripción en francés y luego cambiar el menú desplegable de idioma a inglés para escribir la descripción en inglés, todo en la misma página de producto.

#### 2.1.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Longitud de la descripción del producto | `65535` o `0` (sin límite) | Aumenta el número máximo de caracteres para las descripciones de productos. Permite un contenido más detallado y un mejor SEO. |
| Configuración del módulo | Longitud del nombre del producto | `512` o `1024` | Aumenta el número máximo de caracteres para los nombres de productos. Útil para títulos de productos muy específicos o descriptivos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He aumentado el límite de caracteres, pero mis descripciones de productos aún parecen cortarse en el front office. ¿Qué pasa?**
R: Esto suele ser un problema relacionado con el tema, no con el módulo.
- **Verifique la configuración de visualización de su tema:** Algunos temas pueden tener su propio CSS o JavaScript que trunca el texto largo para ajustarse a un diseño específico. Es posible que deba consultar la documentación de su tema o a un desarrollador web para ajustar esto.
- **Borrar caché de Smarty:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop, desplácese hasta "Borrar caché" y haga clic en "Borrar caché". A veces, los archivos de plantilla antiguos se almacenan en caché.
- **Verifique en el Back Office:** Vuelva a comprobar que la descripción completa se guarda correctamente en la página de edición del producto en su Back Office. Si se corta allí, es posible que el módulo no se haya aplicado correctamente (aunque esto es raro).

**P: ¿Este módulo afecta al SEO?**
R: Indirectamente, sí, de una manera muy positiva. Al permitirle escribir descripciones de productos más largas, más detalladas y ricas en palabras clave, proporciona más contenido para que los motores de búsqueda lo rastreen e indexen. Esto puede conducir a mejores clasificaciones para las consultas de búsqueda relevantes y atraer más tráfico orgánico a sus páginas de productos.

**P: ¿Este módulo ralentizará mi tienda?**
R: No, este módulo tiene un impacto insignificante en el rendimiento de la tienda. Principalmente modifica las definiciones de las columnas de la base de datos durante la instalación/configuración. Una vez configurado, no añade ningún procesamiento complejo ni scripts de front-office que ralenticen los tiempos de carga de la página. La única "ralentización" potencial podría ser si escribe descripciones extremadamente largas que tarden más en cargarse desde la base de datos, pero esto suele ser mínimo y se compensa con los beneficios del SEO.

**P: Cambié los límites, pero no veo el cambio en la página de edición del producto. ¿Qué debo hacer?**
R:
- **Guarde la configuración del módulo:** Asegúrese de haber hecho clic en el botón "Guardar" después de cambiar los límites de caracteres en la página de configuración del módulo.
- **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
- **Actualice su navegador:** A veces el navegador almacena en caché formularios antiguos. Realice una actualización forzada (Ctrl+F5 o Cmd+Shift+R).
- **Cierre sesión y vuelva a iniciarla:** Para algunos cambios administrativos, cerrar sesión y volver a iniciarla en el Back Office puede asegurar que todos los datos de la sesión se actualicen.

**P: ¿Hay un límite máximo que puedo establecer?**
R: Si bien el módulo le permite establecer prácticamente cualquier número, el límite práctico está determinado por las capacidades de su base de datos. Para los campos `TEXT` en MySQL, el máximo es `65.535` caracteres. Para `MEDIUMTEXT`, es `16.777.215` caracteres, y para `LONGTEXT`, es `4.294.967.295` caracteres. Establecer `0` o dejar el campo vacío normalmente se establecerá por defecto en el tipo `TEXT` más grande posible, eliminando efectivamente cualquier límite práctico para la mayoría del contenido. Para los nombres de productos, `255` o `512` caracteres suelen ser más que suficientes.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Aumentar el límite de caracteres en la descripción del producto" es un módulo ligero de PrestaShop diseñado principalmente para modificar el esquema de la base de datos para los campos de texto relacionados con el producto. Opera alterando el `type` y `size` de columnas específicas en la tabla `ps_product_lang` (para descripciones) y las tablas `ps_product` / `ps_product_lang` (para nombres) durante su instalación y configuración. No introduce ningún controlador de front-office, clases personalizadas o JavaScript/CSS complejos. Su funcionalidad principal se ejecuta a través de los métodos `install()` y `getContent()` de la clase principal del módulo.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** introduce ninguna clase personalizada o definiciones de `ObjectModel`. Interactúa directamente con las tablas de la base de datos central de PrestaShop y la configuración existentes.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo **no** incluye ningún archivo de plantilla Smarty personalizado. El formulario de configuración se renderiza directamente dentro del método `getContent()` utilizando los componentes `HelperForm` estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo interactúa principalmente con las siguientes tablas principales de PrestaShop:

- `ps_product_lang`:
  - Columna **`description`**: Modificada a un tipo `TEXT` más grande (por ejemplo, `MEDIUMTEXT` o `LONGTEXT`) para acomodar más caracteres.
  - Columna **`description_short`**: No modificada directamente por este módulo, pero a menudo relacionada.
  - Columna **`name`**: Modificada a un tipo `VARCHAR` más grande (por ejemplo, `VARCHAR(512)`) para acomodar más caracteres.
- `ps_configuration`:
  - `chr_max_description_length`: Almacena la longitud máxima configurada para las descripciones de productos.
  - `chr_max_name_length`: Almacena la longitud máxima configurada para los nombres de productos.
  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una clave de configuración estándar de PrestaShop, no creada por el módulo, pero a menudo referenciada en el contexto de la edición de contenido.

El método `install()` del módulo contiene consultas SQL para alterar estas columnas de la tabla. El método `uninstall()` intenta revertir estos cambios, aunque podría ser necesaria una verificación manual dependiendo del estado de la base de datos.

#### Tabla de Hooks registrados

Este módulo **no** registra ningún hook de visualización de front-office o back-office. Su funcionalidad es completamente impulsada por el backend al modificar el esquema de la base de datos.

El método `install()` del módulo podría usar implícitamente `Configuration::updateValue()`, que no registra directamente hooks pero almacena valores.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Aumentar el límite de caracteres en la descripción del producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
