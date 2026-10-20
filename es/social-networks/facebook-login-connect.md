---
title: "Facebook Login Connect - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Facebook Login Connect de MyPresta.eu."
sidebar:
  label: "Facebook Login Connect - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Login Connect en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-login-connect.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-login-connect/)
>
> ---


# Facebook Login Connect

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la comunicación con la API de Facebook. Estas están casi siempre disponibles en cualquier alojamiento web moderno.

## 2. Recorrido Completo por la Configuración (Cada Grupo de Ajustes por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde configurarás cómo se comporta el botón de inicio de sesión de Facebook y dónde aparece.

#### Ajustes Generales

- **ID de Aplicación de Facebook (App ID):**
  - **Qué hace este ajuste:** Este es un identificador único proporcionado por Facebook para tu aplicación específica. Es crucial para que tu tienda se comunique con el sistema de inicio de sesión de Facebook.
  - **Efecto de cambiar este ajuste:** Sin un App ID válido, el botón de inicio de sesión de Facebook no funcionará, ya que tu tienda no puede autenticarse con Facebook.
  - **Valor recomendado:** El App ID que obtengas de tu cuenta de desarrollador de Facebook. Este campo no puede estar vacío.
  - **Escenario/ejemplo del comerciante:** Debes crear una aplicación de Facebook en [developers.facebook.com](https://developers.facebook.com/) para obtener este ID. Sigue las instrucciones de Facebook para configurar una aplicación básica y habilitar el inicio de sesión de Facebook.
- **Grupo de Clientes Predeterminado para Nuevas Cuentas:**
  - **Qué hace este ajuste:** Cuando un nuevo cliente se registra usando Facebook, se le asignará automáticamente a este grupo de clientes.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Cliente" (predeterminado):* Los nuevos usuarios de Facebook se convierten en clientes regulares, sujetos a los precios y descuentos estándar de tu tienda.
    - *Cuando se establece en un grupo personalizado (por ejemplo, "Mayorista"):* Los nuevos usuarios de Facebook podrían acceder inmediatamente a precios o contenido especiales si ese grupo tiene reglas específicas.
  - **Valor recomendado:** `Cliente` (o tu grupo de clientes predeterminado para nuevos registros).
  - **Escenario/ejemplo del comerciante:** Si tienes un grupo de clientes "VIP" con descuentos especiales, podrías considerar asignar a los nuevos usuarios de Facebook a un grupo "Cliente" estándar primero, y luego actualizarlos manualmente si cumplen los criterios VIP.
- **Enviar Correo Electrónico de Bienvenida a Nuevos Clientes:**
  - **Qué hace este ajuste:** Controla si PrestaShop envía su correo electrónico de bienvenida estándar a los clientes que se registran a través de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* Los nuevos usuarios de Facebook reciben un correo electrónico confirmando la creación de su cuenta.
    - *Cuando está deshabilitado (No):* No se envía ningún correo electrónico de bienvenida.
  - **Valor recomendado:** `Sí`. Es una buena práctica dar la bienvenida a los nuevos clientes y proporcionarles sus datos de inicio de sesión (incluso si usan Facebook, es posible que deseen establecer una contraseña más tarde).
  - **Escenario/ejemplo del comerciante:** Mantener esto habilitado asegura que los nuevos clientes se sientan bienvenidos y tengan un registro de su cuenta, incluso si no necesitan recordar una contraseña de inmediato.
- **Habilitar Inicio de Sesión en Navegador Integrado (para aplicaciones móviles):**
  - **Qué hace este ajuste:** Este ajuste es principalmente para tiendas a las que se accede a través de una aplicación móvil dedicada (no solo un navegador móvil). Optimiza el flujo de inicio de sesión de Facebook para navegadores integrados en la aplicación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Mejora la experiencia de inicio de sesión para los usuarios que acceden a tu tienda a través de una WebView dentro de una aplicación móvil.
    - *Cuando está deshabilitado:* Se utiliza el flujo de inicio de sesión estándar del navegador, lo que podría ser menos fluido en una aplicación dedicada.
  - **Valor recomendado:** `No`, a menos que tengas una aplicación móvil específica que incruste tu tienda PrestaShop.
  - **Escenario/ejemplo del comerciante:** Si has desarrollado una aplicación nativa de iOS o Android que muestra el contenido de tu tienda PrestaShop, habilitar esto podría ser necesario para una experiencia de inicio de sesión de Facebook fluida dentro de esa aplicación.
- **Mostrar Inicio de Sesión de Facebook en Ventana Emergente:**
  - **Qué hace este ajuste:** Si tu tema utiliza una ventana emergente para iniciar sesión, esta opción permite que el botón de inicio de sesión de Facebook aparezca dentro de esa ventana emergente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón de inicio de sesión de Facebook estará disponible dentro de la ventana emergente de inicio de sesión de tu tema.
    - *Cuando está deshabilitado:* El botón solo aparecerá en las páginas de inicio de sesión estándar u otras posiciones de hook.
  - **Valor recomendado:** `Sí`, si tu tema utiliza una ventana emergente de inicio de sesión.
  - **Escenario/ejemplo del comerciante:** Muchos temas modernos utilizan una ventana emergente de inicio de sesión rápido accesible desde la cabecera. Habilitar esto hace que la opción de inicio de sesión de Facebook sea inmediatamente visible allí.
- **Idioma del Botón de Inicio de Sesión de Facebook:**
  - **Qué hace este ajuste:** Te permite especificar el idioma para el botón de inicio de sesión de Facebook y los mensajes relacionados.
  - **Efecto de cambiar este ajuste:** El texto del botón y cualquier mensaje generado por Facebook aparecerán en el idioma seleccionado.
  - **Valor recomendado:** `Idioma predeterminado de PrestaShop` (para que coincida con el idioma principal de tu tienda) o `Detección automática` si está disponible.
  - **Escenario/ejemplo del comerciante:** Si tu tienda opera en varios idiomas, es posible que desees configurarlo para que coincida con el idioma actual del front-office para una experiencia de usuario consistente.
- **Permitir que Facebook identifique a los usuarios (Avanzado):**
  - **Qué hace este ajuste:** Este es un ajuste avanzado relacionado con el seguimiento de identidad de Facebook. Permite a Facebook rastrear potencialmente a los usuarios en tu sitio con fines publicitarios.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede proporcionar más datos para la publicidad de Facebook, pero podría tener implicaciones de privacidad dependiendo de las regulaciones locales (por ejemplo, GDPR).
    - *Cuando está deshabilitado:* Limita la capacidad de Facebook para rastrear usuarios en tu sitio.
  - **Valor recomendado:** `No`, a menos que tengas una estrategia de marketing específica que lo requiera y hayas abordado el cumplimiento de la privacidad.
  - **Escenario/ejemplo del comerciante:** Consulta con tu equipo de marketing y asesor legal antes de habilitar esto, especialmente si operas en regiones con leyes estrictas de privacidad de datos.

#### Opciones de Visualización (Dónde mostrar el Botón de Inicio de Sesión de Facebook)

Estos ajustes controlan en qué áreas específicas (hooks) de tu tienda PrestaShop se mostrará el botón de inicio de sesión de Facebook. Puedes habilitar o deshabilitar cada hook individualmente.

- **Mostrar en la parte superior (fbl\_displayTop):**
  - **Qué hace este ajuste:** Muestra el botón en la sección superior de tu tienda, a menudo cerca de la barra de búsqueda o el logotipo.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la cabecera.
    - *Deshabilitado:* El botón está oculto de la cabecera.
  - **Valor recomendado:** `Sí`, para una alta visibilidad.
- **Mostrar en la columna superior (fbl\_displaytopColumn):**
  - **Qué hace este ajuste:** Muestra el botón en el área de contenido principal, generalmente encima de los listados de productos principales o el contenido de la página de inicio.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en el área de contenido superior.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `No`, a menos que quieras un botón muy prominente en la página de inicio.
- **Mostrar en la página de inicio (fbl\_displayHome):**
  - **Qué hace este ajuste:** Muestra el botón específicamente en la página de inicio de tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la página de inicio.
    - *Deshabilitado:* El botón está oculto de la página de inicio.
  - **Valor recomendado:** `Sí`, para fomentar el registro inmediato.
- **Mostrar en la navegación (fbl\_displayNav):**
  - **Qué hace este ajuste:** Muestra el botón dentro de la barra de navegación principal, a menudo junto a los enlaces "Mi cuenta" o "Contáctenos".
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la navegación.
    - *Deshabilitado:* El botón está oculto de la navegación.
  - **Valor recomendado:** `Sí`, para un fácil acceso desde cualquier página.
- **Mostrar en la navegación 1 (fbl\_displayNav1):**
  - **Qué hace este ajuste:** Similar a `displayNav`, pero se dirige a un hook de navegación específico que algunos temas utilizan (a menudo para la barra superior).
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la primera área de navegación.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `Sí`, si tu tema utiliza este hook y quieres el botón allí.
- **Mostrar en la navegación 2 (fbl\_displayNav2):**
  - **Qué hace este ajuste:** Similar a `displayNav`, pero se dirige a un segundo hook de navegación que algunos temas utilizan (a menudo para la barra de navegación principal).
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la segunda área de navegación.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `Sí`, si tu tema utiliza este hook y quieres el botón allí.
- **Mostrar en el carrito de compras (fbl\_displayShoppingCart):**
  - **Qué hace este ajuste:** Muestra el botón en la página de resumen del carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la página del carrito, permitiendo un inicio de sesión rápido antes de finalizar la compra.
    - *Deshabilitado:* El botón está oculto de la página del carrito.
  - **Valor recomendado:** `Sí`, para simplificar el proceso de pago para los clientes que regresan.
- **Mostrar después del formulario de inicio de sesión del cliente (fbl\_displayCustomerLoginFormAfter):**
  - **Qué hace este ajuste:** Muestra el botón directamente debajo del formulario de inicio de sesión estándar de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece como un método de inicio de sesión alternativo en la página de inicio de sesión.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `Sí`, esta es una ubicación principal para opciones de inicio de sesión alternativas.
- **Mostrar en la parte superior de la información personal (fbl\_displayPersonalInformationTop):**
  - **Qué hace este ajuste:** Muestra el botón en la parte superior de la sección "Información personal" durante la creación o edición de la cuenta.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la página de información personal.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `Sí`, para ofrecer el inicio de sesión de Facebook como alternativa a rellenar el formulario.
- **Mostrar en el extra del carrito de compras (fbl\_displayShoppingCartExtra):**
  - **Qué hace este ajuste:** Muestra el botón en un área adicional de la página del carrito de compras, a menudo utilizada para módulos o información extra.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en el área extra del carrito.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `No`, a menos que tu tema utilice específicamente este hook para opciones de inicio de sesión.
- **Mostrar en la columna izquierda (fbl\_displayLeftColumn):**
  - **Qué hace este ajuste:** Muestra el botón en la barra lateral izquierda de tu tienda (si tu tema tiene una).
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la columna izquierda.
    - *Deshabilitado:* El botón está oculto de la columna izquierda.
  - **Valor recomendado:** `No`, a menos que quieras que se muestre prominentemente en la barra lateral.
- **Mostrar en la columna derecha (fbl\_displayRightColumn):**
  - **Qué hace este ajuste:** Muestra el botón en la barra lateral derecha de tu tienda (si tu tema tiene una).
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la columna derecha.
    - *Deshabilitado:* El botón está oculto de la columna derecha.
  - **Valor recomendado:** `No`, a menos que quieras que se muestre prominentemente en la barra lateral.
- **Mostrar en el formulario de creación de cuenta (fbl\_displayCreateAccountForm):**
  - **Qué hace este ajuste:** Muestra el botón directamente dentro del formulario estándar de creación de cuenta de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece como un método de registro alternativo en la página de creación de cuenta.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `Sí`, esta es una ubicación crucial para simplificar el registro.
- **Mostrar en la parte superior de la creación de cuenta (fbl\_displayCreateAccountTop):**
  - **Qué hace este ajuste:** Muestra el botón en la parte superior de la página de creación de cuenta, encima de los campos del formulario.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la parte superior de la página de creación de cuenta.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `Sí`, para máxima visibilidad en la página de registro.
- **Mostrar en el pie de página (fbl\_displayFooter):**
  - **Qué hace este ajuste:** Muestra el botón en la sección del pie de página de tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en el pie de página.
    - *Deshabilitado:* El botón está oculto del pie de página.
  - **Valor recomendado:** `No`, generalmente no es una ubicación principal para los botones de inicio de sesión.
- **Mostrar en la cabecera (fbl\_displayHeader):**
  - **Qué hace este ajuste:** Muestra el botón en la sección de la cabecera de tu tienda. Esta es una ubicación muy común y efectiva.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en la cabecera.
    - *Deshabilitado:* El botón está oculto de la cabecera.
  - **Valor recomendado:** `Sí`, para una alta visibilidad en todas las páginas.
- **Mostrar en la Zona Uno del Panel de Control (fbl\_displayDashboardZoneOne):**
  - **Qué hace este ajuste:** Este hook es típicamente para mostrar contenido en el panel de control de la cuenta del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en el panel de control del cliente.
    - *Deshabilitado:* El botón está oculto de esta área.
  - **Valor recomendado:** `No`, ya que los clientes ya han iniciado sesión cuando ven su panel de control.
- **Mostrar en el inicio de sesión emergente (fbl\_popuplogin):**
  - **Qué hace este ajuste:** Se dirige específicamente a temas que utilizan un modal emergente para iniciar sesión.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece dentro de la ventana emergente de inicio de sesión.
    - *Deshabilitado:* El botón está oculto de la ventana emergente de inicio de sesión.
  - **Valor recomendado:** `Sí`, si tu tema utiliza una ventana emergente de inicio de sesión.
- **Mostrar inicio de sesión de Facebook (fbl\_fblogin):**
  - **Qué hace este ajuste:** Este es un hook genérico para el botón de inicio de sesión de Facebook. Puede ser utilizado por el módulo internamente o por temas para una ubicación personalizada.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El botón aparece en este hook genérico.
    - *Deshabilitado:* El botón está oculto de este hook.
  - **Valor recomendado:** `Sí`, si otros hooks específicos no funcionan o si quieres un respaldo.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de Aplicación de Facebook (App ID) | *Tu ID de Aplicación de Facebook* | Esencial para conectarse a Facebook; el botón no funcionará sin él. |
| Configuración del Módulo | Grupo de Clientes Predeterminado para Nuevas Cuentas | Cliente | Asigna a los nuevos usuarios de Facebook a un grupo de clientes específico. |
| Configuración del Módulo | Enviar Correo Electrónico de Bienvenida a Nuevos Clientes | Sí | Determina si los nuevos registros de Facebook reciben un correo electrónico de bienvenida. |
| Configuración del Módulo | Habilitar Inicio de Sesión en Navegador Integrado | No | Optimiza el inicio de sesión para aplicaciones móviles dedicadas (no navegadores móviles). |
| Configuración del Módulo | Mostrar Inicio de Sesión de Facebook en Ventana Emergente | Sí (si el tema usa ventana emergente) | Muestra el botón en la ventana emergente de inicio de sesión del tema. |
| Configuración del Módulo | Idioma del Botón de Inicio de Sesión de Facebook | Idioma predeterminado de PrestaShop | Establece el idioma para el botón y los mensajes de Facebook. |
| Configuración del Módulo | Permitir que Facebook identifique a los usuarios | No | Opción de seguimiento avanzada; consulta legal/marketing. |
| Configuración del Módulo | Mostrar en la parte superior (fbl\_displayTop) | Sí | Muestra el botón en la cabecera. |
| Configuración del Módulo | Mostrar en la columna superior (fbl\_displaytopColumn) | No | Muestra el botón en el área de contenido principal, generalmente encima de los listados. |
| Configuración del Módulo | Mostrar en la página de inicio (fbl\_displayHome) | Sí | Muestra el botón específicamente en la página de inicio. |
| Configuración del Módulo | Mostrar en la navegación (fbl\_displayNav) | Sí | Muestra el botón en la barra de navegación principal. |
| Configuración del Módulo | Mostrar en la navegación 1 (fbl\_displayNav1) | Sí (si el tema lo usa) | Muestra el botón en un área de navegación superior específica. |
| Configuración del Módulo | Mostrar en la navegación 2 (fbl\_displayNav2) | Sí (si el tema lo usa) | Muestra el botón en un área de navegación principal específica. |
| Configuración del Módulo | Mostrar en el carrito de compras (fbl\_displayShoppingCart) | Sí | Muestra el botón en la página de resumen del carrito de compras. |
| Configuración del Módulo | Mostrar después del formulario de inicio de sesión del cliente | Sí | Muestra el botón debajo del formulario de inicio de sesión estándar. |
| Configuración del Módulo | Mostrar en la parte superior de la información personal | Sí | Muestra el botón en la parte superior de la página de información personal. |
| Configuración del Módulo | Mostrar en el extra del carrito de compras | No | Muestra el botón en un área adicional del carrito. |
| Configuración del Módulo | Mostrar en la columna izquierda (fbl\_displayLeftColumn) | No | Muestra el botón en la barra lateral izquierda. |
| Configuración del Módulo | Mostrar en la columna derecha (fbl\_displayRightColumn) | No | Muestra el botón en la barra lateral derecha. |
| Configuración del Módulo | Mostrar en el formulario de creación de cuenta | Sí | Muestra el botón dentro del formulario de creación de cuenta. |
| Configuración del Módulo | Mostrar en la parte superior de la creación de cuenta | Sí | Muestra el botón en la parte superior de la página de creación de cuenta. |
| Configuración del Módulo | Mostrar en el pie de página (fbl\_displayFooter) | No | Muestra el botón en el pie de página. |
| Configuración del Módulo | Mostrar en la cabecera (fbl\_displayHeader) | Sí | Muestra el botón en la sección de la cabecera. |
| Configuración del Módulo | Mostrar en la Zona Uno del Panel de Control | No | Muestra el botón en el panel de control de la cuenta del cliente. |
| Configuración del Módulo | Mostrar en el inicio de sesión emergente (fbl\_popuplogin) | Sí (si el tema usa ventana emergente) | Muestra el botón dentro del modal de inicio de sesión emergente. |
| Configuración del Módulo | Mostrar inicio de sesión de Facebook (fbl\_fblogin) | Sí | Hook genérico para el botón de inicio de sesión de Facebook. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: El botón de inicio de sesión de Facebook aparece, pero no sucede nada cuando hago clic en él, o muestra un error.**
R1: Esto casi siempre indica un problema con tu ID de aplicación de Facebook o la configuración de la propia aplicación de Facebook.
- **Verifica tu ID de aplicación de Facebook:** Ve a la configuración de tu módulo en PrestaShop y verifica que el "ID de aplicación de Facebook" esté ingresado correctamente.
- **Verifica la configuración de tu aplicación de Facebook:** Inicia sesión en [developers.facebook.com](https://developers.facebook.com/).
- Asegúrate de que tu aplicación esté "En vivo" (no en modo de desarrollo).
- Ve a "Inicio de sesión de Facebook" > "Configuración" y asegúrate de que "Inicio de sesión OAuth de cliente" e "Inicio de sesión OAuth web" estén habilitados.
- En "URI de redirección OAuth válidos", *debes* agregar el dominio completo de tu tienda (por ejemplo, `https://www.tutienda.com/`). A veces, también es posible que debas agregar `https://www.tutienda.com/module/fblogin/index` o `https://www.tutienda.com/module/fblogin/loginloader` dependiendo de tu versión de PrestaShop y la estructura de URL.
- Asegúrate de que tu "URL de Política de Privacidad" y "URL de Términos de Servicio" estén configuradas en la "Configuración básica" de tu aplicación de Facebook.
- **Borrar caché:** Después de realizar cualquier cambio, borra la caché de tu PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).

**P2: Los nuevos clientes se registran a través de Facebook, pero sus nombres o correos electrónicos no aparecen correctamente.**
R2: El módulo extrae información de perfil público de Facebook.
- Asegúrate de que el cliente haya otorgado permiso a tu aplicación para acceder a su perfil básico y correo electrónico.
- La API de Facebook proporciona el nombre, apellido y correo electrónico. Si faltan o son incorrectos, generalmente es un problema con la configuración de privacidad del perfil de Facebook del cliente o un raro fallo de la API.
- El módulo crea una nueva cuenta si no se encuentra un correo electrónico coincidente. Si un correo electrónico ya existe en tu base de datos de PrestaShop, el módulo debería intentar iniciar sesión al usuario en esa cuenta existente.

**P3: El botón de Facebook no aparece en la ubicación que espero, incluso después de habilitar el hook.**
R3:
- **Borrar caché:** Siempre borra la caché de tu PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) después de cambiar la configuración de los hooks.
- **Compatibilidad del tema:** Algunos temas personalizados pueden anular los hooks estándar de PrestaShop o tener estructuras únicas. Si el botón no aparece, es posible que tu tema no esté mostrando activamente ese hook específico. Es posible que debas consultar a tu desarrollador de temas o a un webmaster para integrarlo manualmente en los archivos `.tpl` de tu tema.
- **Verificar posiciones del módulo:** Ve a Diseño > Posiciones (o Módulos > Posiciones en versiones anteriores) y busca `fblogin`. Asegúrate de que el módulo esté "enganchado" a las posiciones deseadas. Si no lo está, puedes "Trasplantar un módulo" manualmente al hook correcto.

**P4: ¿Pueden los clientes que se registraron con Facebook establecer una contraseña más tarde para iniciar sesión directamente?**
R4: Sí. Una vez que se crea una cuenta a través de Facebook, es una cuenta de cliente estándar de PrestaShop.
- Los clientes pueden usar el enlace "Olvidé mi contraseña" en la página de inicio de sesión de tu tienda. Recibirán un correo electrónico para establecer una nueva contraseña, lo que les permitirá iniciar sesión directamente con su correo electrónico y la nueva contraseña, incluso sin Facebook.

**P5: ¿Este módulo admite varios idiomas para el botón?**
R5: Sí, el módulo tiene una configuración para "Idioma del botón de inicio de sesión de Facebook". Puedes configurarlo para que coincida con el idioma predeterminado de tu tienda, o en algunos casos, el SDK de Facebook podría detectar automáticamente el idioma del navegador del usuario.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo `Facebook Login Connect` integra el SDK de JavaScript de Facebook para facilitar la autenticación de usuarios. Opera principalmente mediante la conexión a varios puntos de visualización del front-office para renderizar el botón de inicio de sesión de Facebook. Tras un inicio de sesión exitoso en Facebook, un controlador frontal gestiona la devolución de llamada, recupera los datos del usuario de Facebook y, o bien inicia sesión a un cliente de PrestaShop existente, o crea uno nuevo. El módulo aprovecha la clase `Module` de PrestaShop para la configuración y la gestión de hooks, con clases personalizadas mínimas, basándose en gran medida en el archivo principal `fblogin.php` para la lógica central.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/index.php`
    - **Nombre de la Clase:** `FbloginIndexModuleFrontController`
    - **Clase Padre:** `ModuleFrontController`
    - **Responsabilidad:** Este controlador actúa como el punto de conexión de devolución de llamada principal para el proceso de autenticación de Facebook. Después de que un usuario inicia sesión con éxito a través de Facebook, Facebook redirige a este controlador. Se encarga de la recuperación del token de acceso de Facebook, obtiene los datos del perfil del usuario (nombre, correo electrónico) y luego inicia sesión a un cliente de PrestaShop existente o crea uno nuevo. Luego redirige al usuario a su página de cuenta o a la página de inicio.
  - `controllers/front/loginloader.php`
    - **Nombre de la Clase:** `FbloginLoginloaderModuleFrontController`
    - **Clase Padre:** `ModuleFrontController`
    - **Responsabilidad:** Este controlador es probablemente un respaldo o un punto de entrada alternativo para el proceso de inicio de sesión de Facebook, potencialmente utilizado para escenarios específicos o versiones anteriores de PrestaShop. Realizaría tareas similares de autenticación y gestión de usuarios que `index.php`.
- **Controladores de Administración del Back-Office**:

  - Ninguno. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Centrales (`classes/`)

- Ninguno. El módulo no define ninguna clase `ObjectModel` personalizada ni otras clases de lógica de negocio central en el directorio `classes/`. Toda la lógica central está encapsulada dentro de la clase `Fblogin` en `fblogin.php`.

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/fblogin4.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Este script es responsable de inicializar el SDK de JavaScript de Facebook. Carga el SDK, configura la configuración `FB.init` (incluyendo el ID de la aplicación y los permisos deseados), y maneja la llamada `FB.login` cuando se hace clic en el botón de inicio de sesión de Facebook. Probablemente escucha el evento `auth.statusChange` para detectar los estados de inicio de sesión/cierre de sesión y redirige al usuario al controlador frontal de PrestaShop apropiado (`index.php` o `loginloader.php`) tras una autenticación exitosa. También gestiona la visualización del botón de inicio de sesión de Facebook y su interacción.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `css.css`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Es probable que sea una hoja de estilo genérica para el módulo, que proporciona un estilo básico para el botón de inicio de sesión de Facebook y cualquier elemento de la interfaz de usuario relacionado.
- `views/css/fblogin.css`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Proporciona reglas de estilo específicas para el botón de inicio de sesión de Facebook y su contenedor, asegurando una apariencia consistente en diferentes temas. Podría incluir estilos para el tamaño del botón, color, efectos de desplazamiento y alineación.
- `views/css/fblogin17.css`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Esta hoja de estilo probablemente contiene anulaciones específicas o estilos adicionales adaptados para PrestaShop 1.7.x y versiones más recientes, abordando posibles diferencias de diseño o estilo en estructuras de temas más nuevas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - `createAccountForm.tpl`: Renderiza el botón de inicio de sesión de Facebook dentro del formulario estándar de creación de cuenta.
  - `createAccountTop.tpl`: Renderiza el botón de inicio de sesión de Facebook en la parte superior de la página de creación de cuenta.
  - `dashboardZoneOne.tpl`: Renderiza el botón de inicio de sesión de Facebook en la zona uno del panel de control del cliente (menos común para el inicio de sesión, pero disponible).
  - `displayCustomerLoginFormAfter.tpl`: Renderiza el botón de inicio de sesión de Facebook directamente después del formulario estándar de inicio de sesión del cliente.
  - `displayNav.tpl`: Renderiza el botón de inicio de sesión de Facebook en la barra de navegación principal.
  - `displayPersonalInformationTop.tpl`: Renderiza el botón de inicio de sesión de Facebook en la parte superior de la página de información personal.
  - `displayPopUpLogin.tpl`: Renderiza el botón de inicio de sesión de Facebook dentro de un modal de inicio de sesión emergente del tema.
  - `fblogin.tpl`: Una plantilla genérica para el botón de inicio de sesión de Facebook, potencialmente utilizada por `displayfblogin` o como respaldo.
  - `footer.tpl`: Renderiza el botón de inicio de sesión de Facebook en el pie de página de la tienda.
  - `header.tpl`: Renderiza el botón de inicio de sesión de Facebook en la cabecera de la tienda.
  - `home.tpl`: Renderiza el botón de inicio de sesión de Facebook en la página de inicio.
  - `leftcolumn.tpl`: Renderiza el botón de inicio de sesión de Facebook en la barra lateral izquierda.
  - `rightcolumn.tpl`: Renderiza el botón de inicio de sesión de Facebook en la barra lateral derecha.
  - `shoppingCart.tpl`: Renderiza el botón de inicio de sesión de Facebook en la página del carrito de compras.
  - `shoppingCartExtra.tpl`: Renderiza el botón de inicio de sesión de Facebook en un área adicional de la página del carrito de compras.
  - `top.tpl`: Renderiza el botón de inicio de sesión de Facebook en la sección superior de la tienda.
  - `topColumn.tpl`: Renderiza el botón de inicio de sesión de Facebook en el área de contenido principal, típicamente encima de los listados de productos.
- **Plantillas de administración (`views/templates/admin/`)**:

  - Ninguno. La configuración del módulo se renderiza directamente a través de `getContent()` en `fblogin.php` utilizando los ayudantes de formulario estándar de PrestaShop.
- **Plantillas de front-office (`views/templates/front/`)**:

  - Ninguno. Toda la visualización del front-office se maneja a través de plantillas de hook.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - La configuración se almacena en la tabla `ps_configuration` utilizando claves como `FBL_APPID`, `FBL_GROUPID`, `FBL_POPUP_LOGIN`, `FBL_DISPLAYTOP`, etc.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha. | Muestra el botón de inicio de sesión de Facebook en la columna derecha. |
| `displaypopuplogin` | Renderiza contenido dentro de un pop-up de inicio de sesión del tema. | Muestra el botón de inicio de sesión de Facebook en el pop-up de inicio de sesión. |
| `displayCreateAccountForm` | Renderiza contenido dentro del formulario de creación de cuenta del cliente. | Muestra el botón de inicio de sesión de Facebook como método de registro alternativo. |
| `displayPersonalInformationTop` | Renderiza contenido en la parte superior de la página de información personal. | Muestra el botón de inicio de sesión de Facebook para un registro/inicio de sesión rápido. |
| `displayTop` | Renderiza contenido en la sección superior de la tienda. | Muestra el botón de inicio de sesión de Facebook en la barra superior de la cabecera. |
| `displayCreateAccountTop` | Renderiza contenido en la parte superior de la página de creación de cuenta. | Muestra el botón de inicio de sesión de Facebook encima del formulario de registro. |
| `displayHeader` | Renderiza contenido en la sección `<head>` del HTML y potencialmente elementos visibles de la cabecera. | Inyecta el JavaScript del SDK de Facebook y muestra el botón de inicio de sesión en la cabecera. |
| `displayNav` | Renderiza contenido en la barra de navegación principal. | Muestra el botón de inicio de sesión de Facebook en la navegación. |
| `displayDashboardZoneOne` | Renderiza contenido en la primera zona del panel de control del cliente. | Muestra el botón de inicio de sesión de Facebook (menos común para usuarios ya conectados). |
| `displayNav2` | Renderiza contenido en una barra de navegación secundaria (dependiente del tema). | Muestra el botón de inicio de sesión de Facebook en la navegación secundaria. |
| `displayShoppingCart` | Renderiza contenido en la página de resumen del carrito de compras. | Muestra el botón de inicio de sesión de Facebook para un inicio de sesión rápido antes de finalizar la compra. |
| `displayTopColumn` | Renderiza contenido en el área de contenido principal, típicamente encima de los listados. | Muestra el botón de inicio de sesión de Facebook en la columna de contenido superior. |
| `displayFooter` | Renderiza contenido en el pie de página de la tienda. | Muestra el botón de inicio de sesión de Facebook en el pie de página. |
| `displayfblogin` | Un hook personalizado definido por el propio módulo. | Proporciona un punto flexible para que los temas integren el botón de inicio de sesión de Facebook. |
| `displayHome` | Renderiza contenido en la página de inicio de la tienda. | Muestra el botón de inicio de sesión de Facebook en la página de inicio. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda. | Muestra el botón de inicio de sesión de Facebook en la columna izquierda. |
| `displayCustomerLoginFormAfter` | Renderiza contenido directamente después del formulario de inicio de sesión estándar del cliente. | Muestra el botón de inicio de sesión de Facebook como método de inicio de sesión alternativo. |
| `displayShoppingCartExtra` | Renderiza contenido en un área adicional de la página del carrito de compras. | Muestra el botón de inicio de sesión de Facebook en un área adicional del carrito. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con el módulo "Facebook Login Connect".
