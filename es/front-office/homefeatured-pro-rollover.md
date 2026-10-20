---
title: "HomeFeatured Pro Rollover - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo HomeFeatured Pro Rollover de PrestaShop por MyPresta.eu."
sidebar:
  label: "HomeFeatured Pro Rollover"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo HomeFeatured Pro Rollover en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homefeatured-pro-rollover.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homefeatured-pro-rollover/)
>
> ---


# HomeFeatured Pro Rollover

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente vienen preinstaladas en la mayoría de los entornos de alojamiento web.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Después de la instalación, haz clic en "Configurar" junto a "HomeFeatured Pro Rollover" en el Gestor de Módulos para acceder a sus ajustes.

#### 2.1.1 Número de productos a mostrar
-   **Qué hace este ajuste:** Controla cuántos productos destacados se mostrarán en la sección "Productos Destacados" de tu página de inicio.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece un número específico (por ejemplo, 8):* Tu página de inicio mostrará exactamente esa cantidad de productos de tu categoría "Inicio" (o la categoría que hayas designado para productos destacados).
    -   *Cuando se establece un número diferente:* El número de productos mostrados cambiará en consecuencia. Si lo estableces demasiado alto, podría hacer que tu página de inicio sea muy larga; si es demasiado bajo, es posible que no muestres suficientes productos.
-   **Valor recomendado:** Un número que se ajuste bien al diseño de tu página de inicio, típicamente entre 8 y 12 para una cuadrícula estándar.
-   **Escenario / ejemplo de comerciante:** Si quieres destacar tus 8 productos más vendidos en la página de inicio, lo establecerías en "8". Si tienes un diseño más amplio y quieres mostrar más variedad, podrías aumentarlo a "12".

#### 2.1.2 Mostrar atributos en la página del producto
-   **Qué hace este ajuste:** Este es un ajuste estándar de PrestaShop que controla si los atributos del producto (como tamaño, color) se muestran en la propia página del producto. Aunque este módulo afecta principalmente a la página de inicio, este ajuste a menudo se incluye en módulos que interactúan con las visualizaciones de productos.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (Sí):* Los atributos del producto serán visibles y seleccionables en las páginas de productos individuales.
    -   *Cuando está deshabilitado (No):* Los atributos del producto no se mostrarán en las páginas de productos, lo que podría simplificar la página pero eliminar opciones de selección importantes para los clientes.
-   **Valor recomendado:** **Sí**. La mayoría de las tiendas necesitan mostrar atributos para productos con variaciones.
-   **Escenario / ejemplo de comerciante:** Para una tienda de ropa, los clientes necesitan seleccionar talla y color. Habilitar esto asegura que esas opciones aparezcan en la página del producto. Deshabilitarlo haría imposible que los clientes eligieran variaciones.

#### 2.1.3 Idioma predeterminado
-   **Qué hace este ajuste:** Este ajuste especifica el idioma predeterminado de tu tienda. Es un ajuste central de PrestaShop a menudo referenciado por los módulos para asegurar un manejo adecuado del idioma.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en tu idioma principal (por ejemplo, Español):* El módulo utilizará este idioma para cualquier dato dependiente del idioma o para los valores predeterminados si faltan traducciones.
-   **Valor recomendado:** **El idioma principal de tu tienda.** Esto debe coincidir con el idioma predeterminado que hayas configurado en los ajustes de localización de PrestaShop.
-   **Escenario / ejemplo de comerciante:** Si el público principal de tu tienda está en Francia, lo establecerías en "Francés" para asegurar que todo el texto predeterminado y la información del producto se muestren correctamente en francés.

#### 2.1.4 Número de productos a mostrar (Duplicado de 4.1.1)
-   **Qué hace este ajuste:** Este es un duplicado del ajuste "Número de productos a mostrar" (`HOME_FEATURED_PRO_NBR`). Controla el mismo aspecto: cuántos productos destacados aparecen en tu página de inicio.
-   **Efecto de cambiar este ajuste:** Cambiar esto alterará directamente el recuento de productos mostrados en la sección destacada.
-   **Valor recomendado:** Consulta la sección 4.1.1.
-   **Escenario / ejemplo de comerciante:** Consulta la sección 4.1.1.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del Módulo | Número de productos a mostrar (`HOME_FEATURED_PRO_NBR`) | 8-12 (depende del diseño) | Establece el recuento de productos destacados en la página de inicio. |
| Configuración del Módulo | Mostrar atributos en la página del producto (`PS_ATTRIBUTE_CATEGORY_DISPLAY`) | Sí | Controla la visibilidad de los atributos del producto en las páginas de productos. |
| Configuración del Módulo | Idioma predeterminado (`PS_LANG_DEFAULT`) | Idioma principal de tu tienda | Especifica el idioma predeterminado para la tienda. |
| Configuración del Módulo | Número de productos a mostrar (`HOME_FEATURED_NBR`) | Igual que `HOME_FEATURED_PRO_NBR` | Ajuste duplicado para el recuento de productos destacados. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: El efecto de cambio de imagen no funciona en mi página de inicio.**
R:
1.  **Verifica el Estado del Módulo:** Asegúrate de que el módulo "HomeFeatured Pro Rollover" esté instalado y habilitado en **Módulos > Gestor de Módulos**.
2.  **Borra la Caché:** Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché antigua impide que aparezcan los nuevos cambios del módulo.
3.  **Imágenes del Producto:** Verifica que los productos destacados tengan *al menos dos* imágenes subidas en su configuración de producto (**Catálogo > Productos > [Editar Producto] > pestaña Imágenes**). El módulo necesita una segunda imagen para mostrar al pasar el ratón.
4.  **Compatibilidad del Tema:** Aunque el módulo está diseñado para una amplia compatibilidad, los temas muy personalizados podrían requerir pequeños ajustes de CSS. Si el problema persiste, contacta con el soporte de MyPresta.eu.

**P: Mi página de inicio se ve rota después de la instalación.**
R:
1.  **Acción Inmediata:** Si tu tienda se vuelve inutilizable, desactiva el módulo inmediatamente desde **Módulos > Gestor de Módulos**.
2.  **Verifica la Versión de PrestaShop:** Asegúrate de haber descargado la versión correcta del módulo para tu instalación de PrestaShop (por ejemplo, la versión para PS 8.x para PrestaShop 8.x).
3.  **Conflictos de Tema:** Algunos temas pueden tener su propia lógica de "productos destacados" que entra en conflicto. Intenta cambiar temporalmente al tema predeterminado de PrestaShop (Classic) para ver si el problema se resuelve. Si lo hace, el problema está relacionado con el tema.
4.  **Contacta con Soporte:** Proporciona al soporte de MyPresta.eu detalles sobre tu versión de PrestaShop, tema y cualquier mensaje de error que veas.

**P: ¿Cómo cambio qué productos son "destacados"?**
R: El módulo utiliza el mecanismo estándar de "Productos Destacados" de PrestaShop. Para cambiar qué productos aparecen:
1.  Ve a **Catálogo > Categorías**.
2.  Encuentra la categoría llamada "Inicio" (o la categoría que hayas designado como tu categoría de página de inicio).
3.  Edita esta categoría y ve a la pestaña "Productos".
4.  Puedes añadir o eliminar productos de esta categoría para controlar lo que aparece en tu sección destacada.

**P: Las imágenes no están perfectamente alineadas o dimensionadas durante el cambio de imagen.**
R: Esto generalmente indica un conflicto de CSS con tu tema.
1.  **Dimensiones de la Imagen:** Asegúrate de que todas las imágenes del producto (especialmente la primera y la segunda) se suban con relaciones de aspecto consistentes y dimensiones similares. PrestaShop las redimensiona automáticamente, pero grandes diferencias pueden causar cambios en el diseño.
2.  **Personalización del Tema:** El CSS de tu tema podría estar anulando el estilo del módulo. Un webmaster puede inspeccionar el elemento usando las herramientas de desarrollador del navegador para identificar las reglas CSS en conflicto y aplicar una solución en el archivo CSS personalizado de tu tema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura
El módulo HomeFeatured Pro Rollover (`homefeaturedpro`) es un módulo sencillo de PrestaShop diseñado para anular y mejorar la funcionalidad del módulo predeterminado `homefeatured`. Se centra principalmente en la visualización del front-office, inyectando específicamente JavaScript y CSS para habilitar el efecto de cambio de imagen al pasar el ratón en los productos destacados de la página de inicio. Aprovecha el sistema de hooks de PrestaShop para integrar su lógica y plantillas. El módulo no introduce nuevas tablas de base de datos ni ObjectModels complejos, sino que se basa en los datos de productos existentes de PrestaShop.

### 4.2 Controladores (`controllers/`)
Este módulo no introduce ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la configuración se maneja a través del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)
Este módulo no introduce ninguna clase u ObjectModels personalizados. Opera extendiendo la funcionalidad existente de PrestaShop y renderizando sus propias plantillas.

### 4.4 Activos JavaScript (`views/js/`)
Este módulo no incluye ningún archivo JavaScript personalizado. El efecto de cambio de imagen se logra puramente a través de CSS.

### 4.5 Hojas de Estilo CSS (`views/css/`)
-   **`homefeaturedpro/homefeatured.css`**
    *   **Alcance:** Estilo del front-office para el cliente.
    *   **Componentes de UI principales y contenedores que estiliza:** Esta hoja de estilo contiene las reglas CSS principales responsables del efecto de cambio de imagen al pasar el ratón. Se dirige a los contenedores de imágenes de productos dentro de la sección de productos destacados, probablemente utilizando selectores como `.product-container .product-image`, `.product-image-container`, o similares, para ocultar la segunda imagen por defecto y mostrarla al pasar el ratón.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:**
        *   `.product-image-container .img-hover`: Probablemente controla la visibilidad y el posicionamiento de la segunda imagen.
        *   `.product-image-container .img-primary`: Controla la imagen principal.
        *   Estilos relacionados con las propiedades `transition` para cambios de imagen suaves.
        *   `overflow: hidden` en el contenedor de la imagen para gestionar el intercambio de imágenes.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`homefeaturedpro/homefeatured.tpl`**
    *   **Alcance:** Front-office.
    *   **Hook:** Principalmente renderizado en `displayHome` o `Home` (dependiendo de la versión de PrestaShop y la configuración del tema).
    *   **Propósito:** Esta es la plantilla principal responsable de renderizar la cuadrícula de productos destacados en la página de inicio. Itera a través de la variable `$products` (pasada desde el método `hookDisplayHome` del módulo) y para cada producto, genera la estructura HTML que incluye las imágenes primaria y secundaria, el nombre del producto, el precio y otros detalles. Está diseñada para funcionar con PrestaShop 1.7.x y versiones más recientes. La lógica dentro de esta plantilla es crucial para mostrar ambas imágenes y aplicar las clases CSS necesarias para el efecto de cambio de imagen.

-   **`homefeaturedpro/homefeatured14.tpl`**
    *   **Alcance:** Front-office.
    *   **Hook:** Probablemente destinado a versiones anteriores de PrestaShop (por ejemplo, 1.4.x, 1.5.x, 1.6.x) si el módulo las soporta, o como una alternativa para estructuras de tema específicas.
    *   **Propósito:** Esta plantilla tiene el mismo propósito que `homefeatured.tpl` pero está estructurada para ser compatible con sintaxis de plantillas y estructuras HTML de PrestaShop más antiguas. También iteraría a través de los productos y renderizaría los elementos de imagen necesarios para el efecto de cambio de imagen. Para las versiones modernas de PrestaShop (1.7+), `homefeatured.tpl` es la plantilla principal utilizada.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    *   El módulo no crea ninguna tabla de base de datos personalizada.
    *   Almacena sus ajustes de configuración en la tabla `ps_configuration` utilizando las siguientes claves:
        *   `HOME_FEATURED_PRO_NBR`: Almacena el número de productos destacados a mostrar.
        *   `PS_ATTRIBUTE_CATEGORY_DISPLAY`: (Configuración estándar de PrestaShop, potencialmente referenciada o establecida por el módulo).
        *   `PS_LANG_DEFAULT`: (Configuración estándar de PrestaShop, potencialmente referenciada o establecida por el módulo).
        *   `HOME_FEATURED_NBR`: (Duplicado de `HOME_FEATURED_PRO_NBR`, probablemente para compatibilidad con versiones anteriores o consistencia interna).

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir la hoja de estilo CSS del módulo (`homefeatured.css`) para asegurar que los estilos de cambio de imagen se carguen antes del contenido de la página. |
| `header` | Alias de `displayHeader`. | Igual que `displayHeader`. |
| `Home` | En la página de inicio, típicamente en el área de contenido principal. | Renderiza la plantilla de productos destacados del módulo (`homefeatured.tpl` o `homefeatured14.tpl`) y le pasa los datos del producto. |
| `displayHome` | Alias de `Home` en versiones modernas de PrestaShop. | Igual que `Home`. |

## 5. Soporte Oficial y Actualizaciones
Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo HomeFeatured Pro Rollover, visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener.
