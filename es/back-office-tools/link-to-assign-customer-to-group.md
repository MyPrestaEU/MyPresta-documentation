---
title: "Enlace para asignar cliente a grupo - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Enlace para asignar cliente a grupo' de MyPresta.eu."
sidebar:
  label: "Enlace para asignar cliente a grupo"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Link to assign customer to group en MyPresta.eu](https://mypresta.eu/modules/administration-tools/link-to-assign-customer-to-group.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/link-to-assign-customer-to-group/)
>
> ---


# Enlace para asignar cliente a grupo

## 1. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Configurar Enlace para asignar cliente a grupo)

Esta es la pantalla de configuración principal y única del módulo. Aquí puede definir cómo se comporta el módulo al asignar clientes a grupos.

#### **Cambiar grupo a predeterminado**
-   **Qué hace este ajuste:** Este ajuste determina si el módulo también debe asignar al cliente al grupo de clientes "Predeterminado" además del grupo especificado en la URL.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Si un cliente hace clic en un enlace para ser asignado al "Grupo X", también será asignado al grupo "Predeterminado". Esto significa que será parte tanto del "Grupo X" como del "Predeterminado". Esto puede ser útil si su grupo "Predeterminado" tiene ciertos permisos base o descuentos que siempre desea que los clientes tengan, independientemente de otros grupos a los que se unan.
    -   *Cuando está deshabilitado (NO):* El cliente solo será asignado al grupo especificado en la URL (por ejemplo, "Grupo X"). No se le añadirá automáticamente al grupo "Predeterminado" a menos que ya forme parte de él o que otro mecanismo lo añada.
-   **Valor recomendado:** **NO**. En la mayoría de los casos, desea asignar clientes a un grupo *específico* sin necesariamente añadirlos al grupo "Predeterminado", especialmente si su grupo "Predeterminado" no tiene un significado especial o si desea gestionar los grupos con mayor precisión. Habilite esto solo si tiene una razón específica para incluir siempre el grupo "Predeterminado".
-   **Escenario / ejemplo de comerciante:** Tiene un grupo "VIP" con descuentos especiales. Si habilita esto, un cliente que haga clic en un enlace VIP estará tanto en "VIP" como en "Predeterminado". Si "Predeterminado" tiene un descuento del 5% en toda la tienda y "VIP" tiene un descuento del 15% en productos específicos, el cliente se beneficiará de ambos donde sea aplicable. Si está deshabilitado, solo obtendría los beneficios "VIP".

#### **Desasignar cliente de otros grupos**
-   **Qué hace este ajuste:** Este ajuste controla si el módulo debe eliminar al cliente de *todos los demás* grupos de clientes cuando se le asigna a un nuevo grupo a través del enlace especial.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Si un cliente está actualmente en el "Grupo A" y el "Grupo B", y luego hace clic en un enlace para ser asignado al "Grupo X", será eliminado del "Grupo A" y del "Grupo B", y solo permanecerá en el "Grupo X" (y potencialmente en "Predeterminado" si el ajuste anterior está habilitado). Esto asegura que el cliente esté *solo* en el grupo objetivo.
    -   *Cuando está deshabilitado (NO):* El cliente será *añadido* al nuevo grupo ("Grupo X") pero *permanecerá* en cualquier otro grupo del que ya formara parte (por ejemplo, "Grupo A", "Grupo B"). Esto permite que los clientes sean miembros de varios grupos simultáneamente.
-   **Valor recomendado:** **NO**. Permitir que los clientes estén en varios grupos ofrece más flexibilidad para una segmentación compleja. Habilite esto solo si necesita grupos estrictos y mutuamente excluyentes (por ejemplo, un cliente solo puede ser "Minorista" O "Mayorista", nunca ambos).
-   **Escenario / ejemplo de comerciante:**
    -   *Habilitado (SÍ):* Tiene grupos de "Cliente estándar" y "Cliente mayorista". Un cliente hace clic en un enlace para convertirse en "Mayorista". Si está habilitado, se le elimina de "Cliente estándar" y solo permanece como "Mayorista". Esto es ideal para tipos de clientes claros y distintos.
    -   *Deshabilitado (NO):* Tiene grupos de "Suscriptor de boletín" y "Miembro del programa de fidelización". Un cliente hace clic en un enlace para unirse al "Programa de fidelización". Si está deshabilitado, permanece como "Suscriptor de boletín" *y* se convierte en "Miembro del programa de fidelización". Esto es ideal para beneficios aditivos.

#### **Cómo crear el enlace especial**
El módulo funciona añadiendo un parámetro especial a cualquier URL de su tienda. El formato del parámetro es: `?asg={group_id}`

1.  **Encuentre el ID del grupo:**
    -   Vaya a **Clientes > Grupos** en su Back Office de PrestaShop.
    -   Anote el número de ID junto al grupo al que desea asignar clientes. Por ejemplo, si "Mayorista" tiene un ID de `3`, entonces `3` es su `group_id`.
2.  **Construya el enlace:**
    -   Tome cualquier URL de su tienda (por ejemplo, `https://su-tienda.com/`)
    -   Añádale `?asg={group_id}`.
    -   **Ejemplo:** Para asignar un cliente al grupo ID `3` (por ejemplo, "Mayorista") y redirigirlo a su página de inicio: `https://su-tienda.com/?asg=3`
    -   **Ejemplo:** Para asignar un cliente al grupo ID `5` (por ejemplo, "VIP") y redirigirlo a una página de producto específica: `https://su-tienda.com/es/producto/123-producto-increible?asg=5`

:::warning
El parámetro `asg` debe ser el *primer* parámetro si no hay otros parámetros en la URL (es decir, use `?`). Si la URL ya tiene parámetros (por ejemplo, `https://su-tienda.com/categoria/1-ropa?id_category=1`), debe usar `&` para añadir el parámetro `asg`: `https://su-tienda.com/categoria/1-ropa?id_category=1&asg=3`.
:::

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuración del módulo | Cambiar grupo a predeterminado | NO | Si SÍ, el cliente también se añade al grupo 'Predeterminado'. Si NO, solo al grupo especificado. |
| Configuración del módulo | Desasignar cliente de otros grupos | NO | Si SÍ, el cliente se elimina de todos los demás grupos. Si NO, el cliente permanece en los grupos existentes y se añade al nuevo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El cliente hizo clic en el enlace pero no fue asignado al grupo. ¿Qué está mal?**
R:
1.  **Cliente no conectado:** El módulo solo funciona para clientes *conectados*. Si no estaban conectados, solo serán redirigidos a la página sin asignación de grupo.
2.  **ID de grupo incorrecto:** Verifique dos veces el `group_id` en su URL con el ID real en **Clientes > Grupos**.
3.  **Parámetro de URL incorrecto:** Asegúrese de usar `?asg=` para el primer parámetro y `&asg=` para los parámetros subsiguientes.
4.  **Módulo no habilitado:** Verifique que el módulo esté instalado y habilitado en **Módulos > Gestor de módulos**.
5.  **Caché:** Borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador.

**P: ¿Puedo asignar un cliente a varios grupos con un solo enlace?**
R: No, el parámetro `asg` solo admite la asignación a un grupo a la vez. Sin embargo, si "Desasignar cliente de otros grupos" está configurado en NO, el cliente será *añadido* al nuevo grupo mientras mantiene la membresía en sus grupos existentes.

**P: ¿Este módulo afecta al SEO?**
R: No, este módulo no tiene un impacto directo en el SEO de su tienda. El parámetro `asg` es un parámetro dinámico que los motores de búsqueda suelen ignorar.

**P: ¿Qué sucede si un cliente hace clic en el enlace varias veces?**
R: Si el cliente ya está en el grupo objetivo, no cambia nada. Si no lo está, se le asignará. El módulo está diseñado para manejar esto con elegancia sin errores.

**P: Quiero eliminar un cliente de un grupo usando un enlace. ¿Es posible?**
R: No, este módulo está diseñado solo para *asignar* clientes a grupos. No proporciona funcionalidad para eliminar clientes de grupos a través de una URL. Tendría que hacerlo manualmente en el Back Office o usar otro módulo/desarrollo personalizado.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura
El módulo "Enlace para asignar cliente a grupo" (`assigntogroup`) es un módulo ligero de PrestaShop diseñado principalmente para interceptar solicitudes del front-office y modificar las asignaciones de grupos de clientes basándose en un parámetro de URL. Aprovecha el sistema de hooks de PrestaShop (`displayHeader`) para ejecutar su lógica temprano en el proceso de carga de la página, asegurando que los cambios de grupo se apliquen antes de que se renderice el contenido de la página. No introduce controladores, modelos o JavaScript/CSS complejos personalizados. Su funcionalidad principal reside dentro de la clase principal del módulo.

### 4.2 Controladores (`controllers/`)
-   **Controladores de Front-Office**: Ninguno. La lógica del módulo se ejecuta a través de un hook, no de un controlador frontal dedicado.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)
-   No se definen clases personalizadas ni ObjectModels dentro del directorio `classes/`. El módulo interactúa directamente con los ObjectModels `Customer` y `Group` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)
-   No se incluyen archivos JavaScript con este módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)
-   No se incluyen archivos CSS con este módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   `assigntogroup/views/templates/hook/form.tpl`
        *   **Propósito**: Esta plantilla se utiliza para renderizar el formulario de configuración del módulo en el Back Office de PrestaShop. Es renderizada por el método `getContent()` de la clase principal del módulo.
        *   **Contenido**: Contiene la estructura HTML para los dos interruptores de configuración (`asg_unassign`, `asg_default`) y el botón de envío del formulario. Utiliza elementos de formulario de ayuda estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    *   El módulo no crea ninguna tabla SQL personalizada.
    *   Almacena sus ajustes de configuración en la tabla `ps_configuration`:
        *   `PS_ASG_UNASSIGN`: Almacena el valor del ajuste "Desasignar cliente de otros grupos" (0 o 1).
        *   `PS_ASG_DEFAULT`: Almacena el valor del ajuste "Cambiar grupo a predeterminado" (0 o 1).

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Se ejecuta temprano en la carga de la página del front-office, dentro de la sección `<head>`. | Este es el hook principal utilizado por el módulo. Comprueba el parámetro `asg` de la URL, verifica si un cliente ha iniciado sesión y luego realiza la lógica de asignación de grupo basándose en los ajustes de configuración del módulo (`PS_ASG_UNASSIGN`, `PS_ASG_DEFAULT`). |

### 4.8 Archivo PHP del módulo principal (`assigntogroup/assigntogroup.php`)

Este es el archivo central del módulo, que contiene su instalación, desinstalación, configuración y lógica principal.

-   **Nombre de la clase**: `Assigntogroup`
-   **Clase padre**: `Module`
-   **Métodos clave**:
    *   `__construct()`: Inicializa los metadatos del módulo (nombre, pestaña, versión, autor, etc.).
    *   `install()`:
        *   Registra el hook `displayHeader`.
        *   Establece los valores de configuración predeterminados para `PS_ASG_UNASSIGN` (0) y `PS_ASG_DEFAULT` (0) en `ps_configuration`.
        *   Devuelve `true` si tiene éxito.
    *   `uninstall()`:
        *   Anula el registro del hook `displayHeader`.
        *   Elimina los valores de configuración `PS_ASG_UNASSIGN` y `PS_ASG_DEFAULT` de `ps_configuration`.
        *   Devuelve `true` si tiene éxito.
    *   `getContent()`:
        *   Maneja el envío del formulario de configuración del Back Office del módulo.
        *   Actualiza `PS_ASG_UNASSIGN` y `PS_ASG_DEFAULT` en `ps_configuration` basándose en la entrada del usuario.
        *   Renderiza el formulario de configuración usando `display(__FILE__, 'views/templates/hook/form.tpl')`.
    *   `hookDisplayHeader()`:
        *   **Lógica principal**: Este método se ejecuta en cada carga de página del front-office.
        *   Comprueba si el parámetro GET `asg` está presente y es un entero válido que representa un `id_group`.
        *   Verifica si un cliente ha iniciado sesión (`$this->context->customer->isLogged()`).
        *   Recupera el objeto `Group` de destino.
        *   Recupera el objeto `Customer` actual.
        *   Basándose en la configuración `PS_ASG_UNASSIGN` y `PS_ASG_DEFAULT`:
            *   Gestiona las asociaciones de grupo del cliente (`$customer->updateGroup()`).
            *   Añade al cliente al grupo especificado.
            *   Opcionalmente, elimina al cliente de otros grupos.
            *   Opcionalmente, añade al cliente al grupo predeterminado.
        *   Redirige al usuario a la URL actual sin el parámetro `asg` para evitar el reprocesamiento al actualizar.

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Enlace para asignar cliente a grupo", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad del módulo.
