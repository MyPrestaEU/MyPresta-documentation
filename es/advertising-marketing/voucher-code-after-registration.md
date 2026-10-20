---
title: "Código de cupón después del registro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Código de cupón después del registro' de MyPresta.eu."
sidebar:
  label: "Código de cupón después del registro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Voucher code after registration en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-code-after-registration.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/voucher-code-after-registration/)
>
> ---


# Código de cupón después del registro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente vienen preinstaladas en la mayoría de los entornos de alojamiento web.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en el botón "Configurar" junto al módulo "Código de cupón después del registro". Esto le llevará a la pantalla de configuración principal donde podrá definir cómo funcionarán sus nuevos cupones de cliente.

La página de configuración le presentará opciones para definir las características del cupón que recibirán los nuevos clientes. Estos ajustes corresponden directamente a las características estándar de la "Regla de carrito" (cupón) de PrestaShop.

Aquí están los ajustes típicos que encontrará:

- **Descripción:**

  - **Qué hace este ajuste:** Este es el nombre interno de la regla de carrito (cupón) que se creará. Le ayuda a identificar el cupón en su Back Office.
  - **Efecto de cambiar este ajuste:** Este nombre es solo para su referencia y no es visible para los clientes.
  - **Valor recomendado:** Algo descriptivo como "Cupón de registro de nuevo cliente" o "Descuento de bienvenida".
  - **Escenario / ejemplo del comerciante:** Si realiza varias promociones, una descripción clara como "Cupón de bienvenida - 10% de descuento" le ayuda a rastrear su rendimiento.
- **Código:**

  - **Qué hace este ajuste:** Define el prefijo para los códigos de cupón únicos generados. El módulo añadirá una cadena única a este prefijo para cada nuevo cliente.
  - **Efecto de cambiar este ajuste:** Si lo establece en "BIENVENIDO", los clientes podrían recibir códigos como "BIENVENIDO12345" o "BIENVENIDOABCDE". Esto hace que los códigos sean fácilmente identificables.
  - **Valor recomendado:** Un prefijo corto y memorable como "BIENVENIDO", "NUEVOCLIENTE" o "MITIENDA". Déjelo vacío para un código totalmente aleatorio.
  - **Escenario / ejemplo del comerciante:** Usar "BIENVENIDO" deja claro al cliente que se trata de una oferta de bienvenida.
- **Resaltar:**

  - **Qué hace este ajuste:** Si está habilitado, este cupón se mostrará en el resumen del carrito (si corresponde) y en la página del producto (si está configurado para hacerlo por los ajustes principales de PrestaShop).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* La existencia del cupón podría insinuarse sutilmente en lugares donde las reglas de carrito suelen promocionarse.
    - *Cuando está deshabilitado:* El cupón solo es conocido por el cliente a través del correo electrónico y su cuenta.
  - **Valor recomendado:** SÍ (Habilitado), ya que puede recordar sutilmente a los clientes los descuentos disponibles.
  - **Escenario / ejemplo del comerciante:** Habilitar esto puede animar a los clientes a usar el cupón que recibieron, incluso si lo olvidaron.
- **Uso parcial:**

  - **Qué hace este ajuste:** Determina si el cupón se puede usar varias veces si su valor es mayor que el total del pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Si un cliente tiene un cupón de 50€ y compra un artículo de 30€, le quedará un saldo de 20€ en el cupón para una futura compra.
    - *Cuando está deshabilitado:* El valor total del cupón debe usarse en una sola transacción, o el saldo restante se pierde.
  - **Valor recomendado:** NO (Deshabilitado) para la mayoría de los cupones de bienvenida, para fomentar una compra completa.
  - **Escenario / ejemplo del comerciante:** Para un cupón de "10% de descuento", este ajuste es menos relevante, pero para un cupón de "cantidad fija" (por ejemplo, "10€ de descuento"), deshabilitar el uso parcial fomenta un pedido inicial más grande.
- **Prioridad:**

  - **Qué hace este ajuste:** Si un cliente tiene varios cupones, este número determina el orden en que se aplican. Los números más bajos significan mayor prioridad.
  - **Efecto de cambiar este ajuste:** Un cupón con prioridad 1 se aplicará antes que un cupón con prioridad 2. Esto es importante si los cupones no se pueden combinar.
  - **Valor recomendado:** 1 (Máxima prioridad) para los cupones de bienvenida, asegurando que se apliquen primero.
  - **Escenario / ejemplo del comerciante:** Si tiene un cupón general de "envío gratuito" (prioridad 5) y un cupón de "descuento de bienvenida" (prioridad 1), el descuento de bienvenida se calculará primero.
- **Estado:**

  - **Qué hace este ajuste:** Controla si el módulo está activo y generando cupones.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los nuevos clientes recibirán cupones al registrarse.
    - *Cuando está deshabilitado:* El módulo dejará de generar y enviar cupones.
  - **Valor recomendado:** SÍ (Habilitado) para activar la funcionalidad principal del módulo.
  - **Escenario / ejemplo del comerciante:** Podría deshabilitarlo temporalmente durante un evento de ventas específico en el que no desee ofrecer descuentos de registro adicionales.
- **Tipo de descuento:**

  - **Qué hace este ajuste:** Define si el descuento es un porcentaje, una cantidad fija o envío gratuito.
  - **Efecto de cambiar este ajuste:**
    - *Porcentaje:* por ejemplo, "10%" de descuento en el pedido.
    - *Cantidad:* por ejemplo, "10€" de descuento en el pedido.
    - *Envío gratuito:* Exime de los gastos de envío.
  - **Valor recomendado:** Porcentaje o Cantidad, según su estrategia de marketing.
  - **Escenario / ejemplo del comerciante:** Ofrecer "10% de descuento" es común para los descuentos de bienvenida. "5€ de descuento" podría ser mejor para artículos de menor precio.
- **Valor:**

  - **Qué hace este ajuste:** El valor real del descuento, correspondiente al "Tipo de descuento" seleccionado.
  - **Efecto de cambiar este ajuste:** Si el "Tipo de descuento" es Porcentaje y el "Valor" es 10, los clientes obtienen un 10% de descuento. Si el "Tipo de descuento" es Cantidad y el "Valor" es 10, obtienen 10€ de descuento.
  - **Valor recomendado:** Un valor que sea atractivo pero también rentable, por ejemplo, "10" para el 10% o "5€".
  - **Escenario / ejemplo del comerciante:** Un descuento del 10% es un buen punto de partida para atraer a nuevos clientes.
- **Cantidad mínima:**

  - **Qué hace este ajuste:** El total mínimo del pedido (antes del envío) requerido para que el cupón sea válido.
  - **Efecto de cambiar este ajuste:** Si se establece en 50€, el cliente debe realizar un pedido de 50€ o más para usar el cupón.
  - **Valor recomendado:** Establezca un mínimo razonable para fomentar pedidos iniciales más grandes, o 0 si no se requiere un mínimo.
  - **Escenario / ejemplo del comerciante:** Establecer un mínimo de 50€ para un cupón del 10% de descuento asegura que aún obtenga una buena ganancia en el primer pedido.
- **Acumulativo:**

  - **Qué hace este ajuste:** Determina si este cupón se puede combinar con otros cupones.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden usar este cupón de bienvenida junto con otros cupones activos (por ejemplo, un cupón de envío gratuito).
    - *Cuando está deshabilitado:* Este cupón no se puede usar si ya se ha aplicado otro cupón al carrito.
  - **Valor recomendado:** NO (Deshabilitado) para la mayoría de los cupones de bienvenida para evitar descuentos excesivos.
  - **Escenario / ejemplo del comerciante:** Normalmente, querrá limitar la acumulación de descuentos para proteger sus márgenes, por lo que deshabilitar el uso acumulativo suele ser preferible.
- **Válido desde / Válido hasta:**

  - **Qué hace este ajuste:** Define el rango de fechas durante el cual el cupón está activo.
  - **Efecto de cambiar este ajuste:** El cupón solo será válido entre estas fechas.
  - **Valor recomendado:** Deje "Válido desde" como la fecha actual. Para "Válido hasta", considere establecer una fecha de vencimiento (por ejemplo, 30 días desde el registro) para crear urgencia, o déjelo muy en el futuro si desea que sea perenne.
  - **Escenario / ejemplo del comerciante:** Establecer "Válido hasta" 30 días en el futuro anima a los clientes a usar el cupón rápidamente.
- **Cantidad:**

  - **Qué hace este ajuste:** Se refiere al número total de cupones *únicos* que puede generar el módulo.
  - **Efecto de cambiar este ajuste:** Si se establece en 100, solo los primeros 100 nuevos registrados recibirán un cupón.
  - **Valor recomendado:** Un número muy alto (por ejemplo, 999999) o déjelo vacío si desea que se genere un número ilimitado de cupones para nuevos registrados.
  - **Escenario / ejemplo del comerciante:** Para una oferta de bienvenida continua, normalmente querrá una cantidad ilimitada. Si está ejecutando una campaña por tiempo limitado para los primeros X registrados, establecería un número específico.
- **Cantidad por cliente:**

  - **Qué hace este ajuste:** Define cuántas veces un *solo cliente* puede recibir este cupón específico.
  - **Efecto de cambiar este ajuste:** Establezca en 1 para asegurar que cada cliente solo reciba un cupón de bienvenida al registrarse inicialmente.
  - **Valor recomendado:** 1.
  - **Escenario / ejemplo del comerciante:** Desea que cada nuevo cliente obtenga un descuento de bienvenida, no varios si se registran de nuevo con un correo electrónico diferente (aunque el núcleo de PrestaShop suele evitar esto).

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Descripción** | "Cupón de Nuevo Cliente" | Nombre interno del cupón en el BO. |
| Configuración del módulo | **Código** | Vacío (aleatorio) / "BIENVENIDO" | Prefijo para los códigos de cupón generados. |
| Configuración del módulo | **Resaltar** | SÍ | Mostrar cupón en el resumen del carrito/página del producto. |
| Configuración del módulo | **Uso parcial** | NO | Permitir múltiples usos si el valor > total del pedido. |
| Configuración del módulo | **Prioridad** | 1 | Orden de aplicación si hay varios cupones. |
| Configuración del módulo | **Estado** | SÍ | Activar/desactivar la generación de cupones del módulo. |
| Configuración del módulo | **Tipo de descuento** | Porcentaje | Tipo de descuento (%, cantidad, envío gratuito). |
| Configuración del módulo | **Valor** | 10 | El valor real del descuento (por ejemplo, 10 para 10%). |
| Configuración del módulo | **Cantidad mínima** | 0 | Total mínimo del pedido para la validez del cupón. |
| Configuración del módulo | **Acumulativo** | NO | Permitir combinar con otros cupones. |
| Configuración del módulo | **Válido desde** | Fecha actual | Fecha de inicio de la validez del cupón. |
| Configuración del módulo | **Válido hasta** | Futuro lejano / 30 días | Fecha de finalización de la validez del cupón. |
| Configuración del módulo | **Cantidad** | 999999 | Número total de cupones únicos a generar. |
| Configuración del módulo | **Cantidad por cliente** | 1 | Cuántas veces un solo cliente puede obtenerlo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben el correo electrónico del cupón. ¿Qué debo verificar?**
R:

1.  **Estado del módulo:** Asegúrese de que la configuración "Estado" en la configuración del módulo esté establecida en SÍ (Habilitado).
2.  **Configuración de correo electrónico:** Verifique la configuración de correo electrónico de su PrestaShop en **Parámetros avanzados > E-mail**. Envíe un correo electrónico de prueba para asegurarse de que el sistema de correo electrónico de su tienda funciona correctamente.
3.  **Carpetas de spam:** Aconseje a los clientes que revisen sus carpetas de spam o correo no deseado.
4.  **Registros del módulo:** Si están disponibles, busque cualquier registro de errores relacionado con el módulo o el envío de correo electrónico.
5.  **Caché de Smarty:** A veces, borrar la caché de Smarty en **Parámetros avanzados > Rendimiento** puede resolver problemas de visualización o funcionalidad.

**P: El código de cupón se genera, pero no se aplica correctamente al finalizar la compra.**
R:

1.  **Configuración del cupón:** Vuelva a verificar todas las configuraciones del cupón en la configuración del módulo (por ejemplo, "Cantidad mínima", "Válido desde/hasta", "Acumulativo"). Asegúrese de que el carrito del cliente cumpla todas las condiciones.
2.  **Entrada del código:** Confirme que el cliente está introduciendo el código correctamente en el carrito/finalización de la compra.
3.  **Restricciones de producto:** Asegúrese de que no haya restricciones ocultas de producto o categoría aplicadas a la regla de carrito generada (aunque este módulo suele crear reglas simples y amplias).

**P: ¿Puedo personalizar la plantilla de correo electrónico que envía el cupón?**
R: Sí, el módulo utiliza el sistema de plantillas de correo electrónico estándar de PrestaShop. Puede encontrar y personalizar los archivos de plantilla de correo electrónico relevantes (normalmente en `themes/su_tema/mail/es/` o `mails/es/` para versiones anteriores) que se activan cuando se crea y envía una nueva regla de carrito. Busque plantillas relacionadas con `voucher` o `cart_rule`.

**P: ¿Qué sucede si un cliente se registra varias veces con diferentes direcciones de correo electrónico?**
R: El módulo generará un nuevo cupón único para cada nuevo registro. La funcionalidad principal de PrestaShop suele evitar registros de correo electrónico duplicados, pero si un cliente utiliza diferentes correos electrónicos, recibiría un nuevo cupón cada vez. La configuración "Cantidad por cliente" se aplica a un solo ID de cliente, no necesariamente a direcciones de correo electrónico únicas si omiten las comprobaciones principales.

**P: El módulo está instalado, pero no veo ningún elemento nuevo en el menú del Back Office.**
R: Este módulo se integra directamente en la sección existente "Módulos > Gestor de módulos" y no añade nuevos elementos de menú de nivel superior. Su configuración es accesible haciendo clic en "Configurar" junto a su nombre en la lista de módulos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Código de cupón después del registro" (`registervoucher`) es un módulo estándar de PrestaShop diseñado principalmente para extender el hook `actionCustomerAccountAdd`. Aprovecha la funcionalidad principal de `CartRule` (cupón) de PrestaShop para crear y asignar automáticamente un código de descuento único a las nuevas cuentas de cliente. La configuración del módulo se gestiona a través del método `getContent()` en el archivo principal del módulo, almacenando la configuración en `ps_configuration`. Incluye una interacción mínima con el front-office, basándose principalmente en el sistema de correo electrónico nativo de PrestaShop y la visualización de la cuenta del cliente para la entrega del cupón.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la lógica está encapsulada dentro del archivo principal del módulo y sus hooks registrados.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Interactúa directamente con la clase principal `CartRule` de PrestaShop para crear y gestionar cupones.

### 4.4 Activos JavaScript (`views/js/`)

- `registervoucher/lib/voucherengine/script.js`
  - **Alcance:** Potencialmente Back-office, o un script genérico incluido para compatibilidad.
  - **Descripción:** Dada la función principal del módulo (generación de cupones en el backend), este script es probablemente una utilidad o un script de compatibilidad. Podría manejar mejoras de la interfaz de usuario en la página de configuración, validación de formularios o proporcionar correcciones de compatibilidad para versiones anteriores de PrestaShop, especialmente en lo que respecta a elementos de formulario dinámicos o interacciones AJAX dentro del método `getContent()`. Sin una inspección adicional, su propósito exacto es especulativo, pero generalmente está relacionado con la mejora de la interfaz de configuración del módulo o la garantía de la compatibilidad entre versiones para el panel de administración.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `registervoucher/css.css`

  - **Alcance:** Probablemente estilo del formulario de administración del Back-office.
  - **Descripción:** Esta hoja de estilo probablemente contiene estilos personalizados para la página de configuración del módulo dentro del Back Office de PrestaShop. Podría ajustar el diseño, el espaciado, los colores o las apariencias de elementos específicos para garantizar que el formulario de configuración sea visualmente coherente o para aplicar una marca personalizada.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** `.registervoucher-config`, `.form-group`, `.control-label`, `.help-block` (específicos del HTML generado por el módulo).
- `registervoucher/lib/voucherengine/ps16.css`

  - **Alcance:** Estilo del formulario de administración del Back-office, específicamente para la compatibilidad con PrestaShop 1.6.
  - **Descripción:** Esta hoja de estilo casi con certeza se incluye para garantizar que la página de configuración del módulo se renderice correctamente y de manera consistente con el tema del Back Office de PrestaShop 1.6. Aborda las diferencias de estilo entre PS 1.6 y las versiones más nuevas, proporcionando las anulaciones necesarias o estilos específicos para elementos como botones, campos de formulario y contenedores de diseño para mantener una apariencia adecuada.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Específicos del tema de administración de PS 1.6, por ejemplo, `.panel`, `.form-horizontal`, `.btn`.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El dossier del módulo no indica archivos `.tpl` personalizados. Esto sugiere que el formulario de configuración del módulo se renderiza directamente dentro del método `getContent()` utilizando las clases de ayuda de PrestaShop (por ejemplo, `HelperForm`), y cualquier visualización en el front-office (como el cupón en la cuenta del cliente) se maneja anulando las plantillas principales de PrestaShop o inyectando contenido directamente a través de hooks sin plantillas de módulo dedicadas. El contenido del correo electrónico se gestiona a través de las plantillas de correo nativas de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - La configuración se almacena en la tabla `ps_configuration` (por ejemplo, `PS_REGISTERVOUCHER_DESCRIPTION`, `PS_REGISTERVOUCHER_CODE`, etc.).
  - Los cupones generados se almacenan en las tablas principales de PrestaShop `ps_cart_rule` y `ps_cart_rule_lang`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Se ejecuta inmediatamente después de que se crea una nueva cuenta de cliente con éxito. | Este es el hook principal. El módulo escucha este evento para activar el proceso de generación y asignación de cupones para el cliente recién registrado. |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | A menudo se usa para agregar CSS/JS, pero en este módulo, no se usa explícitamente para la visualización del front-office. Podría ser para la configuración interna del módulo o la compatibilidad. |
| `displayRightColumn` | Se ejecuta en la columna derecha del front-office. | No se usa directamente para la funcionalidad principal del módulo de visualización de cupones. |
| `displayLeftColumn` | Se ejecuta en la columna izquierda del front-office. | No se usa directamente para la funcionalidad principal del módulo de visualización de cupones. |
| `displayFooter` | Se ejecuta en la sección del pie de página de cada página del front-office. | No se usa directamente para la funcionalidad principal del módulo de visualización de cupones. |
| `displayProductButtons` | Se ejecuta en la página del producto, cerca del botón de añadir al carrito. | No se usa directamente para la funcionalidad principal del módulo de visualización de cupones. |
| `displayCustomerAccount` | Se ejecuta en la página "Mi cuenta" del cliente. | Este hook es crucial para mostrar el código de cupón generado directamente dentro del área de la cuenta del cliente, haciéndolo fácilmente accesible. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Código de cupón después del registro", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
