---
title: "Hooks Manager - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Hooks Manager de PrestaShop por MyPresta.eu."
sidebar:
  label: "Hooks Manager - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Hooks Manager en MyPresta.eu](https://mypresta.eu/modules/administration-tools/hooks-manager.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/hooks-manager/)
>
> ---


# Hooks Manager

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo Hooks Manager. Verá una lista de todos los hooks personalizados que ha creado, junto con opciones para añadir nuevos.

#### Añadiendo un Nuevo Hook Personalizado:

En la parte superior de la página de configuración, encontrará los campos para crear un nuevo hook.

- **Nombre del Hook:**

  - **Qué hace esta configuración:** Este es el nombre técnico único para su nuevo hook. Debe comenzar con `display` (por ejemplo, `displayMyCustomHook`, `displayProductExtraInfo`). Este nombre es el que utilizará más tarde en los archivos `.tpl` de su tema para "llamar" al hook.
  - **Efecto de cambiar esta configuración:** Este nombre es crucial para que los desarrolladores coloquen el hook en su tema. Cambiarlo después de la creación requeriría actualizar los archivos de su tema.
  - **Valor recomendado:** Use nombres descriptivos en camelCase que comiencen con `display`. Ejemplo: `displayProductBelowAddToCart`, `displayHomepagePromoBanner`.
  - **Escenario / ejemplo de comerciante:** Desea añadir un banner debajo del botón "Añadir al carrito" en las páginas de producto. Podría nombrar el hook `displayProductBelowAddToCart`.
- **Título del Hook:**

  - **Qué hace esta configuración:** Este es un título amigable y legible para su hook que aparecerá en su Back Office de PrestaShop (por ejemplo, cuando vaya a **Diseño > Posiciones** para asignar módulos a hooks).
  - **Efecto de cambiar esta configuración:** Facilita la identificación de su hook personalizado entre los muchos hooks estándar en el Back Office.
  - **Valor recomendado:** Un título claro y descriptivo. Ejemplo: "Página de Producto - Debajo de Añadir al Carrito", "Página de Inicio - Banner Promocional Superior".
  - **Escenario / ejemplo de comerciante:** Para el hook `displayProductBelowAddToCart`, establecería el título en "Página de Producto - Debajo de Añadir al Carrito".
- **Descripción del Hook:**

  - **Qué hace esta configuración:** Una descripción opcional más larga para proporcionar más contexto sobre el propósito o la ubicación prevista del hook. Esto también es para uso interno en el Back Office.
  - **Efecto de cambiar esta configuración:** Le ayuda a usted y a su equipo a recordar el caso de uso específico para cada hook personalizado.
  - **Valor recomendado:** Explique brevemente dónde se pretende colocar el hook y qué tipo de contenido debe contener. Ejemplo: "Destinado a insignias de confianza o pequeños mensajes promocionales directamente debajo del botón de añadir al carrito."
  - **Escenario / ejemplo de comerciante:** Para el hook `displayProductBelowAddToCart`, podría añadir "Usar para pequeñas insignias de confianza o un mensaje de envío gratuito."
- **Visibilidad:**

  - **Qué hace esta configuración:** Esto determina si el hook es visible en la lista de hooks disponibles cuando va a **Diseño > Posiciones** en su Back Office de PrestaShop.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* El hook aparecerá en la lista, permitiéndole asignar módulos fácilmente.
    - *Cuando está deshabilitado:* El hook seguirá existiendo y funcionando si se llama en su tema, pero no aparecerá en la lista "Diseño > Posiciones", lo que dificulta la gestión de módulos para él.
  - **Valor recomendado:** **Habilitado (Sí)**, a menos que tenga una razón muy específica para ocultarlo.
  - **Escenario / ejemplo de comerciante:** Ha creado un nuevo hook y desea comenzar a asignarle módulos de inmediato. Manténgalo habilitado.

#### Gestionando Hooks Personalizados Existentes:

Debajo de la sección "Añadir Nuevo Hook", verá una tabla que enumera todos los hooks personalizados que ha creado.

- **Interruptor Habilitado / Deshabilitado (para cada hook):**

  - **Qué hace esta configuración:** Este interruptor le permite activar o desactivar un hook personalizado individual.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* El hook está activo, y cualquier módulo asignado a él renderizará su contenido cuando el hook sea llamado en su tema.
    - *Cuando está deshabilitado:* El hook está inactivo. Incluso si se llama en su tema, no renderizará ningún contenido de los módulos asignados a él. Esta es una forma suave de ocultar temporalmente el contenido sin desenganchar módulos.
  - **Valor recomendado:** **Habilitado** para los hooks que desea usar, **Deshabilitado** para los hooks que desea ocultar temporalmente.
  - **Escenario / ejemplo de comerciante:** Tiene un banner de promoción estacional colocado a través de un hook personalizado. Cuando la promoción termina, puede deshabilitar el hook para ocultar el banner sin eliminar el módulo.
- **Edición en Vivo (para cada hook):**

  - **Qué hace esta configuración:** Este es un enlace rápido a la página "Diseño > Posiciones", filtrado para mostrar solo el hook personalizado seleccionado.
  - **Efecto de cambiar esta configuración:** Al hacer clic en este botón, se le dirigirá directamente a la página donde puede "enganchar" (asignar) otros módulos a este hook personalizado específico.
  - **Valor recomendado:** Use este botón siempre que desee asignar un módulo a su hook personalizado recién creado.
  - **Escenario / ejemplo de comerciante:** Acaba de crear `displayProductBelowAddToCart` y ahora desea asignar su módulo de "Insignias de Confianza" a él. Haga clic en "Edición en Vivo" junto a `displayProductBelowAddToCart`.

#### Otras Claves de Configuración (Internas):

Es posible que vea `mypresta_updates`, `update_`, `updatev_` en la configuración interna del módulo. Estos suelen estar relacionados con las actualizaciones del módulo y las comprobaciones de licencia de MyPresta.eu y no requieren la interacción del comerciante.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Nombre del Hook | Descriptivo, prefijo `display` | Identificador técnico único para el hook. Usado en archivos de tema. |
| Configuración del Módulo | Título del Hook | Claro, legible para humanos | Aparece en Diseño > Posiciones para una fácil identificación. |
| Configuración del Módulo | Descripción del Hook | Opcional, informativa | Proporciona contexto para el propósito del hook. |
| Configuración del Módulo | Visibilidad | Habilitado (Sí) | Hace que el hook sea visible en Diseño > Posiciones para la asignación de módulos. |
| Configuración del Módulo | Habilitado / Deshabilitado (por hook) | Habilitado | Activa/desactiva la capacidad del hook personalizado para renderizar contenido. |
| Configuración del Módulo | Edición en Vivo (por hook) | N/A (Botón de acción) | Enlace directo a Diseño > Posiciones para asignar módulos al hook. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: He creado un hook y asignado un módulo, pero no aparece nada en mi tienda. ¿Qué pasa?**
R: Este es el problema más común. El módulo Hooks Manager *crea* el hook, pero usted (o su webmaster) aún necesita *colocar* ese hook en los archivos `.tpl` de su tema.
- **Solución:** Debe editar los archivos de su tema (por ejemplo, `product.tpl`, `index.tpl`, `header.tpl`, `footer.tpl`) e insertar el siguiente fragmento de código donde desea que aparezca el hook: `{$hook_name}`. Reemplace `hook_name` con el nombre real de su hook (por ejemplo, `{$hook_displayProductBelowAddToCart}`).
- **También verifique:**
1. ¿Está el hook "Habilitado" en la configuración de Hooks Manager?
2. ¿Está el módulo que intenta mostrar realmente "enganchado" a su hook personalizado en **Diseño > Posiciones**?
3. ¿Ha vaciado la caché de PrestaShop (**Parámetros Avanzados > Rendimiento**)?

**P: ¿Puedo usar el mismo hook personalizado varias veces en diferentes lugares?**
R: Sí, puede. Si coloca `{$hook_displayMyCustomHook}` en `product.tpl` y también en `category.tpl`, cualquier módulo asignado a `displayMyCustomHook` se renderizará en ambas ubicaciones. Esto es potente para mostrar contenido consistente en diferentes tipos de páginas.

**P: Mi hook personalizado aparece, pero el estilo es incorrecto. ¿Qué puedo hacer?**
R: El módulo Hooks Manager solo proporciona la "ranura". El estilo del contenido dentro de esa ranura lo determina el módulo que ha colocado allí y el CSS de su tema.
- **Solución:** Es posible que deba añadir CSS personalizado a su tema para estilizar el contenido renderizado por el módulo en su hook personalizado. Su webmaster puede ayudar con esto.

**P: Quiero eliminar un hook personalizado. ¿Cómo lo hago de forma segura?**
R: En la configuración de Hooks Manager, verá un botón "Eliminar" junto a cada hook personalizado.
- **Importante:** Antes de eliminar, asegúrese de haber eliminado cualquier llamada a ese hook (`{$hook_yourCustomHookName}`) de los archivos `.tpl` de su tema. Si elimina el hook pero deja la llamada en su tema, podría causar un error menor o simplemente no renderizar nada. Además, desenganche cualquier módulo de él a través de **Diseño > Posiciones**.

**P: ¿Este módulo afecta el rendimiento de mi tienda?**
R: El módulo en sí es muy ligero. Añadir más hooks y asignar más módulos *puede* aumentar incrementalmente el tiempo de carga de la página, pero esto es cierto para cualquier contenido adicional en su página, independientemente de cómo esté enganchado. El impacto es generalmente insignificante a menos que esté añadiendo docenas de módulos complejos a una sola página.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo Hooks Manager es un módulo PrestaShop sencillo diseñado para extender el mecanismo de enganche central. Principalmente aprovecha la clase `Module` de PrestaShop y la tabla `Configuration` para gestionar las definiciones de hooks personalizados. No introduce patrones MVC complejos ni tablas de base de datos personalizadas, sino que manipula las tablas `ps_hook` y `ps_hook_module` indirectamente a través de la API de PrestaShop. La funcionalidad principal del módulo reside en su archivo PHP principal, `hooksmanager.php`, que maneja la instalación, desinstalación y la interfaz de configuración del Back Office.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. Toda la renderización del front-office es manejada por el método estándar `Hook::exec()` de PrestaShop cuando el hook personalizado es llamado en un archivo `.tpl`.
- **Controladores de Administración del Back-Office**: Ninguno. Toda la administración se maneja directamente dentro del método `getContent()` del archivo `hooksmanager.php`.

### 4.3 Clases y Modelos Centrales (`classes/`)

- No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/`. El módulo interactúa directamente con las clases centrales `Hook` y `Module` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

- No hay archivos JavaScript personalizados presentes en el módulo. La configuración del Back Office se basa en elementos de formulario estándar de PrestaShop y potencialmente jQuery si se incluye globalmente por PrestaShop.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- No hay archivos CSS personalizados presentes en el módulo. La configuración del Back Office utiliza el estilo predeterminado del tema de administración de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- No hay archivos de plantilla Smarty personalizados presentes en el módulo. Toda la interfaz de configuración se renderiza directamente dentro del método `getContent()` de `hooksmanager.php` utilizando HTML sin procesar y las clases de ayuda de PrestaShop.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea sus propias tablas de base de datos personalizadas.
  - Principalmente interactúa con las siguientes tablas centrales de PrestaShop:
    - `ps_hook`: Almacena las definiciones de todos los hooks, incluidos los creados por este módulo.
    - `ps_hook_lang`: Almacena los títulos y descripciones traducibles para los hooks.
    - `ps_module_hook`: Vincula módulos a hooks, definiendo qué módulo se muestra en qué hook.
    - `ps_configuration`: Almacena valores de configuración específicos del módulo (por ejemplo, `mypresta_updates`, `update_`, `updatev_` para la gestión interna del módulo).
- **Tabla de Hooks Registrados**:
  El módulo en sí no registra ningún hook para mostrar su propio contenido. Su propósito es *crear* nuevos hooks para que otros módulos los utilicen.

  La funcionalidad principal del módulo implica:

  - `install()`:
    - Registra el módulo en `displayAdminProductsExtra` (o similar, aunque no se indica explícitamente en el dossier, esto es común para las herramientas de administración para mostrar un enlace).
    - Crea una nueva pestaña en el Back Office (si corresponde, aunque no se indica explícitamente para este módulo, es común para las herramientas de administración).
    - Establece valores de configuración predeterminados en `ps_configuration`.
  - `uninstall()`:
    - Elimina todos los hooks personalizados creados por el módulo de `ps_hook` y `ps_hook_lang`.
    - Elimina las entradas `ps_module_hook` asociadas.
    - Limpia los valores de configuración de `ps_configuration`.
  - `getContent()`:
    - Maneja el envío del formulario de configuración del Back Office.
    - Procesa la creación, actualización y eliminación de hooks personalizados.
    - Renderiza el HTML para la página de configuración, listando los hooks existentes y proporcionando el formulario para añadir nuevos.
    - Utiliza los métodos `Hook::add()` y `Hook::remove()` para gestionar las entradas de hooks en la base de datos.

  **Nota del Desarrollador sobre el Uso de Hooks Personalizados:**
  Para utilizar un hook personalizado creado por este módulo, un desarrollador debe insertar manualmente la variable Smarty `{$hook_YOUR_CUSTOM_HOOK_NAME}` en el archivo `.tpl` deseado dentro del tema activo de PrestaShop. Por ejemplo, si se crea un hook llamado `displayProductBelowAddToCart`, el desarrollador añadiría `{$hook_displayProductBelowAddToCart}` a `themes/your_theme/templates/catalog/_partials/product-details.tpl` o `product.tpl` en la ubicación deseada. El método `Hook::exec()` del núcleo de PrestaShop se encargará entonces de la renderización de los módulos asignados a este hook personalizado.

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Hooks Manager, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione de manera óptima y a ayudarle con cualquier consulta técnica que pueda tener.
