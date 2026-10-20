---
title: "Seguimiento de Allani - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Seguimiento de Allani' de MyPresta.eu."
sidebar:
  label: "Seguimiento de Allani - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Allani tracking en MyPresta.eu](https://mypresta.eu/modules/ordering-process/allani-tracking.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/allani-tracking/)
>
> ---


# Seguimiento de Allani

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5 (El módulo está diseñado para funcionar en una amplia gama de versiones de PHP, hasta la última versión estable compatible con PrestaShop 1.7.x y versiones futuras).
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) típicamente disponibles en cualquier entorno de alojamiento PrestaShop moderno.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Seguimiento de Allani" para acceder a sus ajustes.

#### Identificación de Pedidos

Esta sección controla cómo el módulo identifica y envía los datos de los pedidos a Allani.

- **Qué hace este ajuste:** Este es el ajuste principal del módulo. Determina si el módulo está activo y enviando datos de pedidos a Allani.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo enviará automáticamente los detalles del pedido (ID de producto, valor del pedido, ID del pedido) a la plataforma Allani cada vez que un cliente complete un pedido con éxito en su tienda PrestaShop. Esto es esencial para que Allani realice un seguimiento de sus ventas.
  - *Cuando está deshabilitado (NO):* El módulo dejará de enviar cualquier dato de pedido a Allani. Esto significa que Allani no recibirá actualizaciones en tiempo real sobre sus ventas, lo que podría afectar sus análisis e informes en su plataforma.
- **Valor recomendado:** **SÍ**. Para utilizar plenamente el servicio de seguimiento de Allani, este ajuste siempre debe estar habilitado.
- **Escenario / ejemplo de comerciante:** Si acaba de registrarse en Allani y desea comenzar a rastrear sus ventas de inmediato, habilitaría este ajuste. Si desea pausar temporalmente la transmisión de datos a Allani por motivos de mantenimiento o prueba, podría deshabilitarlo, pero recuerde volver a habilitarlo después.

#### Otros Ajustes Internos (No configurables directamente por el comerciante)

Es posible que vea otras claves de configuración como `mypresta_updates`, `update_`, `updatev_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Estos son ajustes internos utilizados por el módulo para sus propias comprobaciones de actualización o para interactuar con las funcionalidades principales de PrestaShop (como el manejo de idiomas). No necesita configurar estos, y no se exponen como opciones editables por el usuario.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Identificación de Pedidos | SÍ | Controla si los datos del pedido se envían a Allani. **Habilitar** para el seguimiento de Allani. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He instalado el módulo, pero no veo ningún cambio en mi tienda. ¿Está funcionando?**
R: ¡Sí, esto es normal! El módulo de seguimiento de Allani funciona completamente en segundo plano. No añade ningún elemento visible al front office de su tienda. Su función es enviar datos a Allani después de que se realiza un pedido. Para confirmar que funciona, realice un pedido de prueba y luego verifique su cuenta de Allani para ver los nuevos datos del pedido.

**P: Allani no está recibiendo los datos de mis pedidos. ¿Qué debo verificar?**
R:

1. **Módulo Habilitado:** Vaya a **Módulos > Gestor de módulos**, busque "Seguimiento de Allani" y asegúrese de que esté instalado y habilitado.
2. **Ajuste de Configuración:** Haga clic en "Configurar" para el módulo y asegúrese de que "Identificación de Pedidos" esté configurado en **SÍ**.
3. **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que los nuevos ajustes surtan efecto. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
4. **Cuenta de Allani:** Vuelva a verificar la configuración de su cuenta de Allani o póngase en contacto con el soporte de Allani para asegurarse de que su tienda esté correctamente vinculada en su sistema.
5. **Versión de PrestaShop:** Asegúrese de haber descargado la versión correcta del módulo para su instalación de PrestaShop (por ejemplo, 1.7.x, 1.6.x).

**P: ¿Este módulo ralentizará mi tienda?**
R: No, el impacto en el rendimiento de su tienda es insignificante. El script de seguimiento solo se ejecuta en la página de confirmación del pedido, que suele ser el último paso en el recorrido del cliente. La transferencia de datos es rápida y asíncrona, lo que significa que no retrasará la carga de la página para sus clientes.

**P: ¿Este módulo es compatible con configuraciones multi-idioma o multi-tienda?**
R: El módulo envía principalmente datos numéricos y de ID de producto, que son independientes del idioma. Para multi-tienda, siempre que el módulo esté habilitado y configurado para cada contexto de tienda donde desee rastrear pedidos, debería funcionar correctamente.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `Seguimiento de Allani` es un módulo ligero de PrestaShop diseñado para un único propósito: enviar datos de confirmación de pedidos a la plataforma Allani. Sigue una estructura de módulo estándar de PrestaShop, utilizando principalmente hooks para inyectar su lógica de seguimiento. La funcionalidad principal reside dentro de la clase principal del módulo (`allanitracking.php`), que maneja la instalación, desinstalación, configuración y registro de hooks. No introduce controladores personalizados, modelos o activos complejos de JavaScript/CSS, centrándose únicamente en la transmisión de datos a través de una plantilla Smarty inyectada en el hook `displayOrderConfirmation`.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. La lógica de front-office del módulo se maneja directamente dentro del hook `displayOrderConfirmation` a través de una plantilla Smarty.
- **Controladores de Administración de Back-Office**: Ninguno. La configuración se gestiona directamente a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- Este módulo no introduce clases personalizadas ni definiciones de `ObjectModel`. Toda la lógica está autocontenida dentro de `allanitracking.php`.

### 4.4 Activos de JavaScript (`views/js/`)

- Este módulo no incluye ni utiliza archivos JavaScript personalizados. El script de seguimiento se incrusta directamente en la plantilla `displayOrderConfirmation.tpl`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- Este módulo no incluye ni utiliza archivos CSS personalizados, ya que no tiene componentes visibles en el front-office.

### 4.6 Estructura de la Plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para inyectar el script de seguimiento en el front office.

- **Plantillas de Hook (`views/templates/hook/`)**:

  - `allanitracking/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Propósito**: Esta plantilla se renderiza en la página de confirmación del pedido (después de una compra exitosa). Contiene la lógica principal para enviar datos del pedido a Allani. Accede a las variables Smarty `$order` y `$products`, que PrestaShop pasa a este hook, para extraer `orderValue`, `orderID` y `productIds`. La plantilla luego construye y ejecuta el JavaScript necesario para transmitir estos datos a la plataforma Allani.
  - `allanitracking/views/templates/hook/header.tpl`
    - **Hook**: `displayHeader` (o `header` en versiones anteriores)
    - **Propósito**: Esta plantilla se usa típicamente para incluir JavaScript o CSS global en la sección `<head>` de la página. En el contexto de este módulo, podría usarse para incluir cualquier script global o metaetiquetas necesarias de Allani, aunque la transmisión principal de datos se maneja mediante `displayOrderConfirmation.tpl`. Dada la descripción del módulo, es probable que incluya una configuración mínima o un marcador de posición.
- **Plantillas de Administración (`views/templates/admin/`)**: Ninguna.
- **Plantillas de Front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - Almacena su configuración en la tabla `ps_configuration`, específicamente la clave `ALLANI_ORDER_TRACK`.
  - También utiliza claves de configuración estándar de PrestaShop para las comprobaciones de actualización (`mypresta_updates`, `update_`, `updatev_`).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` / `header` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para la inicialización global del script de Allani o metaetiquetas. |
| `displayOrderConfirmation` | En la página de confirmación del pedido, después de una compra exitosa. | **Hook principal para este módulo.** Inyecta el código JavaScript para enviar los detalles del pedido (ID de producto, valor del pedido, ID del pedido) a la plataforma Allani. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Seguimiento de Allani", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad del módulo.
