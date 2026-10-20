---
title: "Integración con Shopmania - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Integración con Shopmania' de MyPresta.eu."
sidebar:
  label: "Integración con Shopmania"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Shopmania Integration en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/shopmania-integration.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/shopmania-integration/)
>
> ---


# Integración con Shopmania

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para el funcionamiento general de PrestaShop, pero este módulo tiene requisitos específicos mínimos más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Después de la instalación, haga clic en "Configurar" junto al módulo "Integración con Shopmania" en su Gestor de Módulos. Esto le llevará a la página de configuración principal.

El módulo de Integración con Shopmania está diseñado para ser muy sencillo, a menudo requiriendo una configuración mínima, ya que se centra principalmente en generar un feed de productos.

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|
| **URL del Feed de ShopMania** | Generado automáticamente | Este es el enlace directo al feed de productos generado por su módulo. Deberá copiar esta URL y proporcionársela a ShopMania al configurar su cuenta de comerciante con ellos. Esta URL es la que ShopMania utilizará para obtener regularmente los datos de sus productos. |

**Qué hace este ajuste:**
Esta sección muestra la URL que ShopMania utilizará para acceder a su feed de datos de productos. Este feed contiene toda la información necesaria sobre sus productos (nombre, descripción, precio, imágenes, disponibilidad, etc.) en un formato que ShopMania puede entender y mostrar en su plataforma.

**Efecto de cambiar este ajuste:**
No puede cambiar directamente esta URL. Se genera automáticamente por el módulo basándose en el dominio de su tienda y la lógica interna del módulo.

**Valor recomendado:**
Copie esta URL exactamente como aparece. No la modifique.

**Escenario / ejemplo de comerciante:**
Después de instalar y configurar el módulo, iniciará sesión en su cuenta de comerciante de ShopMania (o creará una). ShopMania le pedirá la "URL del Feed de Productos" o "URL del Feed de Datos". Luego, pegará la URL proporcionada en esta página de configuración en el campo correspondiente en el sitio web de ShopMania. ShopMania visitará periódicamente esta URL para actualizar sus listados de productos en su plataforma.

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis productos no aparecen en ShopMania. ¿Qué debo hacer?**
R:
1.  **Verifique la URL del Feed:** Asegúrese de haber copiado y pegado correctamente la URL exacta del feed de la página de configuración del módulo en la configuración de su cuenta de comerciante de ShopMania.
2.  **Tiempo de Procesamiento de ShopMania:** Puede llevar algún tiempo (horas o incluso algunos días) que ShopMania procese su feed por primera vez. Sea paciente.
3.  **Accesibilidad del Feed:** Intente abrir la URL del feed en su navegador web. ¿Carga? ¿Muestra datos de productos? Si muestra un error o una página en blanco, podría haber un problema del lado del servidor o un problema con el proceso de generación del módulo. Contacte con el soporte de MyPresta.eu.
4.  **Visibilidad del Producto:** Asegúrese de que sus productos estén activos, en stock y visibles en su tienda PrestaShop. Los productos que están deshabilitados o agotados podrían no incluirse en el feed.

**P: ¿Este módulo actualiza automáticamente los precios y el stock en ShopMania?**
R: Sí, el feed generado por este módulo reflejará los precios y niveles de stock actuales de su tienda PrestaShop. ShopMania volverá a obtener este feed periódicamente para mantener sus listados actualizados. La frecuencia de las actualizaciones depende del programa de obtención de ShopMania, que podría configurar en su cuenta de comerciante de ShopMania.

**P: ¿Puedo elegir qué productos se incluyen en el feed?**
R: La versión básica de este módulo suele incluir todos los productos activos y visibles. Si necesita un filtrado avanzado (por ejemplo, excluir categorías o productos específicos), esto requeriría un desarrollo personalizado o un módulo de gestión de feeds más avanzado. El módulo "Integración con Shopmania" se centra en una integración sencilla de catálogo completo.

**P: Veo un error al intentar configurar el módulo.**
R:
1.  **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** en el back office de su PrestaShop y haga clic en "Borrar caché". A veces, los archivos de caché antiguos pueden interferir con la configuración del módulo.
2.  **Verificar Registros de Errores del Servidor:** Si el problema persiste, revise los registros de errores PHP de su servidor. Estos registros pueden proporcionar detalles técnicos específicos sobre lo que salió mal. Es posible que deba ponerse en contacto con su proveedor de alojamiento o un desarrollador para esto.
3.  **Contactar con Soporte:** Si sigue teniendo problemas, recopile cualquier mensaje de error o captura de pantalla y póngase en contacto con el soporte de MyPresta.eu para obtener ayuda.

**P: ¿Qué pasa si mi tema personalizado causa problemas de visualización (aunque este módulo no tiene visualización en el front-office)?**
R: Dado que este módulo no tiene visualización en el front-office, es muy poco probable que cause problemas visuales con su tema personalizado. Su funcionamiento es puramente de backend, generando un archivo de datos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)
Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura
El módulo `Integración con Shopmania` es un módulo de PrestaShop simple de un solo archivo diseñado para generar un feed de productos XML compatible con la plataforma ShopMania. Sigue una estructura de módulo estándar de PrestaShop, utilizando principalmente los métodos `install()` y `uninstall()` para la configuración y el método `getContent()` para su configuración de back-office, que en este caso, simplemente muestra la URL del feed generado. La lógica central reside dentro del archivo principal del módulo, responsable de generar dinámicamente el feed XML cuando se accede a la URL específica del feed. No utiliza controladores personalizados, modelos o archivos de plantilla dedicados para su funcionalidad principal, confiando en la salida directa para el feed.

### 4.2 Controladores (`controllers/`)
-   **Controladores de Front-Office**: Ninguno. El feed de productos es generado directamente por el archivo principal del módulo cuando se accede a su URL específica, en lugar de a través de un `ModuleFrontController` dedicado.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración (mostrar la URL del feed) se maneja dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)
-   No hay clases personalizadas o definiciones de `ObjectModel` presentes en este módulo. Toda la lógica está contenida dentro de la clase `ShopmaniaIntegration` en el archivo principal del módulo.

### 4.4 Activos JavaScript (`views/js/`)
-   Este módulo no incluye ni utiliza archivos JavaScript.

### 4.5 Hojas de Estilo CSS (`views/css/`)
-   Este módulo no incluye ni utiliza archivos CSS.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)
-   Este módulo no utiliza archivos de plantilla Smarty (`.tpl`) personalizados. El método `getContent()` genera directamente el HTML para la página de configuración, y el feed de productos se genera como XML sin formato.

### 4.7 Esquema de Base de Datos y Mapa de Hooks
-   **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración (si fuera necesaria más allá de la URL del feed) en la tabla estándar `ps_configuration`, aunque para este módulo, la URL del feed se genera dinámicamente y no se almacena como un valor de configuración.
-   **Tabla de Hooks Registrados**:
    Este módulo no registra explícitamente ningún hook en el método `install()` para visualización o acción en el front-office. Su función principal es responder a una solicitud de URL directa para el feed XML. Si bien la descripción de la característica menciona "Hooks de Front-Office: Cabecera, Columnas, Producto o Pie de página", es probable que sea una descripción genérica para módulos que *podrían* usarlos, pero este módulo específico no implementa ningún componente visual de front-office. Su integración se basa puramente en el feed de datos.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayBackOfficeHeader` | Se ejecuta al renderizar la cabecera del Back Office. | Se utiliza para incluir CSS/JS específicos del módulo para la página de configuración (aunque este módulo no utiliza ninguno). |
| `displayHeader` | Se ejecuta en la sección `<head>` de las páginas del front-office. | (No utilizado por este módulo para la salida visual, pero podría usarse para metaetiquetas o scripts si fuera necesario). |
| `displayRightColumn` | Se ejecuta en la columna derecha de las páginas del front-office. | (No utilizado por este módulo). |
| `displayLeftColumn` | Se ejecuta en la columna izquierda de las páginas del front-office. | (No utilizado por este módulo). |
| `displayProductAdditionalInfo` | Se ejecuta en la página del producto. | (No utilizado por este módulo). |
| `displayFooter` | Se ejecuta en el pie de página de las páginas del front-office. | (No utilizado por este módulo). |

La funcionalidad principal del módulo (generar el feed XML) se activa cuando se accede a la URL específica del feed (por ejemplo, `tutienda.com/modules/shopmania-integration/shopmania-feed.php` o similar, dependiendo del enrutamiento de PrestaShop). Esto no es un hook estándar de PrestaShop, sino una solicitud HTTP directa a un endpoint específico del módulo.

## 5. Soporte Oficial y Actualizaciones
Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo de Integración con Shopmania, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con problemas relacionados con el módulo y asegurar que su integración funcione sin problemas.
