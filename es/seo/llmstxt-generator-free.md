---
title: "LLMS.txt Generator Free - Manual de Usuario y Guía de Configuración para Comerciantes"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo LLMS.txt Generator Free para PrestaShop de MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Free - Manual de Usuario y Guía de Configuración para Comerciantes"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo LLMS.txt Generator Free en MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/llmstxt-generator-free/)
>
> ---


# LLMS.txt Generator Free

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Tu servidor debe permitir la escritura de archivos en el directorio raíz de tu instalación de PrestaShop para que el archivo `llms.txt` pueda ser creado y actualizado.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" para acceder a la página de configuración principal del módulo. Aquí es donde definirás qué contenido va en tu archivo `llms.txt`.

#### Configuración General

- **Perfil de la Tienda (para cada idioma activo)**
  - **Qué hace esta configuración:** Te permite escribir una descripción corta y concisa de tu tienda en cada idioma que tu tienda soporta. Este perfil se incluirá en el archivo `llms.txt`, dando a los modelos de IA una visión general rápida de tu negocio.
  - **Efecto de cambiar esta configuración:**
    - *Cuando se rellena:* El texto que proporciones se añadirá al archivo `llms.txt`, ayudando a los modelos de IA a comprender el propósito y las ofertas de tu tienda en idiomas específicos.
    - *Cuando se deja vacío:* No se incluirá ningún perfil de tienda para ese idioma, lo que podría dificultar que la IA capte la esencia de tu tienda.
  - **Valor recomendado:** Rellena esto para cada idioma activo. Mantenlo breve (1-2 frases) y descriptivo.
  - **Escenario / ejemplo de comerciante:** Si tu tienda vende comida orgánica para mascotas, podrías escribir: "MiTienda ofrece una amplia selección de comida orgánica premium para mascotas y suministros naturales para perros y gatos. Priorizamos la salud, la sostenibilidad y las mascotas felices."

#### Selección de Contenido

- **Categorías Promocionadas**

  - **Qué hace esta configuración:** Te permite seleccionar categorías de productos específicas de tu tienda que deseas destacar para los rastreadores de IA. Estas categorías se listarán explícitamente en el archivo `llms.txt`.
  - **Efecto de cambiar esta configuración:**
    - *Cuando se seleccionan categorías:* Los modelos de IA serán dirigidos a estas categorías, señalando su importancia y potencialmente aumentando su visibilidad en las búsquedas impulsadas por IA.
    - *Cuando no se seleccionan categorías:* Los modelos de IA no recibirán una guía específica sobre qué categorías priorizar de tu archivo `llms.txt`.
  - **Valor recomendado:** Selecciona 3-5 de tus categorías más importantes o más vendidas.
  - **Escenario / ejemplo de comerciante:** Si te especializas en "Vestidos de Mujer", "Zapatos de Hombre" y "Juguetes para Niños", selecciona estas categorías para decirle a la IA que estas son ofertas principales.
- **Incluir los 5 Productos Más Vendidos con Precios**

  - **Qué hace esta configuración:** Cuando está habilitado, el módulo identificará automáticamente tus 5 productos más vendidos e incluirá sus nombres, enlaces y precios actuales en el archivo `llms.txt`.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Los modelos de IA tendrán acceso directo a información sobre tus productos más populares, incluyendo sus precios, lo cual puede ser crucial para las recomendaciones de compra impulsadas por IA.
    - *Cuando está deshabilitado:* Tus productos más vendidos no se destacarán explícitamente con sus precios en el archivo `llms.txt`.
  - **Valor recomendado:** SÍ. Esta es una característica potente para mostrar tus artículos más populares.
  - **Escenario / ejemplo de comerciante:** Un cliente le pregunta a una IA: "¿Cuáles son los artículos más vendidos en [Nombre de tu Tienda]?" Con esto habilitado, la IA puede proporcionar una respuesta directa con los precios actuales.
- **Incluir Páginas CMS**

  - **Qué hace esta configuración:** Te permite seleccionar páginas de contenido estático importantes (como "Sobre nosotros", "Contáctanos", "Política de privacidad", "Información de entrega") de las que quieres que los modelos de IA estén al tanto.
  - **Efecto de cambiar esta configuración:**
    - *Cuando se seleccionan páginas CMS:* Los modelos de IA serán dirigidos a estas páginas informativas, ayudándoles a comprender las políticas, el historial de tu tienda y cómo contactarte.
    - *Cuando no se seleccionan páginas CMS:* Los modelos de IA podrían tener que descubrir estas páginas a través de un rastreo general, lo que podría ser menos eficiente.
  - **Valor recomendado:** Selecciona todas las páginas informativas esenciales que generen confianza y proporcionen detalles de servicio al cliente.
  - **Escenario / ejemplo de comerciante:** Asegúrate de que tus páginas de "Política de devoluciones" y "Preguntas frecuentes" estén incluidas para que la IA pueda responder con precisión a las preguntas de los clientes sobre estos temas.

#### Acción

- **Guardar y Regenerar el archivo llms.txt**
  - **Qué hace este botón:** Este botón guarda todas las configuraciones que has configurado en esta página e inmediatamente regenera el archivo `llms.txt` en el directorio raíz de tu tienda con la información actualizada.
  - **Efecto de hacer clic en este botón:** Tu archivo `llms.txt` se actualizará con tus últimas selecciones. Esta acción también se activa automáticamente cuando actualizas productos o categorías en tu tienda.
  - **Valor recomendado:** Haz clic siempre en este botón después de realizar cualquier cambio para asegurarte de que tu archivo `llms.txt` esté actualizado.
  - **Escenario / ejemplo de comerciante:** Después de añadir una nueva descripción de "Perfil de la Tienda", haz clic en este botón para asegurarte de que los rastreadores de IA obtengan la nueva información.

#### Actualizar a la Versión Pro (Bloque de Venta Adicional)

Esta sección es un bloque informativo que promociona la versión Pro del módulo. Destaca características adicionales disponibles en la versión de pago, como la exportación completa del catálogo, análisis de rastreadores, filtros y soporte para tareas programadas (cron jobs). Esto no es una configuración configurable, sino una sugerencia para necesidades avanzadas.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Perfil de la Tienda (por idioma) | Rellenar para todos los idiomas | Proporciona a los modelos de IA una descripción breve y estructurada de tu tienda. |
| Configuración del Módulo | Categorías Promocionadas | Seleccionar 3-5 categorías clave | Dirige a los rastreadores de IA a tus categorías de productos más importantes. |
| Configuración del Módulo | Incluir los 5 Productos Más Vendidos con Precios | SÍ | Destaca tus productos más populares con precios actuales para la IA. |
| Configuración del Módulo | Incluir Páginas CMS | Seleccionar todas las páginas esenciales | Guía a la IA a páginas informativas importantes (ej., Sobre nosotros, Contacto). |
| Configuración del Módulo | Guardar y Regenerar el archivo llms.txt | Hacer clic después de cualquier cambio | Guarda la configuración y actualiza el archivo `llms.txt` en la raíz de tu tienda. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: He configurado el módulo, pero no veo ningún cambio en mi sitio web. ¿Está funcionando?**
R1: Sí, es probable que esté funcionando correctamente. El archivo `llms.txt` es un archivo técnico para los rastreadores de IA, no para los visitantes humanos. No verás ningún cambio visual en el front-office de tu tienda. Para verificar que funciona, puedes intentar acceder a `tutienda.com/llms.txt` en tu navegador. Deberías ver el contenido generado allí.

**P2: Recibo un error que indica que el módulo no puede escribir el archivo `llms.txt`.**
R2: Esto suele indicar un problema de permisos de archivo en tu servidor. El módulo necesita permiso para crear y actualizar el archivo `llms.txt` en el directorio raíz de tu PrestaShop.
- **Solución:** Contacta a tu proveedor de alojamiento y pídeles que se aseguren de que la aplicación PrestaShop tenga permisos de escritura (por ejemplo, chmod 755 o 775 para directorios, 644 o 664 para archivos) en la carpeta raíz de tu tienda.

**P3: ¿Con qué frecuencia se actualiza el archivo `llms.txt`?**
R3: El archivo `llms.txt` se regenera automáticamente cada vez que:
- Haces clic en el botón "Guardar y Regenerar el archivo llms.txt" en la configuración del módulo.
- Actualizas un producto (por ejemplo, cambias el precio, el nombre, la descripción).
- Actualizas una categoría (por ejemplo, cambias el nombre, la descripción).
Esto asegura que el archivo esté siempre actualizado con los datos más recientes de tu tienda.

**P4: Mi tema personalizado no parece verse afectado por este módulo. ¿Hay algún conflicto?**
R4: No, no debería haber ningún conflicto. Este módulo opera completamente en segundo plano, generando un archivo de texto. No modifica el diseño, CSS o JavaScript de tu tema. Su propósito es proporcionar datos estructurados a los rastreadores de IA, no cambiar la apariencia visual de tu tienda.

**P5: ¿Puedo editar manualmente el archivo `llms.txt`?**
R5: Se recomienda encarecidamente **no** editar manualmente el archivo `llms.txt` directamente. Cualquier cambio que realices será sobrescrito la próxima vez que el módulo regenere el archivo (por ejemplo, cuando guardes la configuración o actualices productos/categorías). Utiliza siempre la interfaz de configuración del módulo para controlar su contenido.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `LLMS.txt Generator Free` es un módulo ligero de PrestaShop centrado principalmente en generar un archivo de texto estático (`llms.txt`) en el directorio raíz de la tienda. Sigue una estructura de módulo estándar de PrestaShop, aprovechando la clase `Module` para la instalación, desinstalación y configuración. La lógica central reside dentro del archivo principal del módulo, manejando la persistencia de la configuración y la generación de archivos. Utiliza la clase `Configuration` de PrestaShop para la configuración y los hooks para la regeneración automática.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la lógica se maneja dentro del método `getContent()` del archivo principal del módulo para la configuración y a través de hooks para operaciones en segundo plano.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo **no** contiene ninguna clase personalizada o definiciones de `ObjectModel` en el directorio `classes/`. Utiliza directamente las clases principales de PrestaShop como `Configuration`, `Product`, `Category`, `CMS`, `Language` y `Shop`.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo **no** contiene ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- **`llmstxtfree/views/css/admin-config.css`**
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Principales componentes de la interfaz de usuario y contenedores que estiliza:** Proporciona un estilo básico para la página de configuración del módulo, probablemente para el diseño, el espaciado y, potencialmente, algunas señales visuales para el bloque de venta adicional.
  - **Selectores de clase CSS clave que los desarrolladores pueden sobrescribir en su tema:** Normalmente apunta a elementos dentro de la salida de `getContent()` del módulo, como `.panel`, `.form-group` o clases personalizadas definidas en `configure.tpl`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - **`llmstxtfree/views/templates/admin/configure.tpl`**
    - **Propósito:** Esta es la plantilla principal de Smarty renderizada por el método `getContent()` del módulo. Define la estructura y los campos para la página de configuración del módulo en el Back Office de PrestaShop.
    - **Contenido:** Contiene el formulario HTML para todas las configuraciones descritas en la Sección 4.1, incluyendo campos de entrada para el perfil de la tienda, selección de categorías, alternancia de los más vendidos, selección de páginas CMS y el botón de guardar. También incluye la plantilla `pro-upsell.tpl`.
  - **`llmstxtfree/views/templates/admin/pro-upsell.tpl`**
    - **Propósito:** Esta plantilla se incluye dentro de `configure.tpl` y muestra contenido promocional para la versión Pro del módulo.
    - **Contenido:** Típicamente contiene texto, imágenes y enlaces que animan al comerciante a actualizar a la versión de pago, destacando características adicionales.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:

  - Este módulo **no** crea ninguna tabla SQL personalizada.
  - Almacena sus configuraciones (por ejemplo, categorías seleccionadas, páginas CMS, perfiles de tienda, alternancia de los más vendidos) en la tabla estándar `ps_configuration` de PrestaShop. Las claves de configuración suelen seguir el patrón `LLMSTXTFREE_SETTING_NAME`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | No se utiliza directamente para la salida de contenido, pero a menudo lo registran los módulos para la carga de activos o la configuración inicial. En este módulo, es probable que sea para la inicialización general del módulo o potencialmente para futuras características. |
| `displayRightColumn` | Renderiza contenido en la columna derecha de las páginas del front-office. | No se utiliza para la salida de contenido en este módulo. |
| `displayLeftColumn` | Renderiza contenido en la columna izquierda de las páginas del front-office. | No se utiliza para la salida de contenido en este módulo. |
| `displayFooter` | Renderiza contenido en el pie de página de las páginas del front-office. | No se utiliza para la salida de contenido en este módulo. |
| `displayProductExtraContent` | Renderiza contenido extra en la página del producto. | No se utiliza para la salida de contenido en este módulo. |
| `actionProductUpdate` | Se ejecuta después de que un producto se actualiza en el Back Office. | **Crucial para este módulo:** Activa la regeneración automática del archivo `llms.txt` para asegurar que los datos de los más vendidos y los enlaces de los productos estén actualizados. |
| `actionCategoryUpdate` | Se ejecuta después de que una categoría se actualiza en el Back Office. | **Crucial para este módulo:** Activa la regeneración automática del archivo `llms.txt` para asegurar que los enlaces y nombres de las categorías promocionadas estén actualizados. |
| `actionObjectCmsUpdateAfter` | Se ejecuta después de que se actualiza una página CMS. | Activa la regeneración automática del archivo `llms.txt` para asegurar que los enlaces y títulos de las páginas CMS seleccionadas estén actualizados. |
| `actionObjectCmsAddAfter` | Se ejecuta después de que se añade una nueva página CMS. | Activa la regeneración automática del archivo `llms.txt`. |
| `actionObjectCmsDeleteAfter` | Se ejecuta después de que se elimina una página CMS. | Activa la regeneración automática del archivo `llms.txt`. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para explorar módulos y servicios adicionales, visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con el módulo LLMS.txt Generator Free.
