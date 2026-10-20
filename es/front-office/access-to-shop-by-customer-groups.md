---
title: "Acceso a la tienda por grupos de clientes - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Acceso a la tienda por grupos de clientes' de MyPresta.eu."
sidebar:
  label: "Acceso a la tienda por grupos de clientes - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Access to shop by customer groups en MyPresta.eu](https://mypresta.eu/modules/front-office-features/access-to-shop-by-customer-groups.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/access-to-shop-by-customer-groups/)
>
> ---


# Acceso a la tienda por grupos de clientes

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes.

#### **Grupos de clientes sin acceso a la tienda**

Este es el ajuste más crucial. Determina qué grupos de clientes serán bloqueados para ver su tienda.

-   **Qué hace este ajuste:** Esta sección muestra una lista de todos los grupos de clientes definidos en su tienda PrestaShop. Puede seleccionar uno o más grupos de esta lista.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando se selecciona uno o más grupos:* Cualquier cliente que pertenezca a *cualquiera* de los grupos seleccionados será bloqueado para acceder al front office de la tienda. En su lugar, verán el contenido personalizado que defina a continuación.
    *   *Cuando no se selecciona ningún grupo:* El módulo no bloqueará a ningún cliente basándose en su afiliación a un grupo. Todos los clientes tendrán acceso a la tienda (a menos que habilite la opción "Bloquear acceso para clientes no registrados").
-   **Valor recomendado:** Seleccione los grupos específicos que desea restringir. Por ejemplo, si tiene un grupo "Mayorista Pendiente de Aprobación", podría seleccionarlo aquí.
-   **Escenario / ejemplo de comerciante:** Ha creado un nuevo grupo de clientes llamado "Nuevos Registros - Pendiente de Revisión". Selecciona este grupo aquí. Ahora, cualquier nuevo cliente que se registre será colocado automáticamente en este grupo y no podrá navegar por su tienda hasta que lo mueva manualmente a un grupo de "Clientes Aprobados".

#### **Bloquear acceso para clientes no registrados**

Este ajuste controla el acceso para los visitantes que no han iniciado sesión en su tienda.

-   **Qué hace este ajuste:** Es un simple interruptor ON/OFF.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando está habilitado (SÍ):* Todos los visitantes que no hayan iniciado sesión en una cuenta de cliente serán bloqueados para acceder a la tienda. Verán la página de contenido personalizado. Una vez que inicien sesión (y si pertenecen a un grupo permitido), obtendrán acceso.
    *   *Cuando está deshabilitado (NO):* Los visitantes no registrados tendrán acceso a la tienda, a menos que estén explícitamente bloqueados por pertenecer a "Grupos de clientes sin acceso a la tienda".
-   **Valor recomendado:**
    *   **SÍ:** Si desea que toda su tienda sea privada, requiriendo que todos los visitantes inicien sesión primero (por ejemplo, una tienda B2B, un club solo para miembros).
    *   **NO:** Si desea que su tienda sea visible públicamente, pero solo restringir grupos de clientes específicos.
-   **Escenario / ejemplo de comerciante:** Dirige una tienda solo para mayoristas. Habilita este ajuste. Ahora, cualquier persona que visite su sitio debe iniciar sesión primero para ver sus productos y precios.

#### **Mostrar formulario de inicio de sesión en la página bloqueada**

Este ajuste determina si aparece un formulario de inicio de sesión en la página que se muestra a los clientes bloqueados.

-   **Qué hace este ajuste:** Es un simple interruptor ON/OFF.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando está habilitado (SÍ):* Se mostrará un formulario de inicio de sesión estándar de PrestaShop en la página de contenido personalizado, permitiendo a los clientes bloqueados intentar iniciar sesión.
    *   *Cuando está deshabilitado (NO):* No se mostrará ningún formulario de inicio de sesión. Los clientes solo verán su mensaje personalizado.
-   **Valor recomendado:**
    *   **SÍ:** Si espera que los clientes bloqueados sean clientes existentes que simplemente necesitan iniciar sesión para obtener acceso. Esto mejora la experiencia del usuario.
    *   **NO:** Si desea obligar a los clientes a registrarse primero, o si la restricción de acceso es permanente para ciertos grupos.
-   **Escenario / ejemplo de comerciante:** Ha bloqueado el acceso a usuarios no registrados. Al habilitar esto, los clientes pueden iniciar sesión fácilmente directamente desde la página restringida sin tener que navegar a una página de inicio de sesión separada.

#### **Permitir registro en la página bloqueada**

Este ajuste determina si aparece un enlace de registro en la página que se muestra a los clientes bloqueados.

-   **Qué hace este ajuste:** Es un simple interruptor ON/OFF.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando está habilitado (SÍ):* Se mostrará un enlace a la página de registro de clientes en la página de contenido personalizado.
    *   *Cuando está deshabilitado (NO):* No se mostrará ningún enlace de registro.
-   **Valor recomendado:**
    *   **SÍ:** Si desea permitir que los nuevos clientes se registren desde la página restringida.
    *   **NO:** Si desea controlar el registro por separado, o si su tienda es estrictamente para clientes preaprobados.
-   **Escenario / ejemplo de comerciante:** Dirige una tienda B2B que requiere registro. Habilita este ajuste para que los posibles nuevos clientes puedan registrarse fácilmente para una cuenta directamente desde la página de acceso restringido.

#### **Contenidos personalizados a mostrar**

Aquí es donde define el mensaje y el contenido que se muestra a los clientes bloqueados.

-   **Qué hace este ajuste:** Es un editor de texto enriquecido (WYSIWYG) donde puede introducir texto, imágenes, HTML e incluso vídeos. Admite contenido multilingüe, por lo que puede proporcionar diferentes mensajes para los diferentes idiomas instalados en su tienda.
-   **Efecto de cambiar este ajuste:** El contenido que introduzca aquí se mostrará a cualquier cliente que tenga bloqueado el acceso a su tienda.
-   **Valor recomendado:** Proporcione un mensaje claro, educado e informativo.
-   **Escenario / ejemplo de comerciante:**
    *   *Para una tienda B2B:* "¡Bienvenido a nuestro Portal Mayorista! Por favor, inicie sesión con sus credenciales o regístrese para una nueva cuenta para ver nuestro catálogo de productos."
    *   *Para una restricción temporal:* "Nuestra tienda está actualmente en mantenimiento. ¡Volveremos a estar en línea pronto! Gracias por su paciencia."
    *   *Para acceso exclusivo:* "Esta sección de nuestra tienda está reservada para miembros VIP. Por favor, inicie sesión o póngase en contacto con el soporte para obtener acceso."

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Grupos de clientes sin acceso a la tienda** | Ninguno seleccionado | Seleccione los grupos a los que se les bloqueará la visualización de la tienda. Los clientes de estos grupos ven contenido personalizado. |
| Configuración del módulo | **Bloquear acceso para clientes no registrados** | NO | SÍ: Todos los visitantes no registrados son bloqueados. NO: Los visitantes no registrados tienen acceso (a menos que estén en un grupo bloqueado). |
| Configuración del módulo | **Mostrar formulario de inicio de sesión en la página bloqueada** | SÍ | SÍ: Muestra un formulario de inicio de sesión en la página restringida. NO: No se muestra ningún formulario de inicio de sesión. |
| Configuración del módulo | **Permitir registro en la página bloqueada** | SÍ | SÍ: Muestra un enlace de registro en la página restringida. NO: No se muestra ningún enlace de registro. |
| Configuración del módulo | **Contenidos personalizados a mostrar** | Vacío | Define el mensaje/contenido HTML que se muestra a los clientes bloqueados. Admite varios idiomas. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: ¡Mi tienda está completamente bloqueada, incluso para mí! ¿Qué hago?**
R1: Esto suele ocurrir si ha habilitado "Bloquear acceso para clientes no registrados" y no ha iniciado sesión, o si su cuenta de administrador está de alguna manera asociada a un grupo de clientes bloqueado.
\* **Solución 1 (Recomendada):** Inicie sesión en su Back Office de PrestaShop. El módulo solo bloquea el front office. Una vez que haya iniciado sesión en el BO, navegue a Módulos > Gestor de módulos, busque "Acceso a la tienda por grupos de clientes" y haga clic en "Configurar". Ajuste la configuración para permitir su acceso.
\* **Solución 2 (Si no puede acceder al BO):** Si está completamente bloqueado, es posible que deba deshabilitar temporalmente el módulo a través de FTP. Vaya a `modules/asg/` y cambie el nombre del archivo `asg.php` (por ejemplo, `asg.php.bak`). Esto deshabilitará el módulo. Luego, puede iniciar sesión en su BO y volver a habilitarlo/reconfigurarlo. Recuerde volver a cambiar el nombre del archivo a `asg.php` después.

**P2: El contenido personalizado se ve simple o no coincide con mi tema.**
R2: El área de contenido personalizado utiliza una plantilla básica.
\* **Solución:** Puede usar el editor de texto enriquecido para agregar HTML, CSS en línea o imágenes para dar estilo a su mensaje. Para un estilo más avanzado, un webmaster puede modificar el archivo `custom.css` o la plantilla `custom-contents.tpl` (consulte la sección de desarrolladores). Asegúrese de que su contenido personalizado esté bien formateado y sea responsivo.

**P3: ¿Por qué no aparece el formulario de inicio de sesión/registro?**
R3: Verifique la configuración del módulo:
\* Asegúrese de que "Mostrar formulario de inicio de sesión en la página bloqueada" esté configurado en SÍ.
\* Asegúrese de que "Permitir registro en la página bloqueada" esté configurado en SÍ.
\* Además, asegúrese de que el registro de clientes esté generalmente habilitado en la configuración de su PrestaShop (Clientes > Ajustes > Habilitar creación de cuenta).

**P4: He realizado cambios, pero no aparecen en el front office.**
R4: PrestaShop utiliza el almacenamiento en caché, lo que a veces puede retrasar la visualización de los cambios.
\* **Solución:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop. Haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto debería actualizar su front office.

**P5: ¿Cómo gestiono qué clientes están en qué grupos?**
R5: Gestiona los grupos de clientes a través de la interfaz estándar de PrestaShop:
\* Vaya a **Clientes > Clientes** para editar cuentas de clientes individuales y asignarlas a grupos.
\* Vaya a **Clientes > Grupos** para crear nuevos grupos o editar los existentes.
\* Recuerde que un cliente puede pertenecer a varios grupos. Si un cliente pertenece a *cualquier* grupo que haya marcado como "sin acceso", será bloqueado.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Acceso a la tienda por grupos de clientes" (`asg`) opera principalmente enganchándose al evento `displayHeader`. Esto le permite ejecutar su lógica muy temprano en el proceso de carga de la página, antes de que se renderice cualquier contenido. Si se determina que un cliente está restringido, el módulo toma el control, evita una mayor renderización de la página estándar de PrestaShop y, en su lugar, muestra su página de acceso personalizada. Aprovecha el sistema de configuración de PrestaShop para los ajustes y Smarty para las plantillas.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office. Toda la lógica está encapsulada dentro del archivo principal del módulo (`asg.php`) y se ejecuta a través de hooks o el método `getContent()` para la configuración.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o entidades `ObjectModel`. Interactúa directamente con las clases principales de PrestaShop `Customer`, `Group` y `Configuration`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`asg/views/css/custom.css`**
    *   **Alcance:** Estilo del front-office para el cliente en la página de acceso restringido.
    *   **Componentes principales de la interfaz de usuario y contenedores a los que da estilo:** Este archivo proporciona un estilo básico para el contenedor de contenido personalizado, el formulario de inicio de sesión y el enlace de registro en la página de acceso restringido. Asegura que el contenido mostrado esté centrado y sea legible.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:**
        *   `.asg_wrapper`: El contenedor principal para todo el contenido restringido.
        *   `.asg_content`: El div que contiene el mensaje HTML personalizado.
        *   `.asg_login_form`: El contenedor para el formulario de inicio de sesión.
        *   `.asg_registration_link`: El contenedor para el enlace de registro.
        *   Elementos de formulario estándar de PrestaShop dentro del formulario de inicio de sesión.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna definida explícitamente como plantillas de hook. El módulo renderiza directamente las plantillas basándose en su lógica interna.
-   **Plantillas de administración (`views/templates/admin/`)**:
    *   **`asg/views/admin.tpl`**: Esta plantilla es renderizada por el método `getContent()` en `asg.php`. Contiene la estructura HTML para el formulario de configuración del módulo en el Back Office de PrestaShop. Incluye la selección de grupos de clientes, los interruptores para el inicio de sesión/registro y el editor de texto enriquecido para el contenido personalizado.
-   **Plantillas de front-office (`views/templates/front/`)**:
    *   **`asg/views/custom-contents.tpl`**: Esta es la plantilla principal que se renderiza cuando un cliente es bloqueado. Muestra el contenido personalizado definido en la configuración del módulo. Incluye condicionalmente `login-form.tpl` y `registration-link.tpl` según la configuración del módulo.
    *   **`asg/views/login-form.tpl`**: Esta plantilla contiene el HTML para el formulario de inicio de sesión de cliente estándar de PrestaShop. Se incluye dentro de `custom-contents.tpl` si la opción "Mostrar formulario de inicio de sesión" está habilitada.
    *   **`asg/views/registration-link.tpl`**: Esta plantilla contiene el HTML para el enlace a la página de registro de clientes. Se incluye dentro de `custom-contents.tpl` si la opción "Permitir registro" está habilitada.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    *   Este módulo no crea ninguna tabla SQL personalizada.
    *   Almacena sus ajustes de configuración en la tabla `ps_configuration` (o `_configuration` dependiendo del prefijo) utilizando claves como:
        *   `ASG_ALLOWREGAUTH`: Booleano para permitir el registro.
        *   `ASG_SHOWLOGINFORM`: Booleano para mostrar el formulario de inicio de sesión.
        *   `ASG_CCONTENTS`: Campo multilingüe para contenido personalizado (HTML).
        *   `ASG_WHATTOSHOW`: Array serializado de IDs de grupos de clientes que están bloqueados.
        *   `ASG_BLOCK_NOT_LOGGED`: Booleano para bloquear a los usuarios no registrados.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta muy temprano en la carga de la página del front-office, dentro de la sección `<head>`. | Este es el hook principal utilizado por el módulo. Comprueba el estado de inicio de sesión del cliente y la afiliación al grupo. Si un cliente está restringido, termina inmediatamente el proceso de renderización estándar de PrestaShop y genera la página de acceso personalizada (`custom-contents.tpl`). |
| `actionCustomerGroupsUpdate` | Se ejecuta cuando se actualizan los grupos de clientes. | Se utiliza para borrar la caché interna del módulo relacionada con los grupos de clientes, asegurando que los cambios en las asignaciones de grupos se reflejen inmediatamente. |
| `actionObjectCustomerAddAfter` | Se ejecuta después de que se añade un nuevo cliente. | Se utiliza para borrar la caché interna del módulo relacionada con los grupos de clientes, asegurando que los nuevos clientes se evalúen correctamente para el acceso. |
| `actionObjectCustomerUpdateAfter` | Se ejecuta después de que se actualiza un cliente existente. | Se utiliza para borrar la caché interna del módulo relacionada con los grupos de clientes, asegurando que los cambios en las asignaciones de grupos de clientes se reflejen inmediatamente. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte dedicado para desarrolladores del módulo "Acceso a la tienda por grupos de clientes", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se compromete a proporcionar asistencia oportuna y garantizar la compatibilidad del módulo con las últimas versiones de PrestaShop.
