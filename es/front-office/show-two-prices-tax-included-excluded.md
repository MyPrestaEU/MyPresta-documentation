---
title: "Mostrar dos precios - impuestos incluidos / excluidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Mostrar dos precios - impuestos incluidos / excluidos' de MyPresta.eu."
sidebar:
  label: "Mostrar dos precios - impuestos incluidos / excluidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Show two prices - tax included / excluded en MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-two-prices-tax-included-excluded.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/show-two-prices-tax-included-excluded/)
>
> ---


# Mostrar dos precios - impuestos incluidos / excluidos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son necesarias para PrestaShop en sí y, en general, para las operaciones del módulo. No hay requisitos de alojamiento especiales más allá de un entorno estándar compatible con PrestaShop.

## 2. Recorrido completo de la configuración (Cada grupo de ajustes por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Mostrar dos precios - impuestos incluidos / excluidos". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto al nombre del módulo.

#### Ajustes generales

-   **Activado / Desactivado (Interruptor global)**
    -   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad de todo el módulo en su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo comenzará a mostrar los precios con y sin impuestos según sus otras configuraciones.
        -   *Cuando está desactivado:* El módulo dejará de mostrar la información de precio adicional, y su tienda volverá a su comportamiento predeterminado de visualización de precios.
    -   **Valor recomendado:** Activado (para utilizar las características del módulo).
    -   **Escenario / ejemplo del comerciante:** Si está realizando mantenimiento o desea ocultar temporalmente la visualización de doble precio, puede desactivarlo aquí.

#### Ajustes de la página de producto

-   **Mostrar en la página de producto (BF\_PP)**

    -   **Qué hace este ajuste:** Controla si los precios con y sin impuestos se muestran en las páginas de detalles de productos individuales.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Ambos precios aparecerán en las páginas de productos.
        -   *Cuando está desactivado:* Solo se mostrará el precio predeterminado de PrestaShop (generalmente con impuestos incluidos) en las páginas de productos.
    -   **Valor recomendado:** Activado (para proporcionar total transparencia).
    -   **Escenario / ejemplo del comerciante:** Si solo desea mostrar precios duales en los listados de categorías, pero mantener las páginas de productos más limpias, podría desactivar esto.
-   **Ocultar precio con impuestos incluidos en la página de producto (BOTH\_HIDE\_P)**

    -   **Qué hace este ajuste:** Si "Mostrar en la página de producto" está activado, esta opción le permite ocultar el precio con impuestos incluidos, mostrando efectivamente solo el precio sin impuestos junto con el precio original (si no está oculto).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El precio con impuestos incluidos se ocultará en las páginas de productos.
        -   *Cuando está desactivado:* El precio con impuestos incluidos será visible en las páginas de productos (si "Mostrar en la página de producto" está activado).
    -   **Valor recomendado:** Desactivado (a menos que tenga una razón específica para ocultarlo, por ejemplo, una tienda enfocada en B2B).
    -   **Escenario / ejemplo del comerciante:** Una tienda B2B podría querer enfatizar los precios sin impuestos y ocultar el precio con impuestos incluidos para simplificar la vista para sus clientes comerciales.
-   **CSS personalizado para la página de producto (BF\_PPC)**

    -   **Qué hace este ajuste:** Le permite añadir reglas CSS personalizadas específicamente para la visualización de doble precio en las páginas de productos. Esto es para usuarios avanzados o webmasters.
    -   **Efecto de cambiar este ajuste:** Cualquier código CSS introducido aquí se aplicará a los elementos de precio del módulo en las páginas de productos, permitiéndole cambiar colores, fuentes, tamaños o posicionamiento.
    -   **Valor recomendado:** Dejar vacío a menos que tenga necesidades de estilo específicas.
    -   **Escenario / ejemplo del comerciante:** Es posible que desee que el precio sin impuestos sea más pequeño o de un color diferente al precio con impuestos incluidos para diferenciarlos visualmente.
-   **Forzar ocultar página de producto (BP\_FORCE\_HIDE)**

    -   **Qué hace este ajuste:** Esta es una opción más agresiva para ocultar la salida del módulo en la página de producto. Puede ser útil si la salida del módulo entra en conflicto con su tema u otros módulos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo intentará ocultar forzosamente su visualización de precios en las páginas de productos, independientemente de otras configuraciones.
        -   *Cuando está desactivado:* El módulo mostrará los precios según otras configuraciones.
    -   **Valor recomendado:** Desactivado (solo active si experimenta problemas de visualización).
    -   **Escenario / ejemplo del comerciante:** Si la visualización de doble precio se superpone con otro elemento en su página de producto, habilitar esto podría resolver el conflicto.
-   **Etiqueta de precio con impuestos incluidos (BP\_TIN)**

    -   **Qué hace este ajuste:** Define la etiqueta de texto que se muestra junto al precio con impuestos incluidos en las páginas de productos.
    -   **Efecto de cambiar este ajuste:** Cambia el texto de la etiqueta.
    -   **Valor recomendado:** "Impuestos incl." o "IVA incl."
    -   **Escenario / ejemplo del comerciante:** Podría cambiar esto a "Precio con IVA" para mayor claridad en ciertas regiones.
-   **Etiqueta de precio sin impuestos (BP\_TEX)**

    -   **Qué hace este ajuste:** Define la etiqueta de texto que se muestra junto al precio sin impuestos en las páginas de productos.
    -   **Efecto de cambiar este ajuste:** Cambia el texto de la etiqueta.
    -   **Valor recomendado:** "Impuestos excl." o "IVA excl."
    -   **Escenario / ejemplo del comerciante:** Podría cambiar esto a "Precio sin IVA" para mayor claridad.
-   **Etiqueta de precio original con impuestos incluidos (BP\_O\_TIN)**

    -   **Qué hace este ajuste:** Define la etiqueta de texto para el precio *original* con impuestos incluidos, especialmente útil cuando se aplican precios específicos o descuentos.
    -   **Efecto de cambiar este ajuste:** Cambia el texto de la etiqueta.
    -   **Valor recomendado:** "Impuestos incl. originales"
    -   **Escenario / ejemplo del comerciante:** Cuando un producto está en oferta, es posible que desee mostrar el precio original con una etiqueta específica.

#### Ajustes de la página de listado de productos

-   **Mostrar en el listado de productos (BF\_PL)**

    -   **Qué hace este ajuste:** Controla si los precios con y sin impuestos se muestran en las páginas de listado de productos (categorías, resultados de búsqueda, módulos de la página de inicio).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Ambos precios aparecerán en las páginas de listado de productos.
        -   *Cuando está desactivado:* Solo se mostrará el precio predeterminado de PrestaShop en las páginas de listado de productos.
    -   **Valor recomendado:** Activado (para una transparencia consistente).
    -   **Escenario / ejemplo del comerciante:** Si sus páginas de categorías son muy densas, podría desactivar esto para reducir el desorden visual.
-   **Ocultar precio con impuestos incluidos en el listado de productos (BOTH\_HIDE\_PL)**

    -   **Qué hace este ajuste:** Si "Mostrar en el listado de productos" está activado, esta opción le permite ocultar el precio con impuestos incluidos en las páginas de listado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El precio con impuestos incluidos se ocultará en las páginas de listado de productos.
        -   *Cuando está desactivado:* El precio con impuestos incluidos será visible en las páginas de listado de productos.
    -   **Valor recomendado:** Desactivado (a menos que tenga una razón específica para ocultarlo).
    -   **Escenario / ejemplo del comerciante:** Una tienda B2B podría querer mostrar solo precios sin impuestos en todos los listados de productos.
-   **CSS personalizado para el listado de productos (BF\_PLC)**

    -   **Qué hace este ajuste:** Le permite añadir reglas CSS personalizadas específicamente para la visualización de doble precio en las páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:** Cualquier código CSS introducido aquí se aplicará a los elementos de precio del módulo en las páginas de listado.
    -   **Valor recomendado:** Dejar vacío a menos que tenga necesidades de estilo específicas.
    -   **Escenario / ejemplo del comerciante:** Es posible que desee que el precio sin impuestos sea más pequeño y atenuado en las páginas de categorías para que el precio principal (con impuestos incluidos) destaque más.
-   **Etiqueta de precio con impuestos incluidos (BP\_TINL)**

    -   **Qué hace este ajuste:** Define la etiqueta de texto que se muestra junto al precio con impuestos incluidos en las páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:** Cambia el texto de la etiqueta.
    -   **Valor recomendado:** "Impuestos incl." o "IVA incl."
    -   **Escenario / ejemplo del comerciante:** Podría usar una etiqueta más corta como "incl." en las páginas de listado debido al espacio limitado.
-   **Etiqueta de precio sin impuestos (BP\_TEXL)**

    -   **Qué hace este ajuste:** Define la etiqueta de texto que se muestra junto al precio sin impuestos en las páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:** Cambia el texto de la etiqueta.
    -   **Valor recomendado:** "Impuestos excl." o "IVA excl."
    -   **Escenario / ejemplo del comerciante:** Podría usar una etiqueta más corta como "excl." en las páginas de listado.

#### Reglas de visibilidad

-   **Regla de visibilidad (bp\_visibility\_rule)**

    -   **Qué hace este ajuste:** Determina cómo se comporta la visualización de doble precio en función de los grupos de clientes, productos específicos o categorías.
    -   **Efecto de cambiar este ajuste:**
        -   *Mostrar siempre:* Los precios duales se muestran siempre para todos los clientes, productos y categorías.
        -   *Ocultar para grupos/productos/categorías seleccionados:* Los precios duales se ocultan para selecciones específicas.
        -   *Mostrar solo para grupos/productos/categorías seleccionados:* Los precios duales solo se muestran para selecciones específicas.
    -   **Valor recomendado:** Mostrar siempre (para máxima transparencia), o "Mostrar solo para grupos seleccionados" si se dirige específicamente a clientes B2B.
    -   **Escenario / ejemplo del comerciante:** Podría elegir "Mostrar solo para grupos seleccionados" y luego seleccionar su grupo de "Clientes mayoristas" para mostrar precios duales solo para sus clientes B2B.
-   **Visibilidad para grupos de clientes (actionAdminGroupsControllerSaveAfter)**

    -   **Qué hace este ajuste:** Le permite seleccionar qué grupos de clientes verán la visualización de doble precio, según la "Regla de visibilidad" anterior.
    -   **Efecto de cambiar este ajuste:** Solo los clientes que pertenezcan a los grupos seleccionados verán los precios duales (si la regla es "Mostrar solo para grupos seleccionados") o *no* los verán (si la regla es "Ocultar para grupos seleccionados").
    -   **Valor recomendado:** Seleccione "Todos los grupos de clientes" si su regla es "Mostrar siempre". De lo contrario, seleccione los grupos relevantes.
    -   **Escenario / ejemplo del comerciante:** Si desea que solo sus grupos "Invitado" y "Cliente" vean principalmente los precios con impuestos incluidos, pero "Mayorista" vea ambos, configuraría la regla en "Mostrar solo para grupos seleccionados" y seleccionaría "Mayorista".
-   **Visibilidad para productos (bp\_visibility\_products)**

    -   **Qué hace este ajuste:** Le permite especificar productos individuales para los cuales la visualización de doble precio debe aplicarse (o no aplicarse), según la "Regla de visibilidad". Esto utiliza un campo de búsqueda con autocompletado.
    -   **Efecto de cambiar este ajuste:** La visualización de doble precio se habilitará o deshabilitará para los productos seleccionados según la regla de visibilidad elegida.
    -   **Valor recomendado:** Dejar vacío si desea que se aplique a todos los productos.
    -   **Escenario / ejemplo del comerciante:** Es posible que tenga algunos productos específicos donde mostrar ambos precios es confuso, por lo que configuraría la regla en "Ocultar para productos seleccionados" y añadiría esos productos aquí.
-   **Visibilidad para categorías (bp\_visibility\_cat)**

    -   **Qué hace este ajuste:** Le permite especificar categorías para las cuales la visualización de doble precio debe aplicarse (o no aplicarse), según la "Regla de visibilidad".
    -   **Efecto de cambiar este ajuste:** La visualización de doble precio se habilitará o deshabilitará para todos los productos dentro de las categorías seleccionadas según la regla de visibilidad elegida.
    -   **Valor recomendado:** Dejar vacío si desea que se aplique a todas las categorías.
    -   **Escenario / ejemplo del comerciante:** Si vende tanto bienes físicos (donde el impuesto es relevante) como productos digitales (donde el impuesto podría manejarse de manera diferente), podría ocultar los precios duales para su categoría de "Descargas digitales".

#### Opciones de visualización

-   **Mostrar tipos de precio (BF\_SHOW\_TYPES)**

    -   **Qué hace este ajuste:** Determina qué tipos de precio se muestran.
    -   **Efecto de cambiar este ajuste:**
        -   *Impuestos incluidos e Impuestos excluidos:* Muestra ambos precios.
        -   *Solo Impuestos incluidos:* Muestra solo el precio con impuestos incluidos (el módulo sigue procesando, pero solo muestra uno).
        -   *Solo Impuestos excluidos:* Muestra solo el precio sin impuestos.
    -   **Valor recomendado:** Impuestos incluidos e Impuestos excluidos (para aprovechar la característica principal del módulo).
    -   **Escenario / ejemplo del comerciante:** Si su objetivo principal es mostrar precios sin impuestos a clientes B2B, podría seleccionar "Solo Impuestos excluidos" junto con una regla de visibilidad de grupo de clientes.
-   **Usar CSS del tema Classic (BF\_CLASSICCSS)**

    -   **Qué hace este ajuste:** Si su tema se basa en el tema Classic predeterminado de PrestaShop, habilitar esto aplicará reglas CSS específicas diseñadas para integrarse sin problemas con el estilo de ese tema.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo cargará una hoja de estilo dedicada (`classic.css`) para asegurar una mejor integración visual con los temas basados en Classic.
        -   *Cuando está desactivado:* El módulo utilizará su estilo predeterminado, lo que podría requerir CSS personalizado para una integración perfecta con temas no Classic.
    -   **Valor recomendado:** Activar si su tema se basa en Classic o es un tema hijo de Classic. Desactivar en caso contrario.
    -   **Escenario / ejemplo del comerciante:** Si acaba de instalar el módulo y los precios se ven desalineados en su tema Classic, habilitar esto podría solucionarlo.
-   **CSS propio (BF\_OWNCSS)**

    -   **Qué hace este ajuste:** Proporciona un área de texto donde puede introducir su propio código CSS personalizado para anular o añadir estilos a la salida del módulo. Esto es para usuarios avanzados o webmasters.
    -   **Efecto de cambiar este ajuste:** Cualquier código CSS introducido aquí se aplicará globalmente a las visualizaciones de precios del módulo, permitiendo un control completo sobre el estilo.
    -   **Valor recomendado:** Dejar vacío a menos que tenga necesidades de estilo específicas.
    -   **Escenario / ejemplo del comerciante:** Desea cambiar el tamaño de la fuente de los precios mostrados o añadir un borde alrededor de ellos para hacerlos más prominentes.

#### Ajustes avanzados

-   **Porcentaje de impuestos en la página de producto (BP\_PP\_TPERCENT)**

    -   **Qué hace este ajuste:** Le permite mostrar el porcentaje de impuestos en las páginas de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* El porcentaje de impuestos (por ejemplo, "20% IVA") se mostrará junto a los precios.
        -   *Desactivado:* El porcentaje de impuestos no se mostrará.
    -   **Valor recomendado:** Desactivado (a menos que desee mostrar explícitamente la tasa de impuestos).
    -   **Escenario / ejemplo del comerciante:** En países donde los clientes son muy conscientes de los impuestos, mostrar el porcentaje puede añadir otra capa de transparencia.
-   **Porcentaje de impuestos en la página de producto (Impuestos excluidos) (BP\_PP\_TPERCENT\_TEXL)**

    -   **Qué hace este ajuste:** Similar al anterior, pero específicamente para la visualización del precio sin impuestos en las páginas de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* El porcentaje de impuestos se mostrará junto al precio sin impuestos.
        -   *Desactivado:* El porcentaje de impuestos no se mostrará.
    -   **Valor recomendado:** Desactivado.
    -   **Escenario / ejemplo del comerciante:** Útil si desea resaltar la tasa de impuestos que se está excluyendo.
-   **Porcentaje de impuestos en el listado de productos (BP\_PL\_TPERCENT)**

    -   **Qué hace este ajuste:** Le permite mostrar el porcentaje de impuestos en las páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* El porcentaje de impuestos se mostrará junto a los precios en las páginas de listado.
        -   *Desactivado:* El porcentaje de impuestos no se mostrará.
    -   **Valor recomendado:** Desactivado (para mantener las páginas de listado más limpias).
    -   **Escenario / ejemplo del comerciante:** Si sus listados de productos no están demasiado abarrotados, mostrar el porcentaje de impuestos puede ser informativo.
-   **Porcentaje de impuestos en el listado de productos (Impuestos excluidos) (BP\_PL\_TPERCENT\_TEXL)**

    -   **Qué hace este ajuste:** Similar al anterior, pero específicamente para la visualización del precio sin impuestos en las páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* El porcentaje de impuestos se mostrará junto al precio sin impuestos en las páginas de listado.
        -   *Desactivado:* El porcentaje de impuestos no se mostrará.
    -   **Valor recomendado:** Desactivado.
    -   **Escenario / ejemplo del comerciante:** Menos común, pero podría usarse para enfatizar el componente fiscal que se está eliminando.

#### Ajustes de idioma (Interno)

-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**
    -   **Qué hace este ajuste:** Estos son ajustes internos de PrestaShop relacionados con el idioma predeterminado y el idioma del formulario de empleado. Se muestran aquí con fines informativos y no son directamente configurables por el módulo.
    -   **Efecto de cambiar este ajuste:** No aplicable, estos son valores de solo lectura de su configuración de PrestaShop.
    -   **Valor recomendado:** N/A
    -   **Escenario / ejemplo del comerciante:** Estos valores ayudan al módulo a determinar qué idioma usar para las etiquetas si no las ha configurado explícitamente para todos los idiomas.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminBothpricesSearchController (Back Office > Módulos > Mostrar dos precios - impuestos incluidos / excluidos > Buscar productos)

Esta pantalla de administración dedicada se utiliza para gestionar la configuración de "Visibilidad para productos". Proporciona una interfaz para buscar y seleccionar productos específicos que deben verse afectados por las reglas de visibilidad del módulo.

-   **Nombre de la pantalla y ubicación del menú:** Puede acceder a esta pantalla haciendo clic en el enlace o botón "Buscar productos" dentro de la página de configuración principal del módulo, generalmente junto a la configuración "Visibilidad para productos".
-   **Acciones y configuraciones disponibles:**
    -   **Campo de búsqueda de productos:** Un campo de texto donde puede escribir nombres o ID de productos para encontrar productos específicos.
    -   **Cuadrícula de resultados de búsqueda:** Muestra una lista de productos que coinciden con su consulta de búsqueda.
    -   **Botones Añadir/Eliminar:** Le permite añadir o eliminar productos seleccionados de la lista de productos afectados por la regla de visibilidad.
    -   **Lista de productos seleccionados:** Muestra todos los productos actualmente configurados para la regla de visibilidad.
-   **Efecto de los cambios:**
    -   Añadir un producto a la lista significa que la visualización de doble precio del módulo se mostrará *solo* para ese producto o se *ocultará* para ese producto, dependiendo de su configuración general de "Regla de visibilidad".
    -   Eliminar un producto significa que ya no se verá afectado específicamente por la regla de visibilidad a nivel de producto y volverá a la configuración general del módulo.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Vaya a la página de configuración principal del módulo.
    2.  Establezca su "Regla de visibilidad" (por ejemplo, "Ocultar para productos seleccionados").
    3.  Haga clic en el enlace/botón para abrir la pantalla "AdminBothpricesSearchController".
    4.  Utilice el campo de búsqueda para encontrar los productos que desea incluir en la regla.
    5.  Añádalos a la "Lista de productos seleccionados".
    6.  Guarde sus cambios en la página de configuración principal del módulo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activado / Desactivado | Activado | Interruptor maestro para la funcionalidad del módulo. |
| Configuración del módulo | Mostrar en la página de producto (BF\_PP) | Activado | Muestra precios duales en las páginas de detalles del producto. |
| Configuración del módulo | Ocultar precio con impuestos incluidos en la página de producto (BOTH\_HIDE\_P) | Desactivado | Oculta el precio con impuestos incluidos en las páginas de productos. |
| Configuración del módulo | CSS personalizado para la página de producto (BF\_PPC) | Vacío | CSS personalizado para la visualización de precios en la página de producto. |
| Configuración del módulo | Forzar ocultar página de producto (BP\_FORCE\_HIDE) | Desactivado | Oculta forzosamente la salida del módulo en la página de producto. |
| Configuración del módulo | Etiqueta de precio con impuestos incluidos (BP\_TIN) | "Impuestos incl." | Etiqueta para el precio con impuestos incluidos en la página de producto. |
| Configuración del módulo | Etiqueta de precio sin impuestos (BP\_TEX) | "Impuestos excl." | Etiqueta para el precio sin impuestos en la página de producto. |
| Configuración del módulo | Etiqueta de precio original con impuestos incluidos (BP\_O\_TIN) | "Impuestos incl. originales" | Etiqueta para el precio original con impuestos incluidos en la página de producto. |
| Configuración del módulo | Mostrar en el listado de productos (BF\_PL) | Activado | Muestra precios duales en las páginas de categoría/listado. |
| Configuración del módulo | Ocultar precio con impuestos incluidos en el listado de productos (BOTH\_HIDE\_PL) | Desactivado | Oculta el precio con impuestos incluidos en las páginas de listado. |
| Configuración del módulo | CSS personalizado para el listado de productos (BF\_PLC) | Vacío | CSS personalizado para la visualización de precios en la página de listado. |
| Configuración del módulo | Etiqueta de precio con impuestos incluidos (BP\_TINL) | "Impuestos incl." | Etiqueta para el precio con impuestos incluidos en las páginas de listado. |
| Configuración del módulo | Etiqueta de precio sin impuestos (BP\_TEXL) | "Impuestos excl." | Etiqueta para el precio sin impuestos en las páginas de listado. |
| Configuración del módulo | Regla de visibilidad (bp\_visibility\_rule) | Mostrar siempre | Define cómo se aplican las reglas de visibilidad (mostrar/ocultar para seleccionados). |
| Configuración del módulo | Visibilidad para grupos de clientes | Todos los grupos de clientes | Selecciona los grupos de clientes afectados por la regla de visibilidad. |
| Configuración del módulo | Visibilidad para productos (bp\_visibility\_products) | Vacío | Selecciona productos específicos afectados por la regla de visibilidad. |
| Configuración del módulo | Visibilidad para categorías (bp\_visibility\_cat) | Vacío | Selecciona categorías específicas afectadas por la regla de visibilidad. |
| Configuración del módulo | Mostrar tipos de precio (BF\_SHOW\_TYPES) | Impuestos incluidos e Impuestos excluidos | Determina qué tipos de precio se muestran (ambos, solo incl., solo excl.). |
| Configuración del módulo | Usar CSS del tema Classic (BF\_CLASSICCSS) | Desactivado (Activar para temas Classic) | Aplica estilos específicos del tema Classic. |
| Configuración del módulo | CSS propio (BF\_OWNCSS) | Vacío | CSS personalizado global para la salida del módulo. |
| Configuración del módulo | Porcentaje de impuestos en la página de producto (BP\_PP\_TPERCENT) | Desactivado | Muestra el porcentaje de impuestos en las páginas de productos. |
| Configuración del módulo | Porcentaje de impuestos en la página de producto (Impuestos excluidos) (BP\_PP\_TPERCENT\_TEXL) | Desactivado | Muestra el porcentaje de impuestos para el precio sin impuestos en las páginas de productos. |
| Configuración del módulo | Porcentaje de impuestos en el listado de productos (BP\_PL\_TPERCENT) | Desactivado | Muestra el porcentaje de impuestos en las páginas de listado. |
| Configuración del módulo | Porcentaje de impuestos en el listado de productos (Impuestos excluidos) (BP\_PL\_TPERCENT\_TEXL) | Desactivado | Muestra el porcentaje de impuestos para el precio sin impuestos en las páginas de listado. |
| AdminBothpricesSearchController | Búsqueda de productos / Añadir/Eliminar | N/A | Gestiona la lista de productos para las reglas de visibilidad. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El módulo está activado, pero no veo dos precios en mi tienda.**
R:

-   **Verificar activación global:** Asegúrese de que el interruptor principal "Activado / Desactivado" en la parte superior de la configuración del módulo esté en "Activado".
-   **Verificar ajustes específicos de la página:** Verifique que "Mostrar en la página de producto" (BF\_PP) y/o "Mostrar en el listado de productos" (BF\_PL) estén activados, dependiendo de dónde espere ver los precios.
-   **Verificar reglas de visibilidad:** Si ha establecido una "Regla de visibilidad", asegúrese de que su grupo de clientes, producto o categoría actual esté incluido en la regla de "mostrar" o no esté excluido por una regla de "ocultar".
-   **Borrar caché:** Siempre borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) después de realizar cambios en la configuración del módulo. Además, borre la caché de su navegador.
-   **Conflictos de tema:** Algunos temas altamente personalizados pueden entrar en conflicto. Intente cambiar temporalmente al tema Classic predeterminado de PrestaShop para ver si aparecen los precios. Si lo hacen, es un conflicto de CSS o JS relacionado con el tema.

**P2: Los precios se muestran, pero se ven desalineados o tienen un estilo incorrecto.**
R:

-   **Usar CSS del tema Classic:** Si su tema se basa en el tema Classic predeterminado de PrestaShop, intente habilitar la opción "Usar CSS del tema Classic (BF\_CLASSICCSS)" en la configuración del módulo.
-   **CSS personalizado:** Si tiene un tema personalizado, es posible que deba añadir CSS personalizado. Utilice las herramientas de desarrollo de su navegador (F12) para identificar las clases CSS de los elementos de precio del módulo. Luego, use el campo "CSS propio (BF\_OWNCSS)" en la configuración del módulo para añadir sus reglas de estilo.
-   **Posición del módulo:** Asegúrese de que el módulo esté enganchado correctamente. Aunque el módulo maneja la mayoría de los hooks automáticamente, a veces pueden ser necesarios hooks específicos del tema.

**P3: Los precios no se actualizan cuando cambio los atributos del producto (por ejemplo, tamaño, color) en la página del producto.**
R:

-   **Compatibilidad del módulo:** Asegúrese de que su versión de PrestaShop esté dentro del rango compatible.
-   **Conflictos de JavaScript:** Esto a menudo es causado por conflictos de JavaScript con su tema u otro módulo. Verifique la consola de su navegador (F12 > pestaña Consola) en busca de errores de JavaScript al cambiar los atributos.
-   **Sobreescrituras de tema:** Si su tema sobrescribe en gran medida el JavaScript predeterminado de la página de producto de PrestaShop, podría evitar que el módulo detecte cambios de precio. Póngase en contacto con el desarrollador de su tema o un webmaster para obtener ayuda.
-   **Borrar caché:** Borre la caché de PrestaShop y del navegador.

**Q4: ¿Cómo traduzco las etiquetas de precio (por ejemplo, "Impuestos incl.", "Impuestos excl.") a otros idiomas?**
R:

-   Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
-   Seleccione "Traducciones de módulos instalados".
-   Elija su tema.
-   Seleccione su idioma.
-   Busque el módulo "Mostrar dos precios - impuestos incluidos / excluidos" en la lista.
-   Encontrará campos para "Etiqueta de precio con impuestos incluidos", "Etiqueta de precio sin impuestos", etc., tanto para las páginas de productos como para las de listado. Introduzca sus traducciones allí y guarde.

**Q5: Solo quiero mostrar precios sin impuestos a grupos de clientes específicos (por ejemplo, B2B). ¿Cómo lo hago?**
R:

-   En la configuración del módulo, establezca **"Regla de visibilidad"** en "Mostrar solo para grupos seleccionados".
-   Luego, seleccione el(los) grupo(s) de clientes específico(s) (por ejemplo, "Mayorista", "B2B") que deben ver los precios duales.
-   Opcionalmente, establezca **"Mostrar tipos de precio"** en "Solo Impuestos excluidos" si desea ocultar completamente el precio con impuestos incluidos para estos grupos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Mostrar dos precios - impuestos incluidos / excluidos" (`bothprices`) es un módulo estándar de PrestaShop que sigue el patrón MVC. Principalmente extiende la clase `Module`, aprovechando el sistema de hooks de PrestaShop para inyectar información de precios y modificar la visualización. Utiliza un controlador de administración dedicado para la funcionalidad de búsqueda de productos y controladores frontales para interacciones AJAX. El módulo se basa en plantillas Smarty para la renderización y JavaScript/CSS personalizado para actualizaciones dinámicas y estilos. La configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nombre de la clase y clase padre**: `BothpricesAjaxModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad**: Maneja las solicitudes AJAX desde el front-office, principalmente para actualizar dinámicamente los precios cuando se cambian los atributos del producto. Probablemente obtiene información del producto y calcula los precios en función de los atributos seleccionados y el contexto del cliente, devolviendo datos JSON.
    -   `controllers/front/index.php`
        -   **Nombre de la clase y clase padre**: `BothpricesIndexModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este es un controlador de marcador de posición o de reserva. En muchos módulos, los controladores `index.php` se utilizan para el enrutamiento básico o para evitar la lista de directorios. Es posible que no tenga una lógica personalizada significativa más allá del despacho básico.
-   **Controladores de administración de Back-Office**:

    -   `controllers/admin/AdminBothpricesSearchController.php`
        -   **Nombre de la clase y clase padre**: `AdminBothpricesSearchController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona la búsqueda y selección de productos para las reglas de visibilidad del módulo. No gestiona directamente un `ObjectModel` específico, sino que interactúa con los datos de `Product` para la selección. Proporciona una interfaz similar a una cuadrícula para buscar y añadir/eliminar productos de la configuración `bp_visibility_products`.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no parece definir ninguna clase `ObjectModel` personalizada en el directorio `classes/`. Probablemente se basa en las clases `Product` y `Configuration` existentes de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

-   `bothprices/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance**: Back-office.
    -   **Descripción**: Proporciona funcionalidad de autocompletado para el campo de búsqueda de productos dentro de `AdminBothpricesSearchController`, permitiendo a los administradores encontrar y seleccionar rápidamente productos para las reglas de visibilidad.
-   `bothprices/views/js/both-hide-p.js`
    -   **Alcance**: Front-office (Página de producto).
    -   **Descripción**: Contiene la lógica JavaScript para ocultar el precio con impuestos incluidos específicamente en la página de producto, basándose en la configuración `BOTH_HIDE_P`. Probablemente apunta a elementos DOM específicos para aplicar `display: none` o un estilo similar.
-   `bothprices/views/js/both-hide-pl.js`
    -   **Alcance**: Front-office (Páginas de listado de productos).
    -   **Descripción**: Similar a `both-hide-p.js`, pero para las páginas de listado de productos, ocultando el precio con impuestos incluidos basándose en la configuración `BOTH_HIDE_PL`.
-   `bothprices/views/js/bothprices-admin.js`
    -   **Alcance**: Back-office.
    -   **Descripción**: Contiene JavaScript general para la página de configuración del back-office del módulo. Esto podría incluir lógica para mostrar/ocultar campos de configuración basados en otras selecciones (por ejemplo, cambios en la regla de visibilidad), validación de formularios o llamadas AJAX para guardar configuraciones.
-   `bothprices/views/js/bothprices.js`
    -   **Alcance**: Front-office (Global).
    -   **Descripción**: Este es el archivo JavaScript principal del front-office. Es responsable de:
        -   Escuchar `prestashop.on('updateProduct', ...)` o eventos similares para detectar cambios en los atributos del producto.
        -   Realizar llamadas AJAX a `controllers/front/ajax.php` para obtener precios duales actualizados.
        -   Actualizar dinámicamente los precios con y sin impuestos mostrados en la página de producto y potencialmente en las páginas de listado.
        -   Aplicar CSS o clases personalizadas basadas en la configuración del módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `bothprices/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance**: Back-office.
    -   **Descripción**: Estilos para el desplegable de autocompletado y los resultados de búsqueda dentro de la interfaz `AdminBothpricesSearchController`.
-   `bothprices/views/css/admin.css`
    -   **Alcance**: Back-office.
    -   **Descripción**: Estilo general para la página de configuración del módulo en el Back Office de PrestaShop, asegurando una apariencia consistente con el panel de administración.
-   `bothprices/views/css/bothprices.css`
    -   **Alcance**: Front-office (Global).
    -   **Descripción**: Contiene las reglas CSS predeterminadas para mostrar los precios duales tanto en las páginas de productos como en las páginas de listado. Esto incluye formato básico, posicionamiento y diferenciación de los dos elementos de precio.
    -   **Selectores de clase CSS clave**: Los desarrolladores pueden buscar clases como `.bothprices_price_tax_incl`, `.bothprices_price_tax_excl`, `.bothprices_wrapper` para sobrescribir.
-   `bothprices/views/css/classic.css`
    -   **Alcance**: Front-office (Específico del tema Classic).
    -   **Descripción**: Contiene reglas CSS adicionales o de anulación diseñadas específicamente para mejorar la integración visual con el tema Classic predeterminado de PrestaShop o temas basados en él. Este archivo se carga condicionalmente según la configuración `BF_CLASSICCSS`.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `bothprices/views/templates/bothprices.tpl`
        -   **Hook**: Probablemente renderizado en hooks como `displayProductPriceBlock`, `displayProductListReviews`, `displayProductPriceBlock`, `displayProductPriceBlock`, `displayAfterProductThumbs` o similares, tanto en las páginas de productos como en las de listado.
        -   **Salida**: Esta plantilla es responsable de renderizar la estructura HTML real de la visualización de doble precio (precios con y sin impuestos) junto con sus etiquetas. Recibe variables de precio de la lógica PHP del módulo.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `bothprices/views/templates/admin/configure_shell.tpl`
        -   **Hook**: Renderizado dentro del método `getContent()` del módulo para la página de configuración principal.
        -   **Salida**: Esto actúa como un envoltorio o shell para el formulario de configuración del módulo, que potencialmente incluye pestañas, encabezados y pies de página para la interfaz de administración.
    -   `bothprices/views/templates/selectedProducts.tpl`
        -   **Hook**: Utilizado por `AdminBothpricesSearchController`.
        -   **Salida**: Renderiza la lista de productos que han sido seleccionados para las reglas de visibilidad, típicamente en formato de tabla o lista dentro de la interfaz de búsqueda de administración.
-   **Plantillas de Front-office (`views/templates/front/`)**:
    -   `bothprices/views/templates/bothprices-product-page.tpl`
        -   **Hook**: Probablemente renderizado en la página de producto, posiblemente dentro de `displayProductPriceBlock` o similar.
        -   **Salida**: Una plantilla específica para la visualización de doble precio de la página de producto, potencialmente con información más detallada o un diseño diferente en comparación con las páginas de listado.
-   **Plantillas de biblioteca (`lib/searchTool/views/scripts.tpl`)**:
    -   `bothprices/lib/searchTool/views/scripts.tpl`
        -   **Hook**: Probablemente incluido en la vista `AdminBothpricesSearchController`.
        -   **Salida**: Contiene scripts de inicialización de JavaScript o variables de configuración para la herramienta de búsqueda de autocompletado.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para almacenar su configuración. Las claves de configuración incluyen: `mypresta_updates`, `update_`, `updatev_`, `BOTH_HIDE_PL_CSS`, `BOTH_HIDE_P_CSS`, `BF_PP`, `BF_PL`, `bp_visibility_rule`, `bp_visibility_products`, `bp_visibility_cat`, `BF_SHOW_TYPES`, `BF_PLC`, `BF_PPC`, `BP_FORCE_HIDE`, `BP_PP_TPERCENT_TEXL`, `BP_PP_TPERCENT`, `BP_PL_TPERCENT_TEXL`, `BP_PL_TPERCENT`, `BOTH_HIDE_PL`, `BOTH_HIDE_P`, `BF_OWNCSS`, `BF_CLASSICCSS`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `BP_TIN`, `BP_TIN_L`, `BP_TEX`, `BP_TEX_L`, `BP_TINL`, `BP_TINL_L`, `BP_TEXL`, `BP_TEXL_L`, `BP_O_TIN`, `BP_O_TIN_L`, `BP_O_TEX`.
    -   No parece crear ninguna tabla SQL personalizada.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `ActionFrontControllerSetMedia` | Front-Office | Antes de la salida del controlador, después de la inicialización de medios. | Inyecta los activos CSS y JS del módulo en el front-office. |
| `ActionAdminGroupsControllerSaveAfter` | Back-Office | Después de que un administrador guarda un grupo de clientes. | Potencialmente utilizado para borrar la caché o reevaluar las reglas de visibilidad relacionadas con los grupos de clientes. |
| `ActionAdminControllerSetMedia` | Back-Office | Antes de la salida del controlador de administración, después de la inicialización de medios. | Inyecta los activos CSS y JS del módulo en el back-office (por ejemplo, para la página de configuración, controlador de búsqueda). |
| `updateproduct` | Back-Office | Después de que se actualiza un producto. | Borra las cachés relevantes, reevalúa los datos de precios específicos del producto. |
| `ActionProductDelete` | Back-Office | Después de que se elimina un producto. | Limpia cualquier dato específico del módulo relacionado con el producto eliminado (por ejemplo, de `bp_visibility_products`). |
| `displayUpdateProduct` | Back-Office | En la página de edición de producto. | Potencialmente inyecta campos o información personalizada en el formulario de edición de producto. |
| `actionProductUpdate` | Back-Office | Después de que se actualiza un producto. | Similar a `updateproduct`, asegura que los datos internos del módulo reflejen los cambios del producto. |
| `displayHeader` | Front-Office | En la sección `<head>` de cada página del front-office. | Inyecta el CSS y JS del módulo para disponibilidad global, o renderiza un pequeño fragmento. |
| `displayCategoryUpdate` | Back-Office | En la página de edición de categoría. | Potencialmente inyecta campos o información personalizada en el formulario de edición de categoría. |
| `ActionCategoryUpdate` | Back-Office | Después de que se actualiza una categoría. | Borra las cachés relevantes, reevalúa los datos de precios específicos de la categoría. |
| `actionProductAdd` | Back-Office | Después de que se añade un nuevo producto. | Inicializa los datos específicos del módulo para el nuevo producto. |
| `actionObjectSpecificPriceUpdateAfter` | Back-Office | Después de que se actualiza un precio específico (descuento). | Asegura que los cálculos de precios dinámicos reflejen los nuevos precios específicos. |
| `categoryUpdate` | Back-Office | Después de que se actualiza una categoría. | Alias o duplicado de `ActionCategoryUpdate`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Mostrar dos precios - impuestos incluidos / excluidos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad del módulo.
