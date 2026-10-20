---
title: "Píxel de Commerce Connector - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Píxel de Commerce Connector de MyPresta.eu."
sidebar:
  label: "Píxel de Commerce Connector - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Commerce Connector pixel en MyPresta.eu](https://mypresta.eu/modules/ordering-process/commerce-connector-pixel.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/commerce-connector-pixel/)
>
> ---


# Píxel de Commerce Connector

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes para los módulos de PrestaShop. Normalmente no se necesitan configuraciones especiales del servidor para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Píxel de Commerce Connector" para acceder a sus ajustes.

#### **Identificador de tienda**

- **Qué hace este ajuste:** Este es el identificador único que le proporciona Commerce Connector para su tienda o cuenta de comerciante específica. Es crucial para que Commerce Connector atribuya correctamente los datos de ventas a su cuenta.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece con su ID de tienda correcto:* El píxel se activará con su identificador único, lo que permitirá a Commerce Connector rastrear con precisión las ventas de su tienda.
  - *Cuando es incorrecto o está vacío:* Es posible que el píxel no se active correctamente, o que los datos de ventas se atribuyan a la cuenta incorrecta, lo que lleva a un seguimiento inexacto y a una posible pérdida de información de marketing.
- **Valor recomendado:** Introduzca la cadena exacta de "Identificador de tienda" proporcionada por Commerce Connector. Suele ser una combinación de letras y números.
- **Escenario / ejemplo de comerciante:** Commerce Connector le dice que su ID de tienda es "MYSTORE12345". Usted introduciría "MYSTORE12345" en este campo. Sin él, Commerce Connector no sabrá de qué tienda proviene la venta.

#### **Registrar lanzamientos de píxeles**

- **Qué hace este ajuste:** Este ajuste controla si el módulo registra un log cada vez que se lanza el píxel de Commerce Connector (es decir, cada vez que un cliente llega a la página de confirmación del pedido y el píxel intenta activarse). Este log puede ser útil para la resolución de problemas.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado ("Sí"):* El módulo creará un archivo de log (normalmente en el directorio del módulo) que detalla cada lanzamiento del píxel, incluyendo los detalles del pedido. Esto puede ayudarle a verificar si el píxel se está activando como se espera.
  - *Cuando está deshabilitado ("No"):* No se generará ningún archivo de log, que es la configuración estándar para una tienda en producción para ahorrar espacio en disco y procesamiento.
- **Valor recomendado:** "No" para una tienda en producción. Solo habilite "Sí" temporalmente si está solucionando problemas y necesita verificar la actividad del píxel.
- **Escenario / ejemplo de comerciante:** Sospecha que el píxel no está rastreando todas las ventas. Habilita "Registrar lanzamientos de píxeles" a "Sí", realiza un pedido de prueba y luego verifica el archivo de log para ver si su pedido de prueba fue registrado, confirmando que el píxel se activó. Una vez confirmado, lo vuelve a cambiar a "No".

#### **Habilitar / Deshabilitar Módulo**

- **Qué hace este ajuste:** Este es un interruptor estándar del módulo de PrestaShop que le permite habilitar o deshabilitar globalmente todo el módulo de píxeles de Commerce Connector.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo estará activo y el píxel de Commerce Connector se inyectará en su página de confirmación de pedido, rastreando las ventas.
  - *Cuando está deshabilitado:* El módulo estará inactivo y el píxel de Commerce Connector NO estará presente en su página de confirmación de pedido, lo que significa que no se rastrearán ventas a través de este módulo.
- **Valor recomendado:** "Sí" si está utilizando activamente Commerce Connector para el seguimiento de ventas.
- **Escenario / ejemplo de comerciante:** Ha completado su integración con Commerce Connector y desea comenzar a rastrear las ventas. Se asegura de que esta configuración esté en "Sí". Si pausa temporalmente sus campañas de Commerce Connector, podría cambiarla a "No" para evitar la activación innecesaria del píxel.

#### Otras claves de configuración (Internas)

El módulo también utiliza claves de configuración internas como `mypresta_updates`, `update_`, `updatev_`, `COMCONN_SIDENT_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Estas son típicamente para la gestión interna del módulo, comprobaciones de actualización y manejo de idiomas dentro del back office de PrestaShop. Los comerciantes generalmente no necesitan interactuar con estas directamente.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Identificador de tienda | Su ID único de Commerce Connector | Crucial para atribuir datos de ventas a su cuenta específica de Commerce Connector. |
| Configuración del módulo | Registrar lanzamientos de píxeles | No | Controla si el módulo crea un archivo de registro de las activaciones del píxel. Habilitar para solucionar problemas, deshabilitar para producción. |
| Configuración del módulo | Habilitar / Deshabilitar Módulo | Sí | Activa o desactiva globalmente todo el módulo y su seguimiento de píxeles. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero Commerce Connector no muestra ninguna venta. ¿Qué debo hacer?**
R:

1. **Verifique el "Identificador de tienda":** Vaya a la configuración del módulo y asegúrese de que su "Identificador de tienda" esté introducido correctamente y coincida exactamente con lo que le proporcionó Commerce Connector.
2. **Módulo habilitado:** Asegúrese de que el módulo esté habilitado en la página de configuración.
3. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su back office de PrestaShop y borre la caché de Smarty y todas las cachés.
4. **Compra de prueba:** Realice una compra de prueba completa en su tienda, llegando hasta la página de confirmación del pedido.
5. **Habilitar registro:** Habilite temporalmente "Registrar lanzamientos de píxeles" en la configuración del módulo, realice otra compra de prueba y luego verifique el archivo `logFile.tpl` (o un archivo de registro similar) dentro del directorio del módulo a través de FTP para ver si se registró el lanzamiento del píxel.
6. **Contactar con soporte:** Si los problemas persisten, póngase en contacto con el soporte de MyPresta.eu con los detalles de su configuración y cualquier entrada de registro.

**P: ¿Este módulo ralentizará mi sitio web?**
R: No. El píxel de Commerce Connector es un script muy ligero que solo se carga en la página de confirmación del pedido. Esta página se suele alcanzar después de la experiencia de compra principal, y la ejecución del píxel es mínima, por lo que no afectará notablemente el rendimiento ni la velocidad de carga de su tienda para los clientes.

**P: ¿Puedo usar este módulo con otros píxeles de seguimiento (por ejemplo, Google Analytics, Píxel de Facebook)?**
R: Sí, absolutamente. Este módulo está diseñado para integrarse específicamente con Commerce Connector. Opera de forma independiente y no entrará en conflicto con otros píxeles de seguimiento o scripts de análisis que tenga instalados en su tienda PrestaShop.

**P: ¿Dónde puedo encontrar el archivo de registro si habilito "Registrar lanzamientos de píxeles"?**
R: Si está habilitado, el archivo de registro se genera típicamente dentro del directorio del módulo. Necesitará acceso FTP a su servidor para navegar a `su_raiz_prestashop/modules/comconn/views/templates/hook/logFile.tpl` (o una ruta similar) para ver su contenido. Recuerde deshabilitar el registro una vez que la solución de problemas esté completa.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo de píxeles de Commerce Connector (`comconn`) es un módulo de PrestaShop sencillo diseñado para inyectar un píxel JavaScript específico en la página de confirmación del pedido. Se adhiere a la arquitectura del módulo de PrestaShop, aprovechando principalmente el hook `displayOrderConfirmation` para renderizar su script de seguimiento. La lógica del módulo está contenida en su archivo PHP principal, con la configuración gestionada a través de `getContent()` y plantillas para renderizar el píxel y un log opcional.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. El módulo se engancha directamente a `displayOrderConfirmation` y renderiza su contenido a través de una plantilla.
- **Controladores de Back-Office Admin**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo no define ninguna clase personalizada ni instancias de `ObjectModel`. Toda la lógica está autocontenida dentro de `comconn.php`.

### 4.4 Activos JavaScript (`views/js/`)

- Ninguno. El módulo incrusta directamente el script del píxel de Commerce Connector dentro de su plantilla Smarty, en lugar de enlazar a archivos `.js` externos.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no añade ningún estilo personalizado al front o back office.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su salida.

- **Plantillas de hook (`views/templates/hook/`)**:

  - `comconn/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Propósito**: Esta es la plantilla principal responsable de renderizar el script del píxel de Commerce Connector. Inserta dinámicamente el `Shop ident` (de la configuración `COMCONN_SIDENT`) y los detalles del pedido (ID del pedido, total, moneda, productos) en el código JavaScript que activa el píxel. Esta plantilla es crucial para la funcionalidad principal del módulo.
  - `comconn/views/templates/hook/logFile.tpl`
    - **Hook**: No enganchado directamente, pero utilizado por el mecanismo de registro interno del módulo.
    - **Propósito**: Esta plantilla se utiliza para formatear y almacenar entradas de registro cuando la opción "Registrar lanzamientos de píxeles" está habilitada. Registra los detalles de cada lanzamiento del píxel, incluyendo la marca de tiempo, el ID del pedido y los datos enviados a Commerce Connector. Los desarrolladores pueden inspeccionar este archivo a través de FTP para solucionar problemas.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración en la tabla estándar `ps_configuration`.

  - Entradas de `PS_CONFIGURATION`:
    - `COMCONN_SIDENT`: Almacena el ID de tienda de Commerce Connector del comerciante.
    - `COMCONN_LOG`: Almacena el valor booleano (0 o 1) para habilitar/deshabilitar el registro de lanzamiento de píxeles.
    - `mypresta_updates`, `update_`, `updatev_`: Claves internas para actualizaciones y versiones del módulo.
- **Tabla de Hooks Registrados**:

  | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
  | --- | --- | --- |
  | `displayOrderConfirmation` | Después de que un cliente completa un pedido con éxito y llega a la página de confirmación. | Inyecta el script del píxel de Commerce Connector en la página para rastrear la compra completada. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Píxel de Commerce Connector", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.
