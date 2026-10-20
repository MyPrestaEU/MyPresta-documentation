---
title: "Vale para un amigo - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Vale para un amigo' de MyPresta.eu."
sidebar:
  label: "Vale para un amigo - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Voucher for friend en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-friend.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/voucher-for-friend/)
>
> ---


# Vale para un amigo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una tienda PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Vale para un amigo)

Esta es la pantalla de configuración principal para el módulo "Vale para un amigo". Aquí definirá cómo se comporta la función de compartir vales y dónde aparece en su tienda.

#### **Ajustes y opciones**

- **Mostrar enlace "Vale para un amigo" en el bloque de mi cuenta (fvc\_b\_position)**

  - **Qué hace este ajuste:** Controla si un enlace a la página "Vale para un amigo" aparece en el bloque "Mi cuenta" del cliente, que normalmente se encuentra en el encabezado o en una columna después de que un cliente inicia sesión.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* Un enlace, generalmente etiquetado como "Mis vales" o "Vale para un amigo", será visible en el bloque de cuenta del cliente, proporcionando acceso rápido a la función de compartir.
    - *Cuando está deshabilitado (No):* El enlace no aparecerá en el bloque de cuenta del cliente. Los clientes tendrían que navegar a su página completa de "Mi cuenta" para encontrar el enlace, o usar otra opción de ubicación.
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo de comerciante:** Si desea que sea muy fácil para los clientes que han iniciado sesión encontrar la función, habilítela. Es una ubicación destacada para los usuarios activos.
- **Mostrar enlace "Vale para un amigo" en la página de mi cuenta (fvc\_b\_position2)**

  - **Qué hace este ajuste:** Determina si se muestra un enlace a la página "Vale para un amigo" en la página principal "Mi cuenta", que enumera todas las opciones específicas del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* Aparecerá un enlace dedicado en la página "Mi cuenta", generalmente como un icono o un enlace de texto junto con otras opciones como "Historial de pedidos" o "Mis direcciones".
    - *Cuando está deshabilitado (No):* El enlace no estará presente en la página "Mi cuenta".
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo de comerciante:** Este es un lugar estándar y esperado para que los clientes encuentren una función de este tipo. Habilitarlo garantiza la visibilidad para todos los usuarios que han iniciado sesión.
- **Mostrar enlace "Vale para un amigo" en la columna izquierda/derecha (fvc\_b\_position3)**

  - **Qué hace este ajuste:** Controla si un bloque promocional o un enlace para "Vale para un amigo" aparece en las columnas izquierda o derecha de su tienda. Esto puede ser visible tanto para visitantes que han iniciado sesión como para los que no.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* Se renderizará un bloque o enlace en la columna especificada, animando a los visitantes a usar o aprender sobre la función de compartir vales.
    - *Cuando está deshabilitado (No):* No aparecerá ningún bloque de este tipo en las columnas.
  - **Valor recomendado:** SÍ (si desea promocionar la función ampliamente)
  - **Escenario/ejemplo de comerciante:** Si desea promocionar activamente el programa de referidos a todos los visitantes, incluidos aquellos que aún no han iniciado sesión, habilitar esto aumentará la visibilidad. Podría colocarlo en la columna derecha en las páginas de productos para fomentar el intercambio.
- **Número de vales a generar (FV\_NBC)**

  - **Qué hace este ajuste:** Define cuántos códigos de vale únicos puede generar un solo cliente y enviar a sus amigos.
  - **Efecto de cambiar este ajuste:**
    - *Establecido en 1:* Cada cliente solo puede enviar un vale a un amigo.
    - *Establecido en 5:* Cada cliente puede enviar hasta cinco vales a cinco amigos diferentes.
    - *Establecido en 0 (o un número muy alto):* Permite la generación ilimitada de vales por cliente.
  - **Valor recomendado:** 3-5 (para fomentar el intercambio sin abrumar el sistema o crear demasiados descuentos)
  - **Escenario/ejemplo de comerciante:** Si desea limitar el número de referencias que un solo cliente puede hacer para evitar abusos o gestionar su presupuesto de descuentos, establezca un número específico como 3. Si desea la máxima difusión viral, establezca un número más alto o 0 para ilimitado.
- **Permitir a usuarios no registrados enviar vales (FV\_UNLOGGED)**

  - **Qué hace este ajuste:** Determina si los visitantes que no han iniciado sesión en una cuenta de cliente aún pueden acceder al formulario "Vale para un amigo" y enviar un vale.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* Los usuarios no registrados verán los enlaces "Vale para un amigo" (si están habilitados en columnas/pie de página) y podrán proceder a rellenar el formulario. Probablemente se les pedirá que introduzcan su propia dirección de correo electrónico como remitente.
    - *Cuando está deshabilitado (No):* Solo los clientes que han iniciado sesión pueden acceder y utilizar la función de compartir vales. Los usuarios no registrados que hagan clic en el enlace podrían ser redirigidos a la página de inicio de sesión/registro.
  - **Valor recomendado:** NO (para asegurar que solo los clientes reales estén refiriendo, y para prevenir spam/abuso)
  - **Escenario/ejemplo de comerciante:** Si desea controlar estrictamente quién puede referir y asegurarse de que solo su base de clientes existente participe, deshabilite esto. Si desea permitir que cualquiera refiera, incluso si aún no ha comprado, habilítelo (pero tenga en cuenta el posible spam).
- **Correo electrónico de la tienda (PS\_SHOP\_EMAIL)**

  - **Qué hace este ajuste:** Este campo normalmente muestra la dirección de correo electrónico de contacto predeterminada de su tienda, que se utiliza como correo electrónico del "remitente" para la notificación del vale enviada a los amigos. Generalmente se extrae de la configuración general de PrestaShop.
  - **Efecto de cambiar este ajuste:** Cambiar esto aquí podría anular el correo electrónico de la tienda a nivel de sistema para los correos electrónicos específicos de este módulo.
  - **Valor recomendado:** Asegúrese de que sea una dirección de correo electrónico válida y profesional asociada a su tienda (por ejemplo, `info@sutienda.com`).
  - **Escenario/ejemplo de comerciante:** El amigo que reciba el vale verá este correo electrónico como remitente. Debe ser una dirección que puedan reconocer y en la que confíen.
- **Nombre de la tienda (PS\_SHOP\_NAME)**

  - **Qué hace este ajuste:** Este campo normalmente muestra el nombre oficial de su tienda, que se utiliza en el asunto y el cuerpo del correo electrónico al enviar el vale a un amigo. Generalmente se extrae de la configuración general de PrestaShop.
  - **Efecto de cambiar este ajuste:** Cambiar esto aquí podría anular el nombre de la tienda a nivel de sistema para los correos electrónicos específicos de este módulo.
  - **Valor recomendado:** El nombre oficial de su tienda (por ejemplo, "Mi Tienda Impresionante").
  - **Escenario/ejemplo de comerciante:** El amigo que reciba el vale verá este nombre. Debe ser claro y coherente con su marca.

#### 2.1.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar enlace "Vale para un amigo" en el bloque de mi cuenta (fvc\_b\_position) | SÍ | Muestra un enlace en el bloque de cuenta del cliente (encabezado/columna) para un acceso rápido. |
| Configuración del módulo | Mostrar enlace "Vale para un amigo" en la página de mi cuenta (fvc\_b\_position2) | SÍ | Muestra un enlace en la página principal "Mi cuenta". |
| Configuración del módulo | Mostrar enlace "Vale para un amigo" en la columna izquierda/derecha (fvc\_b\_position3) | SÍ | Muestra un bloque/enlace promocional en las columnas laterales para todos los visitantes. |
| Configuración del módulo | Número de vales a generar (FV\_NBC) | 3-5 | Limita cuántos vales puede enviar un solo cliente. |
| Configuración del módulo | Permitir a usuarios no registrados enviar vales (FV\_UNLOGGED) | NO | Restringe el envío de vales solo a clientes que han iniciado sesión. |
| Configuración del módulo | Correo electrónico de la tienda (PS\_SHOP\_EMAIL) | Correo electrónico de su tienda | Correo electrónico del remitente para las notificaciones de vales. |
| Configuración del módulo | Nombre de la tienda (PS\_SHOP\_NAME) | Nombre de su tienda | Nombre de la tienda utilizado en los correos electrónicos de notificación de vales. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no pueden encontrar el enlace "Vale para un amigo".**
R1: Vaya a **Módulos > Gestor de módulos > Configurar** para "Vale para un amigo". Asegúrese de que `fvc_b_position`, `fvc_b_position2` y `fvc_b_position3` estén configurados en "Sí" para las ubicaciones deseadas (bloque Mi cuenta, página Mi cuenta, columna izquierda/derecha). Además, verifique las asignaciones de hooks de su tema en **Diseño > Posiciones** para asegurarse de que el módulo esté enganchado a `displayMyAccountBlock`, `displayCustomerAccount`, `displayLeftColumn` o `displayRightColumn` según lo esperado.

**P2: Los amigos no reciben los correos electrónicos del vale.**
R2:
1. **Verificar carpetas de spam:** Aconseje a sus clientes que pidan a sus amigos que revisen sus carpetas de spam o correo no deseado.
2. **Configuración del correo electrónico de la tienda:** Verifique que la configuración `PS_SHOP_EMAIL` en la configuración del módulo sea una dirección de correo electrónico válida y activa.
3. **Configuración de correo electrónico de PrestaShop:** Vaya a **Parámetros avanzados > Correo electrónico** en el back office de su PrestaShop. Envíe un correo electrónico de prueba para asegurarse de que el sistema de correo electrónico de su tienda funciona correctamente. Si no, podría tener un problema con la configuración de su servidor SMTP.
4. **Registros del servidor:** Su webmaster puede verificar los registros de correo del servidor en busca de errores relacionados con los correos electrónicos salientes.

**P3: El código del vale no funciona para el amigo.**
R3:
1. **Verificar caducidad/condiciones:** Asegúrese de que el vale no haya caducado y de que el carrito del amigo cumpla con los requisitos mínimos de compra o las restricciones de productos que puedan haberse establecido para el vale generado (estos se definen generalmente en la sección nativa de "Reglas de carrito" de PrestaShop, que este módulo aprovecha).
2. **Entrada correcta del código:** Confirme que el amigo está introduciendo el código exactamente como aparece (distingue mayúsculas y minúsculas, sin espacios adicionales).
3. **Uso único:** La mayoría de los vales de referencia son de un solo uso. Si el amigo intentó usarlo anteriormente, es posible que ya no sea válido.

**P4: El módulo no se ve bien en mi tema personalizado.**
R4: Los temas personalizados a menudo tienen estilos únicos que a veces pueden entrar en conflicto con los diseños de los módulos.
1. **Borrar caché:** Primero, intente borrar la caché de su PrestaShop en **Parámetros avanzados > Rendimiento**.
2. **Sobreescrituras de tema:** Es posible que su webmaster necesite crear sobreescrituras CSS en la hoja de estilos de su tema para ajustar la apariencia del módulo. El módulo utiliza `views/css/ps16.css` para su estilo, lo que puede ser un punto de partida para los ajustes.
3. **Visualización móvil:** Asegúrese de que su tema sea totalmente adaptable. Si persisten los problemas en dispositivos móviles, es probable que sea un conflicto de CSS que requiera la intervención de un desarrollador.

**P5: ¿Puedo cambiar la cantidad o el tipo de descuento del vale?**
R5: El módulo en sí genera una regla de carrito estándar de PrestaShop. Normalmente, configuraría los detalles del vale generado (por ejemplo, porcentaje de descuento, cantidad fija, compra mínima, productos específicos) dentro de la sección nativa de PrestaShop **Catálogo > Descuentos > Reglas de carrito**. El módulo crea el *mecanismo* para compartir, pero los *detalles* del descuento se gestionan mediante el sistema de descuentos central de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Vale para un amigo", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Descripción general de la arquitectura

El módulo "Vale para un amigo" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente `ModuleFrontController` para las interacciones de front-office y la clase principal del módulo para la configuración y la gestión de hooks. Se integra con el sistema nativo `CartRule` de PrestaShop para generar y gestionar vales de descuento. La lógica del módulo está contenida en su archivo PHP principal y en los controladores frontales dedicados, con plantillas Smarty que manejan la presentación.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan la lógica orientada al cliente para generar y gestionar vales.

- **`controllers/front/index.php`**

  - **Nombre de la clase:** `FriendvoucherIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador es probablemente responsable de mostrar el formulario inicial de "Vale para un amigo" donde un cliente introduce los datos de su amigo. Maneja el envío de este formulario, valida la entrada, genera la `CartRule` (vale) y envía la notificación por correo electrónico al amigo. También gestiona la lógica para limitar el número de vales que un cliente puede enviar.
  - **Rutas:** Responde a una URL como `sutienda.com/module/friendvoucher/index`.
- **`controllers/front/myvoucher.php`**

  - **Nombre de la clase:** `FriendvoucherMyvoucherModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador es responsable de mostrar la página personal "Mis vales" del cliente, a la que se accede normalmente desde la sección "Mi cuenta". Enumera los vales que el cliente ya ha enviado y, potencialmente, proporciona opciones para ver su estado o enviar nuevos.
  - **Rutas:** Responde a una URL como `sutienda.com/module/friendvoucher/myvoucher`.

#### Controladores de administración de Back-Office

Este módulo no parece tener controladores de administración personalizados dedicados. Toda la configuración del back-office se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Según el inventario proporcionado, este módulo no define clases personalizadas ni `ObjectModel`s en un directorio `classes/`. Es probable que utilice la clase `CartRule` principal de PrestaShop para la gestión de vales y `Customer` para los datos de usuario.

### 4.4 Activos de JavaScript (`views/js/`)

- **`lib/voucherengine/script.js`**
  - **Alcance:** Front-office.
  - **Detalles:** Este script probablemente maneja las interacciones del lado del cliente en el formulario "Vale para un amigo". Esto podría incluir:
    - Validación de formularios (por ejemplo, verificación de formatos de correo electrónico válidos, campos obligatorios).
    - Envíos AJAX de la solicitud de vale al controlador frontal `index.php`.
    - Visualización de mensajes de éxito o error al usuario sin una recarga completa de la página.
    - Posibles actualizaciones dinámicas del formulario basadas en la entrada del usuario.
    - Cualquier elemento interactivo relacionado con el proceso de generación de vales.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`lib/voucherengine/ps16.css`**
  - **Alcance:** Estilo del cliente de Front-office.
  - **Detalles:** Esta hoja de estilos proporciona el estilo visual para los formularios, enlaces y bloques de visualización de "Vale para un amigo" en el front office. Probablemente contiene estilos para:
    - Los elementos del formulario para compartir vales (campos de entrada, botones).
    - La lista "Mis vales" en la página de la cuenta del cliente.
    - Los bloques promocionales en las columnas izquierda/derecha.
    - Diseño básico y tipografía para garantizar la legibilidad.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores deben inspeccionar el HTML renderizado para identificar nombres de clase específicos (por ejemplo, `.friendvoucher-form`, `.voucher-list`, `.friendvoucher-block`) para apuntar a la integración y personalización del tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

El módulo no enumera explícitamente plantillas en un subdirectorio `hook/`, pero las plantillas que se enumeran a continuación suelen renderizarse a través de hooks.

- **`views/templates/front/footer.tpl`**

  - **Hook:** `displayFooter`
  - **Salidas:** Un enlace o bloque relacionado con "Vale para un amigo" en el pie de página de la tienda.
- **`views/templates/front/leftcolumn.tpl`**

  - **Hook:** `displayLeftColumn`
  - **Salidas:** Un bloque promocional o enlace para "Vale para un amigo" en la barra lateral izquierda de la tienda.
- **`views/templates/front/rightcolumn.tpl`**

  - **Hook:** `displayRightColumn`
  - **Salidas:** Un bloque promocional o enlace para "Vale para un amigo" en la barra lateral derecha de la tienda.

#### Plantillas de administración (`views/templates/admin/`)

Este módulo no parece tener plantillas de administración personalizadas. La configuración probablemente se renderiza directamente mediante el método `getContent()` utilizando los formularios de ayuda de PrestaShop.

#### Plantillas de Front-office (`views/templates/front/`)

Estas plantillas son renderizadas por los controladores frontales del módulo.

- **`views/templates/front/my-account.tpl`**

  - **Hook:** `displayCustomerAccount` (o `displayMyAccountBlock`)
  - **Salidas:** Un enlace o icono en la página principal "Mi cuenta" del cliente, dirigiéndolos al controlador `myvoucher.php`.
- **`views/templates/front/my-voucher.tpl`**

  - **Controlador:** `FriendvoucherMyvoucherModuleFrontController`
  - **Salidas:** La página dedicada que muestra una lista de vales que el cliente ha enviado, su estado y, potencialmente, un formulario para enviar nuevos.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

Este módulo no parece crear tablas SQL personalizadas. Es probable que almacene su configuración en `ps_configuration` y aproveche las tablas principales `ps_cart_rule` y `ps_cart_rule_lang` de PrestaShop para los vales generados.

#### Tabla de Hooks registrados

El módulo se registra en varios hooks para mostrar su contenido y funcionalidad.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displaymyAccountBlock` | Se renderiza en el bloque de cuenta del cliente (encabezado/columna) después de iniciar sesión. | Muestra un enlace rápido a la página de vales para usuarios que han iniciado sesión. |
| `displayrightColumn` | Renderiza contenido en la barra lateral derecha. | Muestra un bloque/enlace promocional para la función de vales. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda. | Muestra un bloque/enlace promocional para la función de vales. |
| `displayFooter` | Renderiza contenido en el pie de página de la tienda. | Muestra un enlace a la página de vales en el pie de página. |
| `displaycustomerAccount` | Renderiza contenido en la página principal "Mi cuenta" del cliente. | Muestra un enlace/icono dedicado para la función de vales en la página de la cuenta. |
| `actionValidateOrder` | Se ejecuta después de que un pedido se valida correctamente. | (Potencial) Podría usarse para activar acciones relacionadas con recompensas de referidos o seguimiento de referidos exitosos, aunque no confirmado explícitamente por el inventario de archivos. |

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier otra asistencia, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puede acceder a sus módulos comprados, descargar las últimas versiones y enviar tickets de soporte directamente desde su cuenta.
