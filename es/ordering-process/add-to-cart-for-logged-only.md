---
title: "Añadir al carrito solo para usuarios registrados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Añadir al carrito solo para usuarios registrados' de MyPresta.eu."
sidebar:
  label: "Añadir al carrito solo para usuarios registrados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Add to cart for logged only en MyPresta.eu](https://mypresta.eu/modules/ordering-process/add-to-cart-for-logged-only.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/add-to-cart-for-logged-only/)
>
> ---


# Añadir al carrito solo para usuarios registrados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Añadir al carrito solo para usuarios registrados" para acceder a sus ajustes.

#### **Mostrar**

- **Qué hace este ajuste:** Este es el interruptor principal para habilitar o deshabilitar la funcionalidad principal del módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (Sí):* El módulo estará activo. Los usuarios no registrados no podrán añadir productos a su carrito, y se mostrará un mensaje pidiéndoles que inicien sesión.
  - *Cuando está deshabilitado (No):* El módulo estará inactivo. Todos los usuarios, ya sea que hayan iniciado sesión o no, podrán añadir productos a su carrito según el comportamiento estándar de PrestaShop.
- **Valor recomendado:** **Sí** si desea aplicar la regla de carrito "solo para usuarios registrados". **No** si desea deshabilitar temporalmente la función sin desinstalar el módulo.
- **Escenario / ejemplo de comerciante:** Si tiene una tienda B2B y solo desea que sus clientes comerciales registrados realicen pedidos, lo configuraría en "Sí". Si está abriendo temporalmente su tienda a la navegación pública y a las adiciones al carrito para una promoción especial, podría configurarlo en "No" durante ese período.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar | Sí | Habilita/deshabilita la funcionalidad principal del módulo, restringiendo "Añadir al carrito" a usuarios registrados. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero los usuarios no registrados aún pueden añadir productos al carrito. ¿Qué está mal?**
R:

1. **Borrar caché:** El problema más común es el almacenamiento en caché. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
2. **Posición del módulo:** Asegúrese de que el módulo esté enganchado correctamente. Aunque el módulo lo maneja automáticamente, a veces los conflictos de tema pueden interferir. Verifique la configuración del módulo y asegúrese de que esté activo.
3. **Compatibilidad del tema:** Muy raramente, un tema altamente personalizado podría anular los comportamientos estándar del botón de PrestaShop. Si borrar la caché no funciona, cambie temporalmente al tema predeterminado de PrestaShop (por ejemplo, Classic) para ver si el problema persiste. Si se resuelve, es probable que su tema esté causando un conflicto, y es posible que necesite un desarrollador para investigar.

**P: ¿Puedo personalizar el mensaje que se muestra a los usuarios no registrados?**
R: Sí, el mensaje suele ser traducible. Vaya a **Internacional > Traducciones** en su Back Office. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Añadir al carrito solo para usuarios registrados". Debería encontrar la cadena de texto allí para modificarla para cada idioma.

**P: ¿Este módulo afectará mi SEO?**
R: No, este módulo afecta principalmente la funcionalidad del botón "Añadir al carrito" para los usuarios del front-end. No impide que los rastreadores de los motores de búsqueda indexen sus páginas de productos o contenido. Sus productos seguirán siendo visibles y detectables.

**P: ¿Qué sucede si un cliente cierra sesión después de añadir artículos al carrito?**
R: El módulo impide *añadir* al carrito cuando no se ha iniciado sesión. Si un cliente inicia sesión, añade artículos y luego cierra sesión, los artículos suelen permanecer en su carrito (asociados a su cuenta) para cuando vuelva a iniciar sesión. La restricción del módulo se aplica a la acción de añadir nuevos artículos mientras no se ha iniciado sesión.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Añadir al carrito solo para usuarios registrados" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo "Añadir al carrito solo para usuarios registrados" es un módulo ligero de PrestaShop diseñado principalmente para interceptar y modificar el comportamiento de la acción "Añadir al carrito" en función del estado de inicio de sesión del usuario. Lo logra aprovechando el sistema de hooks de PrestaShop e inyectando JavaScript para deshabilitar o modificar el botón "Añadir al carrito" y mostrar un mensaje a los usuarios no registrados. No introduce nuevas tablas de base de datos ni modelos de objetos complejos, centrándose en la interacción del front-end y las funcionalidades principales existentes de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de Front-Office o Back-Office Admin personalizados. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase personalizada ni extiende `ObjectModel`. Su lógica está contenida principalmente dentro del archivo principal `cartforlogged.php`.

### 4.4 Activos JavaScript (`views/js/`)

- **`cartforlogged/views/js/cfl-17500.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este script está probablemente diseñado para las versiones de PrestaShop 1.7.x y 8.x (indicado por `17500`). Se dirige al botón "Añadir al carrito" (`#add_to_cart button`, `.add-to-cart`) y potencialmente a otros elementos como las entradas de cantidad.
  - **Funcionalidad:**
    - Comprueba si el usuario ha iniciado sesión (`isLogged`).
    - Si no ha iniciado sesión, deshabilita el botón "Añadir al carrito", cambia su texto (por ejemplo, a "Solo usuarios registrados...") y potencialmente añade una clase CSS para darle un estilo visual de deshabilitado.
    - También podría evitar el envío de formularios o las llamadas AJAX relacionadas con la adición de productos al carrito.
    - Es probable que utilice `prestashop.on('updateCart', ...)` o detectores de eventos similares para volver a aplicar su lógica después de las actualizaciones del carrito o los cambios de página (por ejemplo, cuando se cambian los atributos del producto).
- **`cartforlogged/views/js/cfl.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este script es probablemente una versión más genérica o de respaldo, potencialmente para versiones anteriores de PrestaShop (1.5.x, 1.6.x) o como base para el más específico `cfl-17500.js`.
  - **Funcionalidad:** Similar a `cfl-17500.js`, identifica el botón "Añadir al carrito" (por ejemplo, `#add_to_cart button`, `.exclusive button`), comprueba el estado de inicio de sesión y deshabilita el botón para los usuarios no registrados. Podría usar `$(document).ready()` de jQuery y la delegación de eventos para manejar contenido dinámico.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`cartforlogged/views/css/cfl.css`**
  - **Alcance:** Estilo del cliente del front-office.
  - **Propósito:** Proporciona un estilo básico para el botón "Añadir al carrito" deshabilitado o el mensaje que se muestra a los usuarios no registrados.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:**
    - `.cfl_disabled_button`: Probablemente aplicado al botón "Añadir al carrito" cuando está deshabilitado por el módulo. Los desarrolladores pueden usar esto para cambiar el color de fondo, el cursor, la opacidad, etc., para indicar claramente que está inactivo.
    - `.cfl_message`: Si el módulo inyecta un elemento de mensaje específico, esta clase lo estilizaría.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`cartforlogged/views/templates/admin/json.tpl`**
  - **Alcance:** Plantillas de administración.
  - **Propósito:** Esta plantilla es probablemente utilizada internamente por el método `getContent()` del módulo para generar datos JSON, posiblemente para solicitudes AJAX dentro de la página de configuración o para actualizaciones dinámicas de contenido. No es una plantilla visible en el front-office. Podría usarse para devolver el estado de la configuración u otros datos al JavaScript en la página de administración.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones (por ejemplo, `CFL_LOGIN`) en la tabla estándar `ps_configuration`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir activos CSS y JavaScript (`cfl.css`, `cfl.js`, `cfl-17500.js`) que modifican el comportamiento del botón "Añadir al carrito". |
| `actionCartSave` | Después de que un carrito se guarda o actualiza. | Este hook podría usarse potencialmente para reevaluar el contenido del carrito o aplicar restricciones, pero dada la descripción del módulo, su función principal es probablemente la inyección de JS en el front-end a través de `displayHeader`. Podría ser un respaldo o una forma de asegurar la validación del lado del servidor, aunque la descripción del módulo enfatiza el lado del cliente. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se están configurando sus medios (JS/CSS). | Se utiliza para incluir cualquier JavaScript o CSS necesario para la página de configuración del Back Office del módulo. |
| `header` | Similar a `displayHeader`, a menudo se usa indistintamente o para temas heredados específicos. | Se utiliza para incluir activos CSS y JavaScript, asegurando la compatibilidad entre diferentes versiones y temas de PrestaShop. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Añadir al carrito solo para usuarios registrados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
