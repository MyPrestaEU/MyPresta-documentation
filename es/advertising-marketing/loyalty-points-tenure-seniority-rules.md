---
title: "Puntos de fidelidad – Reglas de antigüedad (tenencia) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Puntos de fidelidad – Reglas de antigüedad (tenencia) de MyPresta.eu."
sidebar:
  label: "Puntos de fidelidad – Reglas de antigüedad (tenencia) - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Loyalty points – Tenure (seniority) rules en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-tenure-seniority-rules.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/loyalty-points-tenure-seniority-rules/)
>
> ---


# Puntos de fidelidad – Reglas de antigüedad (tenencia)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y generalmente están disponibles en la mayoría de los entornos de alojamiento. Este módulo no tiene requisitos específicos adicionales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, a la que se accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

**Configuración general**

-   **Activar módulo:**

    -   **Qué hace esta configuración:** Este es el interruptor maestro para activar o desactivar toda la funcionalidad del módulo.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* El módulo comenzará a procesar las reglas de fidelidad basadas en la antigüedad del cliente y a otorgar puntos según lo configurado.
        -   *Cuando está desactivado:* El módulo dejará de funcionar. No se otorgarán nuevos puntos basados en las reglas de antigüedad, y las reglas existentes se ignorarán hasta que se vuelvan a activar.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Ha terminado de configurar sus reglas y está listo para lanzar su programa de fidelidad. Active esto para comenzar a recompensar a los clientes. Si necesita pausar temporalmente el programa para mantenimiento o revisión, puede desactivarlo aquí.
-   **URL de la tarea Cron:**

    -   **Qué hace esta configuración:** Muestra una URL única que debe configurar como una "tarea cron" en su servidor web. Una tarea cron es una tarea programada que le indica a su servidor que ejecute esta URL automáticamente a intervalos regulares (por ejemplo, una vez al día). Así es como el módulo verifica la antigüedad del cliente y otorga puntos sin que usted tenga que activarlo manualmente.
    -   **Efecto de cambiar esta configuración:** No puede cambiar esta URL directamente. Es generada por el módulo.
        -   *Cuando se configura correctamente como una tarea cron:* El módulo ejecutará automáticamente sus comprobaciones y otorgará puntos de acuerdo con sus reglas.
        -   *Cuando NO se configura como una tarea cron:* La asignación automática de puntos del módulo no ocurrirá. Tendría que visitar manualmente esta URL en su navegador para activar el proceso, lo que anula el propósito de la automatización.
    -   **Valor recomendado:** Copie esta URL y configúrela como una tarea cron diaria en su servidor.
    -   **Escenario / ejemplo de comerciante:** Después de instalar el módulo, copie esta URL. Vaya a su panel de control de alojamiento (por ejemplo, cPanel, Plesk) y busque la sección "Tareas Cron" o "Tareas programadas". Agregue una nueva tarea cron para ejecutar esta URL una vez cada 24 horas. Esto asegura que sus clientes reciban sus puntos de antigüedad automáticamente y a tiempo.

### 2.2 Pantalla de administración dedicada: Reglas de antigüedad de fidelidad (Back Office > MyPresta.eu > Reglas de antigüedad de fidelidad)

Esta pantalla le permite definir y administrar las reglas específicas para otorgar puntos de fidelidad basados en la antigüedad del cliente.

-   **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **MyPresta.eu > Reglas de antigüedad de fidelidad** en el menú de su Back Office de PrestaShop.
-   **Acciones y configuraciones disponibles:**

    -   **Tabla de listado de reglas:** Esta tabla muestra todas sus reglas de antigüedad activas e inactivas. Para cada regla, verá:
        -   **ID:** Un identificador único para la regla.
        -   **Antigüedad (Días):** El número mínimo de días que un cliente debe haber estado registrado para calificar para esta regla.
        -   **Puntos a otorgar:** El número de puntos de fidelidad que recibirá un cliente.
        -   **Activo:** Un interruptor para activar o desactivar la regla.
        -   **Acciones:** Botones para "Editar" o "Eliminar" una regla.
    -   **Botón "Añadir nueva regla":** Haga clic en este botón para crear una nueva regla de antigüedad.

    **Al añadir/editar una regla:**
    Se le presentará un formulario para definir los parámetros de la regla:

    -   **Antigüedad (Días):**

        -   **Qué hace esta configuración:** Este es el número mínimo de días que un cliente debe haber estado registrado en su tienda para ser elegible para esta asignación específica de puntos de fidelidad.
        -   **Efecto de cambiar esta configuración:**
            -   *Configurar en 365:* Los clientes registrados durante al menos un año calificarán.
            -   *Configurar en 730:* Los clientes registrados durante al menos dos años calificarán.
        -   **Valor recomendado:** Elija valores que representen hitos significativos para sus clientes (por ejemplo, 365 días para 1 año, 730 días para 2 años, 1095 días para 3 años).
        -   **Escenario / ejemplo de comerciante:** Desea recompensar a los clientes que han estado en su tienda durante al menos un año. Lo configuraría en `365`.
    -   **Puntos a otorgar:**

        -   **Qué hace esta configuración:** Este es el número exacto de puntos de fidelidad que se otorgarán a un cliente que cumpla con el requisito de "Antigüedad (Días)" para esta regla.
        -   **Efecto de cambiar esta configuración:**
            -   *Configurar en 100:* Los clientes que califiquen reciben 100 puntos de fidelidad.
            -   *Configurar en 50:* Los clientes que califiquen reciben 50 puntos de fidelidad.
        -   **Valor recomendado:** Alinee esto con el valor de su programa de puntos de fidelidad existente. Un buen punto de partida podría ser puntos equivalentes a un pequeño descuento (por ejemplo, 5-10% del valor promedio de un pedido).
        -   **Escenario / ejemplo de comerciante:** Para dar un agradecimiento significativo por un año de fidelidad, podría otorgar `250` puntos, lo que podría traducirse en un descuento de 5 € en su próxima compra.
    -   **Activo:**

        -   **Qué hace esta configuración:** Este interruptor determina si esta regla específica está actualmente activa y será considerada por el módulo al otorgar puntos.
        -   **Efecto de cambiar esta configuración:**
            -   *Cuando está activado:* La regla será procesada por la tarea cron, y se otorgarán puntos a los clientes que califiquen.
            -   *Cuando está desactivado:* La regla será ignorada, y no se otorgarán puntos basados en este umbral de antigüedad específico.
        -   **Valor recomendado:** SÍ (para las reglas que desea que estén activas).
        -   **Escenario / ejemplo de comerciante:** Ha creado una regla para 5 años de antigüedad pero desea probarla internamente antes de ponerla en marcha. Puede mantenerla desactivada hasta que esté listo para activarla.
-   **Efecto de los cambios:**

    -   Agregar una nueva regla crea una nueva entrada en la base de datos que la tarea cron del módulo verificará.
    -   Editar una regla modifica sus parámetros (antigüedad, puntos, estado activo), afectando futuras asignaciones de puntos.
    -   Eliminar una regla la elimina permanentemente, y no se otorgarán más puntos basados en esa antigüedad específica.
    -   La clave de configuración `PS_LIST_LIMIT` controla el número de elementos mostrados por página en la tabla de listado de reglas.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

    1.  **Planifique sus niveles de fidelidad:** Decida qué hitos de antigüedad desea recompensar (por ejemplo, 1 año, 2 años, 5 años).
    2.  **Calcule los valores de los puntos:** Determine cuántos puntos desea otorgar para cada nivel, considerando el valor monetario de sus puntos de fidelidad.
    3.  **Cree reglas:** Vaya a **MyPresta.eu > Reglas de antigüedad de fidelidad** y haga clic en "Añadir nueva regla" para cada nivel.
    4.  **Supervise:** Verifique periódicamente los saldos de puntos de fidelidad de sus clientes y asegúrese de que la tarea cron se esté ejecutando correctamente.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e impacto
El módulo "Puntos de fidelidad – Reglas de antigüedad (tenencia)" está diseñado para recompensar a sus clientes con puntos de fidelidad en función del tiempo que llevan registrados en su tienda PrestaShop. Esto le ayuda a reconocer y retener a sus clientes más leales al otorgarles automáticamente puntos de bonificación a medida que alcanzan ciertos hitos de "antigüedad" (por ejemplo, 1 año, 2 años, 5 años desde el registro).

## 3. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y generalmente están disponibles en la mayoría de los entornos de alojamiento. Este módulo no tiene requisitos específicos adicionales más allá de una configuración estándar de PrestaShop.

## 4. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 4.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, a la que se accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

**Configuración general**

-   **Activar módulo:**

    -   **Qué hace esta configuración:** Este es el interruptor maestro para activar o desactivar toda la funcionalidad del módulo.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* El módulo comenzará a procesar las reglas de fidelidad basadas en la antigüedad del cliente y a otorgar puntos según lo configurado.
        -   *Cuando está desactivado:* El módulo dejará de funcionar. No se otorgarán nuevos puntos basados en las reglas de antigüedad, y las reglas existentes se ignorarán hasta que se vuelvan a activar.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Ha terminado de configurar sus reglas y está listo para lanzar su programa de fidelidad. Active esto para comenzar a recompensar a los clientes. Si necesita pausar temporalmente el programa para mantenimiento o revisión, puede desactivarlo aquí.
-   **URL de la tarea Cron:**

    -   **Qué hace esta configuración:** Muestra una URL única que debe configurar como una "tarea cron" en su servidor web. Una tarea cron es una tarea programada que le indica a su servidor que ejecute esta URL automáticamente a intervalos regulares (por ejemplo, una vez al día). Así es como el módulo verifica la antigüedad del cliente y otorga puntos sin que usted tenga que activarlo manualmente.
    -   **Efecto de cambiar esta configuración:** No puede cambiar esta URL directamente. Es generada por el módulo.
        -   *Cuando se configura correctamente como una tarea cron:* El módulo ejecutará automáticamente sus comprobaciones y otorgará puntos de acuerdo con sus reglas.
        -   *Cuando NO se configura como una tarea cron:* La asignación automática de puntos del módulo no ocurrirá. Tendría que visitar manualmente esta URL en su navegador para activar el proceso, lo que anula el propósito de la automatización.
    -   **Valor recomendado:** Copie esta URL y configúrela como una tarea cron diaria en su servidor.
    -   **Escenario / ejemplo de comerciante:** Después de instalar el módulo, copie esta URL. Vaya a su panel de control de alojamiento (por ejemplo, cPanel, Plesk) y busque la sección "Tareas Cron" o "Tareas programadas". Agregue una nueva tarea cron para ejecutar esta URL una vez cada 24 horas. Esto asegura que sus clientes reciban sus puntos de antigüedad automáticamente y a tiempo.

### 4.2 Pantalla de administración dedicada: Reglas de antigüedad de fidelidad (Back Office > MyPresta.eu > Reglas de antigüedad de fidelidad)

Esta pantalla le permite definir y administrar las reglas específicas para otorgar puntos de fidelidad basados en la antigüedad del cliente.

-   **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **MyPresta.eu > Reglas de antigüedad de fidelidad** en el menú de su Back Office de PrestaShop.
-   **Acciones y configuraciones disponibles:**

    -   **Tabla de listado de reglas:** Esta tabla muestra todas sus reglas de antigüedad activas e inactivas. Para cada regla, verá:
        -   **ID:** Un identificador único para la regla.
        -   **Antigüedad (Días):** El número mínimo de días que un cliente debe haber estado registrado para calificar para esta regla.
        -   **Puntos a otorgar:** El número de puntos de fidelidad que recibirá un cliente.
        -   **Activo:** Un interruptor para activar o desactivar la regla.
        -   **Acciones:** Botones para "Editar" o "Eliminar" una regla.
    -   **Botón "Añadir nueva regla":** Haga clic en este botón para crear una nueva regla de antigüedad.

    **Al añadir/editar una regla:**
    Se le presentará un formulario para definir los parámetros de la regla:

    -   **Antigüedad (Días):**

        -   **Qué hace esta configuración:** Este es el número mínimo de días que un cliente debe haber estado registrado en su tienda para ser elegible para esta asignación específica de puntos de fidelidad.
        -   **Efecto de cambiar esta configuración:**
            -   *Configurar en 365:* Los clientes registrados durante al menos un año calificarán.
            -   *Configurar en 730:* Los clientes registrados durante al menos dos años calificarán.
        -   **Valor recomendado:** Elija valores que representen hitos significativos para sus clientes (por ejemplo, 365 días para 1 año, 730 días para 2 años, 1095 días para 3 años).
        -   **Escenario / ejemplo de comerciante:** Desea recompensar a los clientes que han estado con su tienda durante al menos un año. Lo configuraría en `365`.
    -   **Puntos a otorgar:**

        -   **Qué hace esta configuración:** Este es el número exacto de puntos de fidelidad que se otorgarán a un cliente que cumpla con el requisito de "Antigüedad (Días)" para esta regla.
        -   **Efecto de cambiar esta configuración:**
            -   *Configurar en 100:* Los clientes que califiquen reciben 100 puntos de fidelidad.
            -   *Configurar en 50:* Los clientes que califiquen reciben 50 puntos de fidelidad.
        -   **Valor recomendado:** Alinee esto con el valor de su programa de puntos de fidelidad existente. Un buen punto de partida podría ser puntos equivalentes a un pequeño descuento (por ejemplo, 5-10% del valor promedio de un pedido).
        -   **Escenario / ejemplo de comerciante:** Para dar un agradecimiento significativo por un año de fidelidad, podría otorgar `250` puntos, lo que podría traducirse en un descuento de 5 € en su próxima compra.
    -   **Activo:**

        -   **Qué hace esta configuración:** Este interruptor determina si esta regla específica está actualmente activa y será considerada por el módulo al otorgar puntos.
        -   **Efecto de cambiar esta configuración:**
            -   *Cuando está activado:* La regla será procesada por la tarea cron, y se otorgarán puntos a los clientes que califiquen.
            -   *Cuando está desactivado:* La regla será ignorada, y no se otorgarán puntos basados en este umbral de antigüedad específico.
        -   **Valor recomendado:** SÍ (para las reglas que desea que estén activas).
        -   **Escenario / ejemplo de comerciante:** Ha creado una regla para 5 años de antigüedad pero desea probarla internamente antes de ponerla en marcha. Puede mantenerla desactivada hasta que esté listo para activarla.
-   **Efecto de los cambios:**

    -   Agregar una nueva regla crea una nueva entrada en la base de datos que la tarea cron del módulo verificará.
    -   Editar una regla modifica sus parámetros (antigüedad, puntos, estado activo), afectando futuras asignaciones de puntos.
    -   Eliminar una regla la elimina permanentemente, y no se otorgarán más puntos basados en esa antigüedad específica.
    -   La clave de configuración `PS_LIST_LIMIT` controla el número de elementos mostrados por página en la tabla de listado de reglas.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

    1.  **Planifique sus niveles de fidelidad:** Decida qué hitos de antigüedad desea recompensar (por ejemplo, 1 año, 2 años, 5 años).
    2.  **Calcule los valores de los puntos:** Determine cuántos puntos desea otorgar para cada nivel, considerando el valor monetario de sus puntos de fidelidad.
    3.  **Cree reglas:** Vaya a **MyPresta.eu > Reglas de antigüedad de fidelidad** y haga clic en "Añadir nueva regla" para cada nivel.
    4.  **Supervise:** Verifique periódicamente los saldos de puntos de fidelidad de sus clientes y asegúrese de que la tarea cron se esté ejecutando correctamente.

### 4.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e impacto

## 5. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no reciben puntos de fidelidad, aunque he configurado las reglas.**
R1:

-   **Verificar la activación del módulo:** Asegúrese de que la configuración "Activar módulo" en la página de configuración principal esté establecida en SÍ.
-   **Verificar la tarea Cron:** La razón más común es una tarea cron configurada incorrectamente o que no se está ejecutando. Vuelva a verificar la URL de la tarea Cron desde la página de configuración del módulo y asegúrese de que esté configurada correctamente en su servidor de alojamiento para que se ejecute diariamente.
-   **Estado de la regla:** Asegúrese de que las reglas individuales de antigüedad de fidelidad que ha creado estén marcadas como "Activas".
-   **Elegibilidad del cliente:** ¿Ha cumplido el cliente realmente el requisito de "Antigüedad (Días)" para alguna de sus reglas activas? El módulo solo otorga puntos una vez que un cliente cruza un umbral.
-   **Caché de Smarty:** A veces, la caché de PrestaShop puede causar problemas de visualización. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).

**P2: ¿Cómo sé si la tarea cron se está ejecutando correctamente?**
R2:

-   **Verificar los registros de alojamiento:** La mayoría de los proveedores de alojamiento ofrecen una forma de ver los registros de ejecución de tareas cron en su panel de control (por ejemplo, cPanel). Busque entradas relacionadas con la URL de la tarea cron proporcionada por el módulo.
-   **Prueba manual:** Puede visitar manualmente la URL de la tarea Cron en su navegador web. Esto activará el proceso de asignación de puntos en ese momento. Si se otorgan puntos a los clientes elegibles después de esta visita manual, confirma que la lógica del módulo está funcionando y que el problema está en la configuración automatizada de la tarea cron.

**P3: ¿Puedo otorgar puntos retroactivamente a los clientes que ya superaron un hito de antigüedad antes de instalar el módulo?**
R3: Sí, cuando la tarea cron se ejecute por primera vez después de haber configurado las reglas, evaluará a todos los clientes existentes con respecto a sus reglas activas. Si un cliente cumple un requisito de antigüedad y no se le han otorgado puntos para esa regla específica antes, los recibirá. Esto significa que los clientes más antiguos y leales obtendrán sus puntos merecidos.

**P4: Mi tema personalizado no muestra los puntos de fidelidad correctamente, o las notificaciones se ven mal.**
R4: Este módulo interactúa principalmente con el sistema de fidelidad central de PrestaShop. Cualquier problema de visualización con los puntos de fidelidad o las notificaciones suele estar relacionado con el estilo de su tema o las anulaciones del módulo de fidelidad nativo.

-   **Personalización del tema:** Si tiene un tema personalizado, podría tener sus propias plantillas o CSS para mostrar la información de fidelidad. Es posible que deba consultar a su desarrollador de temas o a un webmaster para asegurarse de que se integre correctamente con las funciones de fidelidad de PrestaShop.
-   **Prueba con el tema predeterminado:** Cambie temporalmente al tema predeterminado de PrestaShop (Classic) para ver si el problema persiste. Si funciona correctamente en el tema predeterminado, el problema es definitivamente con su tema personalizado.

**P5: ¿Qué sucede si cambio una regla (por ejemplo, aumento los puntos) después de que los clientes ya hayan recibido puntos de ella?**
R5: El módulo está diseñado para otorgar puntos *una vez* por cada regla cuando un cliente cumple por primera vez el umbral de antigüedad. Si cambia una regla (por ejemplo, aumenta los puntos por 365 días de 100 a 150), los clientes que ya recibieron 100 puntos por 365 días *no* recibirán automáticamente los 50 puntos adicionales. La regla ya ha sido "satisfecha" para ellos. Si desea darles los puntos adicionales, deberá ajustar manualmente su saldo de fidelidad o crear una nueva regla temporal.

## 6. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 6.1 Resumen de la arquitectura

El módulo "Puntos de fidelidad – Reglas de antigüedad (tenencia)" (`myprestaloyalty_tenure`) extiende la funcionalidad de PrestaShop introduciendo un nuevo concepto de asignación de puntos de fidelidad basado en la antigüedad del registro del cliente. Sigue una arquitectura de módulo estándar de PrestaShop, aprovechando `ObjectModel` para gestionar las reglas de antigüedad y un controlador frontal dedicado para la ejecución de tareas cron. El módulo se integra con el `LoyaltyModule` central de PrestaShop para otorgar puntos, asegurando la compatibilidad con el sistema de fidelidad nativo.

### 6.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/cron.php`
        -   **Nombre de la clase:** `MyprestaloyaltyTenureCronModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Este controlador está diseñado para ser ejecutado a través de una tarea cron. Cuando se accede, itera a través de todas las reglas de antigüedad activas y todos los clientes registrados. Para cada cliente, calcula su edad de registro y verifica si califica para alguna regla activa para la cual aún no ha recibido puntos. Si un cliente califica, otorga los puntos de fidelidad especificados utilizando la funcionalidad del `LoyaltyModule` central. Normalmente devuelve un mensaje de éxito simple o una salida de registro.
    -   `controllers/front/index.php`
        -   **Nombre de la clase:** `MyprestaloyaltyTenureIndexModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Este es un controlador frontal predeterminado o de marcador de posición. En muchos módulos, si no se define ninguna acción específica, `index.php` podría manejar una vista predeterminada o una redirección. Para este módulo, su interacción principal con el front-office es a través del controlador `cron.php`.
-   **Controladores de administración de Back-Office**:

    -   `controllers/admin/AdminMyprestaloyaltyTenureController.php`
        -   **Nombre de la clase:** `AdminMyprestaloyaltyTenureController` (extiende `ModuleAdminController`)
        -   **Nombre de la pestaña:** "Reglas de antigüedad de fidelidad" (bajo el menú MyPresta.eu)
        -   **Entidad gestionada:** `MyprestaloyaltyTenureRule` (se asigna a la tabla de base de datos `_myprestaloyalty_tenure_rule`)
        -   **Responsabilidad:** Este controlador proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) para gestionar las reglas de antigüedad de fidelidad en el Back Office de PrestaShop. Utiliza `HelperList` para mostrar la lista de reglas y `HelperForm` para añadir/editar reglas individuales. Maneja el envío de formularios, la validación y la interacción con el `ObjectModel` `MyprestaloyaltyTenureRule`.
    -   `controllers/admin/index.php`
        -   **Nombre de la clase:** (Sin clase específica, normalmente utilizada para seguridad)
        -   **Responsabilidad:** Este archivo suele contener un simple `header('Location: ../../index.php?controller=AdminHome'); exit;` o similar para evitar la lista directa de directorios y asegurar que los controladores de administración se accedan a través del despachador de PrestaShop.

### 6.3 Clases y modelos principales (`classes/`)

-   `classes/index.php`

    -   **Responsabilidad:** Archivo de seguridad estándar de PrestaShop, que normalmente contiene `header('Location: ../../index.php?controller=AdminHome'); exit;` para evitar el acceso directo al directorio `classes`.
-   `classes/MyprestaloyaltyTenureRule.php`

    -   **Nombre de la clase:** `MyprestaloyaltyTenureRule` (extiende `ObjectModel`)
    -   **Tabla de base de datos:** `_myprestaloyalty_tenure_rule`
    -   **Campos `$definition`:**
        -   `id_myprestaloyalty_tenure_rule`: Clave primaria.
        -   `tenure_days`: Entero, el número mínimo de días que un cliente debe estar registrado.
        -   `points_to_award`: Entero, el número de puntos de fidelidad a otorgar.
        -   `active`: Booleano, si la regla está activa (0 o 1).
    -   **Métodos públicos clave:**
        -   `__construct()`: Constructor estándar de `ObjectModel`.
        -   `add()`: Sobrescribe `ObjectModel::add()` para lógica personalizada si es necesario (por ejemplo, manejo de fechas, validación).
        -   `update()`: Sobrescribe `ObjectModel::update()`.
        -   `delete()`: Sobrescribe `ObjectModel::delete()`.
        -   `getAllActiveRules()`: Método estático para recuperar todas las reglas activas de la base de datos.
        -   `hasCustomerReceivedPointsForRule($id_customer, $id_rule)`: Método estático para verificar si un cliente específico ya ha recibido puntos para una regla determinada. Esto es crucial para evitar asignaciones duplicadas.
        -   `markCustomerAsAwarded($id_customer, $id_rule)`: Método estático para registrar que un cliente ha recibido puntos para una regla.

### 6.4 Activos JavaScript (`views/js/`)

El dossier del módulo indica que no hay archivos JavaScript personalizados presentes en `views/js/`. Todas las interacciones se manejan en el lado del servidor o a través de los ayudantes estándar de formularios/listas de PrestaShop.

### 6.5 Hojas de estilo CSS (`views/css/`)

El dossier del módulo indica que no hay archivos CSS personalizados presentes en `views/css/`. La interfaz del Back Office se basa en los estilos del tema de administración predeterminado de PrestaShop.

### 6.6 Estructura de la plantilla Smarty (`views/templates/`)

El dossier del módulo indica que no hay archivos de plantilla Smarty personalizados presentes en `views/templates/`. Las pantallas de configuración y gestión de reglas del módulo se renderizan utilizando las clases `HelperForm` y `HelperList` de PrestaShop, que se basan en los archivos de plantilla principales de PrestaShop.

### 6.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:

    -   `ps_myprestaloyalty_tenure_rule`: Almacena las definiciones de cada regla de antigüedad.
        -   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `tenure_days` INT(10) UNSIGNED NOT NULL
        -   `points_to_award` INT(10) UNSIGNED NOT NULL
        -   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        -   PRIMARY KEY (`id_myprestaloyalty_tenure_rule`)
    -   `ps_myprestaloyalty_tenure_awarded`: Registra qué clientes han recibido puntos para qué reglas, para evitar asignaciones duplicadas.
        -   `id_myprestaloyalty_tenure_awarded` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_customer` INT(10) UNSIGNED NOT NULL
        -   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL
        -   `date_awarded` DATETIME NOT NULL
        -   PRIMARY KEY (`id_myprestaloyalty_tenure_awarded`)
        -   UNIQUE KEY `customer_rule` (`id_customer`, `id_myprestaloyalty_tenure_rule`)
-   **Tabla de ganchos registrados**:
    El módulo no registra explícitamente ningún gancho de visualización de front-office (como `displayHeader`, `displayRightColumn`, `displayProductExtraContent`, `displayFooter`), ya que su función principal es el procesamiento en segundo plano a través de cron.
    Utiliza implícitamente:

    | Nombre del gancho | Momento de ejecución | Propósito técnico |
    | --- | --- | --- |
    | `actionModuleInstall` | Durante la instalación del módulo | Crea tablas de base de datos, registra la pestaña de administración. |
    | `actionModuleUninstall` | Durante la desinstalación del módulo | Elimina tablas de base de datos y configuración. |
    | `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración | Si el módulo tuviera JS/CSS personalizado para el administrador, lo registraría aquí. (No se usa en este módulo según el inventario) |
    | `displayBackOfficeTop` | Renderiza contenido en la parte superior del Back Office | Se utiliza para mostrar la URL de la tarea cron y las instrucciones en la página de configuración del módulo. |

## 7. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Puntos de fidelidad – Reglas de antigüedad (tenencia)", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a brindar asistencia oportuna y garantizar que su módulo funcione de manera óptima.

-   **Acceder a descargas y actualizaciones:** Inicie sesión en su cuenta en [Historial de pedidos y descargas de MyPresta.eu](https://mypresta.eu/my-account/orders/).
-   **Contactar con soporte:** Utilice los canales de soporte proporcionados dentro de su cuenta MyPresta.eu para cualquier problema técnico o pregunta.
