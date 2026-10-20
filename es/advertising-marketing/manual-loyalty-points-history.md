---
title: "Manual Puntos de Fidelidad e Historial - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Manual Loyalty Points & History' de MyPresta.eu."
sidebar:
  label: "Manual Puntos de Fidelidad e Historial - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Manual Loyalty Points & History en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/manual-loyalty-points-history.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/manual-loyalty-points-history/)
>
> ---


# Manual Puntos de Fidelidad e Historial

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Este módulo también requiere que el sistema principal de fidelidad de PrestaShop (por ejemplo, `myprestaloyalty` o el módulo de fidelidad predeterminado de PrestaShop) esté instalado y activo, ya que extiende su funcionalidad.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, donde puedes establecer las preferencias globales.

- **Habilitar Notificaciones por Correo Electrónico para Cambios Manuales de Puntos:**
  - **Qué hace este ajuste:** Controla si los clientes reciben una notificación por correo electrónico cuando sus puntos de fidelidad son ajustados manualmente por un administrador.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Después de añadir o restar puntos manualmente a un cliente, se enviará un correo electrónico a su dirección de correo electrónico registrada, informándoles del cambio y de su nuevo saldo.
    - *Cuando está deshabilitado (NO):* No se enviarán notificaciones por correo electrónico a los clientes por ajustes manuales de puntos.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Habilita esto para mantener a los clientes completamente informados y comprometidos con su programa de fidelidad. Si un cliente recibe puntos como compensación, una notificación por correo electrónico confirma la acción y refuerza tu servicio al cliente. Si está deshabilitado, los clientes podrían no darse cuenta inmediatamente de que su saldo ha cambiado.

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

#### 2.2.1 Gestión Manual de Puntos de Fidelidad (Back Office > Módulos > Puntos de Fidelidad Manuales)

Esta es la pantalla principal donde gestionarás y registrarás todos los ajustes manuales de puntos de fidelidad. Puedes encontrar esta pantalla navegando a **Módulos > Puntos de Fidelidad Manuales** en el menú de tu Back Office de PrestaShop.

Esta pantalla presenta una lista de todos los ajustes históricos manuales de puntos de fidelidad. También puedes añadir nuevos ajustes desde aquí.

**Acciones y Ajustes Disponibles:**

- **Botón "Añadir nuevo ajuste de puntos de fidelidad":**

  - **Qué hace este botón:** Al hacer clic en este botón, accedes a un formulario donde puedes añadir o restar manualmente puntos de fidelidad a un cliente específico.
  - **Efecto de hacer clic en este botón:** Abre un nuevo formulario para crear una nueva entrada de puntos de fidelidad.
- **Formulario de Ajuste de Puntos de Fidelidad (Accedido a través de "Añadir nuevo ajuste de puntos de fidelidad"):**

  - **Campo de Búsqueda de Cliente:**

    - **Qué hace este campo:** Te permite buscar y seleccionar al cliente cuyos puntos de fidelidad deseas ajustar. Empieza a escribir el nombre o correo electrónico del cliente, y aparecerá una lista de clientes coincidentes.
    - **Efecto de cambiar este ajuste:** Una vez seleccionado un cliente, el ajuste se aplicará a su cuenta.
    - **Valor recomendado:** Selecciona el cliente correcto.
    - **Escenario / ejemplo del comerciante:** Necesitas añadir puntos a "Juan Pérez". Escribe "Juan" y selecciónalo del menú desplegable.
  - **Campo Puntos a Añadir/Restar:**

    - **Qué hace este campo:** Aquí es donde introduces el número de puntos de fidelidad a ajustar.
    - **Efecto de cambiar este ajuste:**
      - *Número positivo (por ejemplo, 50):* Añade 50 puntos al saldo de fidelidad del cliente.
      - *Número negativo (por ejemplo, -25):* Resta 25 puntos del saldo de fidelidad del cliente.
    - **Valor recomendado:** El número exacto de puntos que pretendes añadir o restar.
    - **Escenario / ejemplo del comerciante:** Un cliente recibió un artículo dañado, por lo que añades "100" puntos como compensación. Otro cliente devolvió un artículo por el que ganó puntos, por lo que restas "-50" puntos.
  - **Campo Período de Validez (Días):**

    - **Qué hace este campo:** Define cuántos días serán válidos los puntos añadidos manualmente a partir de la fecha del ajuste. Después de este período, los puntos caducarán.
    - **Efecto de cambiar este ajuste:**
      - *Establecido en un número (por ejemplo, 365):* Los puntos caducarán después de 365 días.
      - *Establecido en 0 o vacío:* Los puntos no tendrán fecha de caducidad (o seguirán la caducidad predeterminada de tu módulo principal de fidelidad, si lo hay).
    - **Valor recomendado:** Considera la estrategia general de tu programa de fidelidad. Si quieres fomentar un canje rápido, establece un período más corto. Para buena voluntad general, un período más largo o sin caducidad podría ser mejor.
    - **Escenario / ejemplo del comerciante:** Das 50 puntos como regalo de cumpleaños, válidos por "30" días para fomentar una compra rápida. Para una compensación importante, podrías dejarlo vacío para que no caduquen.
  - **Campo Razón / Comentario:**

    - **Qué hace este campo:** Un campo de texto para registrar la razón del ajuste de puntos de fidelidad. Esto es para seguimiento y auditoría interna.
    - **Efecto de cambiar este ajuste:** Este texto se guardará en el registro de fidelidad, proporcionando un historial claro de por qué se ajustaron los puntos. No es visible para el cliente.
    - **Valor recomendado:** Proporciona siempre una razón clara y concisa.
    - **Escenario / ejemplo del comerciante:** "Compensación por producto dañado #12345", "Regalo de cumpleaños para cliente VIP", "Puntos por participación en evento offline".
  - **Botón "Guardar":**

    - **Qué hace este botón:** Aplica el ajuste de puntos de fidelidad a la cuenta del cliente y guarda la entrada en el registro de historial.
    - **Efecto de hacer clic en este botón:** Los puntos de fidelidad del cliente se actualizan y aparece una nueva entrada en la tabla "Gestión Manual de Puntos de Fidelidad". Si las notificaciones por correo electrónico están habilitadas, el cliente recibe un correo electrónico.
- **Tabla de Historial de Puntos de Fidelidad:**

  - **Qué hace esta tabla:** Muestra una lista cronológica de todos los ajustes manuales de puntos de fidelidad realizados a través de este módulo.
  - **Columnas:**
    - **ID:** Identificador único para la entrada del registro.
    - **Cliente:** El nombre del cliente cuyos puntos fueron ajustados.
    - **Puntos:** El número de puntos añadidos o restados.
    - **Validez (Días):** El período de caducidad establecido para los puntos.
    - **Razón:** El comentario interno proporcionado para el ajuste.
    - **Fecha de Añadido:** La fecha y hora en que se realizó el ajuste.
    - **Administrador:** El nombre del administrador que realizó el ajuste.
  - **Efecto de los cambios:** Esta tabla proporciona una pista de auditoría completa. Puedes ordenar y filtrar entradas para revisar ajustes pasados.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1. Cuando surja una situación que requiera un ajuste manual de puntos (por ejemplo, queja de un cliente, promoción especial), navega a **Módulos > Puntos de Fidelidad Manuales**.
2. Haz clic en "Añadir nuevo ajuste de puntos de fidelidad".
3. Busca y selecciona al cliente.
4. Introduce el número de puntos (positivo para añadir, negativo para restar).
5. Establece un período de validez si lo deseas.
6. Fundamentalmente, añade una "Razón / Comentario" clara para futuras referencias.
7. Haz clic en "Guardar".
8. Revisa la tabla de historial para confirmar la entrada.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Notificaciones por Correo Electrónico | SÍ | Enviar correo electrónico al cliente sobre cambios manuales de puntos. |
| Puntos de Fidelidad Manuales | Búsqueda de Cliente | N/A | Seleccionar cliente para ajuste de puntos. |
| Puntos de Fidelidad Manuales | Puntos a Añadir/Restar | N/A | Introducir valor positivo o negativo para los puntos. |
| Puntos de Fidelidad Manuales | Período de Validez (Días) | Vacío (Sin Caducidad) | Establecer caducidad para los puntos añadidos manualmente. |
| Puntos de Fidelidad Manuales | Razón / Comentario | N/A | Nota interna para la pista de auditoría. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Añadí puntos, pero el cliente dice que no recibió un correo electrónico.**
R: Primero, verifica si "Habilitar Notificaciones por Correo Electrónico para Cambios Manuales de Puntos" está configurado en SÍ en la configuración del módulo. Si lo está, revisa los registros de correo electrónico de tu tienda (si están disponibles) o los registros de correo de tu servidor para ver si se envió el correo electrónico. Además, aconseja al cliente que revise su carpeta de spam o correo no deseado. Asegúrate de que la configuración de correo electrónico de tu PrestaShop esté correctamente configurada y enviando correos electrónicos con éxito.

**P: El saldo de puntos de fidelidad del cliente no se actualizó después de que añadí puntos.**
R: Este módulo actualiza el sistema central de fidelidad de PrestaShop. Si el saldo no se muestra, primero borra la caché de tu PrestaShop (Parámetros Avanzados > Rendimiento > Borrar caché). Si el problema persiste, asegúrate de que tu módulo principal de fidelidad (por ejemplo, el módulo de fidelidad predeterminado de PrestaShop o `myprestaloyalty`) esté correctamente instalado y activo, ya que este módulo depende de él.

**P: ¿Puedo editar un ajuste de puntos de fidelidad después de haberlo guardado?**
R: No, por motivos de auditoría e integridad de los datos, los ajustes individuales de puntos de fidelidad no se pueden editar una vez guardados. Si cometiste un error, debes añadir un *nuevo* ajuste para corregirlo (por ejemplo, si accidentalmente añadiste 100 puntos en lugar de 50, añade una nueva entrada restando 50 puntos) y anota claramente la corrección en el campo "Razón / Comentario".

**P: ¿Qué sucede si resto más puntos de los que tiene un cliente?**
R: El sistema normalmente permitirá la resta, lo que resultará en un saldo negativo de puntos de fidelidad para el cliente. Esto podría ser útil en escenarios específicos, pero generalmente, debes asegurarte de que los clientes tengan suficientes puntos antes de restar.

**P: ¿Cómo sé quién hizo un ajuste de puntos específico?**
R: La columna "Administrador" en la tabla de historial de "Gestión Manual de Puntos de Fidelidad" muestra claramente qué cuenta de administrador realizó cada ajuste, proporcionando una pista de auditoría completa.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo `Manual Loyalty Points & History` (myprestaloyalty_manual) está diseñado como un módulo estándar de PrestaShop, que extiende la funcionalidad principal de fidelidad. Opera principalmente dentro del Back Office, proporcionando una interfaz administrativa para ajustes manuales de puntos y registro. Aprovecha el patrón MVC de PrestaShop para su controlador de administración y utiliza un `ObjectModel` para el almacenamiento persistente de entradas de registro manuales. El módulo se integra con el sistema de fidelidad existente manipulando directamente los puntos de fidelidad del cliente.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**: Este módulo no incluye ningún controlador dedicado al front-office. Toda la visualización de puntos de fidelidad orientada al cliente es manejada por el módulo principal de fidelidad.
- **Controladores de Administración del Back-Office**:

  - `controllers/admin/AdminMyprestaloyaltyManualController.php`

    - **Nombre de la clase y clase padre**: `AdminMyprestaloyaltyManualController` extiende `ModuleAdminController`.
    - **Responsabilidad**: Este es el controlador administrativo principal para gestionar los ajustes manuales de puntos de fidelidad. Maneja la visualización de la lista de registros de fidelidad (usando `HelperList`) y el formulario para añadir nuevos ajustes (usando `HelperForm`). Procesa los envíos de formularios, valida datos, crea objetos `MyprestaloyaltyManualLog` y actualiza los puntos de fidelidad del cliente. También activa las notificaciones por correo electrónico si están habilitadas.
    - **Nombre de la pestaña**: "Puntos de Fidelidad Manuales" (en el menú Módulos).
    - **Entidad gestionada**: `MyprestaloyaltyManualLog` (el registro de ajustes manuales).
  - `controllers/admin/index.php`

    - **Responsabilidad**: Este es un archivo de marcador de posición vacío, a menudo incluido en los directorios `controllers/admin` de los módulos de PrestaShop para evitar la lista de directorios. No contiene ninguna lógica de controlador funcional.

### 4.3 Clases y Modelos Principales (`classes/`)

- `classes/index.php`

  - **Responsabilidad**: Archivo de marcador de posición vacío para evitar la lista de directorios.
- `classes/MyprestaloyaltyManualLog.php`

  - **Con qué tabla de base de datos interactúa**: `ps_myprestaloyalty_manual_log`
  - **Extiende `ObjectModel`**: Sí.
  - **Campos de `$definition`**:
    - `id_myprestaloyalty_manual_log`: Clave primaria.
    - `id_customer`: ID del cliente afectado.
    - `points`: Número de puntos ajustados (puede ser positivo o negativo).
    - `validity`: Período de validez en días para los puntos.
    - `reason`: Razón textual del ajuste.
    - `id_employee`: ID del administrador que realizó el ajuste.
    - `date_add`: Marca de tiempo de cuándo se añadió la entrada.
  - **Métodos públicos clave y lógica de negocio encapsulada**:
    - Métodos estándar de `ObjectModel` (`add`, `update`, `delete`).
    - Maneja la validación de datos para sus campos.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. Se utiliza el JS estándar de PrestaShop para el manejo de formularios y AJAX (por ejemplo, búsqueda de clientes).

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Se basa en el estilo predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Se basa en las plantillas predeterminadas `HelperList` y `HelperForm` de PrestaShop para su interfaz de Back Office.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - `ps_myprestaloyalty_manual_log`:
    - `id_myprestaloyalty_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `points` INT(10) NOT NULL
    - `validity` INT(10) UNSIGNED DEFAULT 0
    - `reason` TEXT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_manual_log`)
    - KEY `id_customer` (`id_customer`)
- **Registros de Configuración (en `ps_configuration`)**:

  - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Almacena el valor booleano (0 o 1) para habilitar/deshabilitar las notificaciones por correo electrónico.
- **Tabla de Hooks Registrados**:

  | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office. | Se utiliza para incluir CSS/JS específicos del módulo (aunque este módulo no tiene ninguno) o para registrar elementos del menú de administración. |
  | `actionCustomerAccountAdd` | Después de que se crea una nueva cuenta de cliente. | No utilizado explícitamente por este módulo, pero un hook de fidelidad común. |
  | `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | No utilizado explícitamente por este módulo, pero un hook de fidelidad común. |
  | `actionObjectCustomerUpdateAfter` | Después de que se actualiza un objeto de cliente. | No utilizado explícitamente por este módulo. |
  | `actionObjectCustomerDeleteAfter` | Después de que se elimina un objeto de cliente. | No utilizado explícitamente por este módulo. |

  *Nota: La funcionalidad principal del módulo (añadir/restar puntos) se activa directamente desde su Controlador de Administración, no a través de hooks del front-office. El módulo interactúa con los métodos del sistema de fidelidad central para ajustar los puntos.*

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Manual Loyalty Points & History", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con la funcionalidad del módulo.
