---
title: "Integración de seguimiento de ventas de Kelkoo - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop de integración de seguimiento de ventas de Kelkoo de MyPresta.eu."
sidebar:
  label: "Integración de seguimiento de ventas de Kelkoo"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Kelkoo sales tracking integration en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/kelkoo-sales-tracking-integration.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/kelkoo-sales-tracking-integration/)
>
> ---


# Integración de seguimiento de ventas de Kelkoo

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la mayoría de los módulos de PrestaShop y suelen estar disponibles en cualquier entorno de alojamiento moderno. No hay requisitos especiales o inusuales para este módulo.

## 2. Recorrido completo de la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, haga clic en "Configurar" junto al módulo "Integración de seguimiento de ventas de Kelkoo". Se le presentará una sencilla pantalla de configuración.

#### ID de seguimiento de Kelkoo
-   **Qué hace este ajuste:** Este es el ajuste más crucial. Aquí es donde introduce su ID de seguimiento único proporcionado por Kelkoo. Este ID le indica a Kelkoo a qué comerciante (su tienda) pertenecen los datos de ventas.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se introduce correctamente:* El módulo utilizará este ID para enviar datos de ventas a su cuenta específica de Kelkoo, lo que permitirá a Kelkoo atribuir las ventas a sus campañas.
    -   *Cuando se deja vacío o es incorrecto:* El seguimiento de ventas no funcionará correctamente y Kelkoo no recibirá datos sobre las compras realizadas a través de su plataforma, lo que imposibilitará la medición del rendimiento de su campaña.
-   **Valor recomendado:** Introduzca el ID de seguimiento exacto que le proporcionó Kelkoo. Suele ser una cadena numérica o alfanumérica.
-   **Escenario / ejemplo de comerciante:** Ha configurado una cuenta de comerciante con Kelkoo. Ellos le proporcionarán un "ID de seguimiento de Kelkoo" o "ID de comerciante" único. Debe copiar y pegar este ID con precisión en este campo. Sin él, la integración está incompleta.

#### Habilitar seguimiento
-   **Qué hace este ajuste:** Este es un simple interruptor de ENCENDIDO/APAGADO para activar o desactivar la funcionalidad de seguimiento de ventas de Kelkoo en toda su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El módulo inyectará activamente los scripts de seguimiento necesarios y enviará datos de ventas a Kelkoo en la página de confirmación del pedido.
    -   *Cuando está deshabilitado (NO):* El módulo detendrá todas las actividades de seguimiento. No se inyectarán scripts y no se enviarán datos de ventas a Kelkoo.
-   **Valor recomendado:** SÍ. Solo debe deshabilitarlo si desea detener temporalmente el seguimiento de ventas a través de Kelkoo o si está solucionando problemas.
-   **Escenario / ejemplo de comerciante:** Ha completado su configuración de Kelkoo y desea comenzar a rastrear las ventas de inmediato. Establezca esto en SÍ. Si decide pausar sus campañas de Kelkoo o necesita realizar un mantenimiento, podría establecerlo temporalmente en NO.

### 2.2 Tabla de referencia rápida de configuración
| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| Configuración del módulo | ID de seguimiento de Kelkoo | Su ID de Kelkoo | Identificador único para su cuenta de comerciante de Kelkoo. Esencial para la atribución de ventas. |
| Configuración del módulo | Habilitar seguimiento | SÍ | Activa/desactiva la funcionalidad de seguimiento de ventas de Kelkoo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero Kelkoo no muestra ninguna venta. ¿Qué debo hacer?**
R:
1.  **Vuelva a verificar su ID de seguimiento de Kelkoo:** Asegúrese de que esté ingresado exactamente como lo proporcionó Kelkoo, sin espacios ni caracteres adicionales.
2.  **Asegúrese de que "Habilitar seguimiento" esté en SÍ:** Este interruptor debe estar activo para que el módulo funcione.
3.  **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, el contenido en caché puede impedir que las nuevas configuraciones del módulo surtan efecto.
4.  **Realice una compra de prueba:** Complete un pedido completo en su tienda para activar el seguimiento.
5.  **Póngase en contacto con el soporte de Kelkoo:** Si todas las configuraciones son correctas y ha borrado la caché, comuníquese con el equipo de soporte de Kelkoo. A menudo pueden verificar su parte para ver si se están recibiendo datos o si hay un problema con la configuración de su cuenta en su plataforma.

**P: ¿Este módulo ralentizará mi sitio web?**
R: No, el módulo es muy ligero. Solo inyecta un pequeño fragmento de JavaScript no bloqueante en la cabecera y envía datos en la página de confirmación del pedido. Este proceso está optimizado para no afectar la velocidad de carga de su tienda ni la experiencia del cliente.

**P: ¿Este módulo funciona con configuraciones de varias tiendas?**
R: Sí, el módulo debería funcionar correctamente en un entorno de varias tiendas. Configurará el ID de seguimiento de Kelkoo para cada tienda individualmente si tienen cuentas de Kelkoo separadas, o usará el mismo ID si está rastreando todas las tiendas bajo una sola cuenta de Kelkoo.

**P: Estoy usando un tema personalizado. ¿Seguirá funcionando este módulo?**
R: Sí, el módulo utiliza ganchos estándar de PrestaShop (`displayHeader`, `displayOrderConfirmation`) que están casi universalmente presentes en todos los temas bien codificados. No depende de elementos específicos del tema, por lo que debería ser compatible con temas personalizados. Si encuentra problemas, asegúrese de que su tema personalizado implemente correctamente estos ganchos principales de PrestaShop.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura
El módulo "Integración de seguimiento de ventas de Kelkoo" es un módulo de PrestaShop sencillo diseñado para integrar el píxel de seguimiento de ventas de Kelkoo. Principalmente aprovecha el sistema de ganchos de PrestaShop para inyectar un script de seguimiento global en la cabecera y un script de seguimiento de conversiones en la página de confirmación del pedido. Sigue una estructura básica de módulo de PrestaShop, con su lógica central contenida dentro del archivo principal del módulo y archivos de plantilla para la representación de ganchos. No hay controladores, modelos o activos complejos de JavaScript/CSS personalizados más allá de lo necesario para el píxel de seguimiento.

### 4.2 Controladores (`controllers/`)
- **Controladores de Front-Office**: Ninguno. Toda la funcionalidad de front-office se maneja a través de ganchos dentro del archivo principal del módulo.
- **Controladores de administración de Back-Office**: Ninguno. La configuración se maneja directamente mediante el método `getContent()` en el archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)
- No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Toda la lógica reside dentro del archivo principal del módulo `Kelkoo.php` (o `index.php` en estructuras más antiguas).

### 4.4 Activos de JavaScript (`views/js/`)
- No se incluyen archivos JavaScript dedicados en el módulo. El script de seguimiento de Kelkoo necesario se genera dinámicamente y se inyecta directamente en el HTML a través de plantillas Smarty o el gancho `displayHeader`.

### 4.5 Hojas de estilo CSS (`views/css/`)
- No se incluyen archivos CSS dedicados en el módulo. El módulo no tiene componentes visuales de front-office y su configuración de back-office utiliza el estilo de formulario estándar de PrestaShop.

### 4.6 Estructura de plantilla Smarty (`views/templates/`)
- **Plantillas de gancho (`views/templates/hook/`)**:
    *   `kelkoo/views/templates/hook/displayOrderConfirmation.tpl`:
        *   **Gancho**: `displayOrderConfirmation`
        *   **Propósito**: Esta plantilla se renderiza en la página de confirmación del pedido después de una compra exitosa. Es responsable de generar el píxel de seguimiento de ventas de Kelkoo (KST) con detalles dinámicos del pedido (ID del pedido, total, detalles del producto). Recupera la información del pedido pasada al gancho y la formatea según las especificaciones de Kelkoo.
    *   `kelkoo/views/templates/hook/header.tpl`:
        *   **Gancho**: `displayHeader`
        *   **Propósito**: Esta plantilla se renderiza dentro de la sección `<head>` de cada página. Está destinada a incluir cualquier script de seguimiento global de Kelkoo o inicializadores que deban estar presentes en todo el sitio, aunque para un seguimiento de ventas simple, la lógica principal a menudo se encuentra en `displayOrderConfirmation`. Podría contener un píxel base de Kelkoo básico o un marcador de posición para futuras funciones de Kelkoo.

- **Plantillas de administración (`views/templates/admin/`)**: Ninguna. El formulario de configuración se construye directamente dentro de `getContent()` utilizando las clases de formulario de ayuda de PrestaShop.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de ganchos
- **Tablas de la base de datos**:
    *   El módulo no crea ninguna tabla SQL personalizada.
    *   Los ajustes de configuración (`Kelkoo Tracking ID`, `Enable Tracking`) se almacenan en la tabla `ps_configuration` (o prefijo `_configuration`) utilizando claves como `KELKOO_TRACKING_ID` y `KELKOO_ENABLED`.

- **Tabla de ganchos registrados**:
  | Nombre del gancho | Momento de ejecución | Propósito técnico |
  |---|---|---|
  | `displayHeader` | Se renderiza en la sección `<head>` de cada página. | Inyecta scripts de seguimiento global de Kelkoo o píxel base. |
  | `displayOrderConfirmation` | Se renderiza en la página de confirmación del pedido después de una compra exitosa. | Envía datos detallados de ventas (ID del pedido, importe, productos) a Kelkoo para el seguimiento de conversiones. |

## 5. Soporte oficial y actualizaciones
Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo "Integración de seguimiento de ventas de Kelkoo", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.
