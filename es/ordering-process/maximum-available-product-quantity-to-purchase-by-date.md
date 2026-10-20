---
title: "Cantidad máxima de producto disponible para comprar por fecha - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cantidad máxima de producto disponible para comprar por fecha' de MyPresta.eu."
sidebar:
  label: "Cantidad máxima de producto disponible para comprar por fecha"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Maximum available product quantity to purchase by date en MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-available-product-quantity-to-purchase-by-date.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/maximum-available-product-quantity-to-purchase-by-date/)
>
> ---


# Cantidad máxima de producto disponible para comprar por fecha

## 1. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal del módulo, a la que se accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

-   **Qué hace este ajuste:** Esta pantalla suele contener ajustes generales para el módulo, como habilitar/deshabilitar su funcionalidad principal o establecer preferencias globales.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* Las funciones de limitación de cantidad del módulo estarán activas en su tienda según las reglas que defina.
    -   *Cuando está deshabilitado:* El módulo dejará de aplicar cualquier límite de cantidad, y los clientes podrán comprar cualquier cantidad de stock disponible.
-   **Valor recomendado:** "SÍ" (Habilitado) para activar la funcionalidad principal del módulo.
-   **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y quiere empezar a definir límites. El primer paso es asegurarse de que el módulo esté activo en esta pantalla antes de proceder a definir límites de productos específicos.

### 2.2 Pantalla de administración dedicada: Límite de cantidad de compra de producto por fecha (Back Office > Catálogo > Límite de cantidad de compra de producto por fecha)
Esta es la pantalla principal donde define y gestiona todos sus límites de cantidad de producto basados en rangos de fechas.

**Nombre de la pantalla y ubicación del menú:**
Puede encontrar esta pantalla navegando a **Catálogo > Límite de cantidad de compra de producto por fecha** en el menú de su Back Office de PrestaShop.

**Acciones y ajustes disponibles:**
Esta pantalla presenta una lista (cuadrícula) de todos los límites de cantidad existentes que ha configurado. Puede añadir nuevos límites, editar los existentes o eliminarlos.

#### **Columnas de la tabla de listado:**
-   **ID:** Un identificador único para cada regla de límite de cantidad.
-   **Producto:** El nombre del producto al que se aplica el límite.
-   **Fecha desde:** La fecha y hora de inicio en que el límite de cantidad se activa.
-   **Fecha hasta:** La fecha y hora de finalización en que el límite de cantidad expira.
-   **Cantidad:** El número máximo de unidades del producto que se pueden comprar dentro del rango de fechas especificado.
-   **Activo:** Un interruptor (Sí/No) para habilitar o deshabilitar una regla de límite específica sin eliminarla.

#### **Añadir / Editar una regla de límite de cantidad:**
Cuando hace clic en "Añadir nuevo" o edita una regla existente, verá un formulario con los siguientes campos:

-   **Límite de cantidad de compra de producto por fecha:** Este es el título principal del formulario.
-   **ID Producto:**
    -   **Qué hace este ajuste:** Este campo le permite seleccionar el producto específico al que se aplicará este límite de cantidad. Normalmente utilizará una barra de búsqueda para encontrar el producto por nombre o ID.
    -   **Efecto de cambiar este ajuste:** Determina la cantidad de compra de qué producto será restringida por esta regla.
    -   **Valor recomendado:** Seleccione el producto exacto que desea limitar.
    -   **Escenario / ejemplo de comerciante:** Desea limitar las ventas de "Camiseta de Verano" a 50 unidades. Buscaría y seleccionaría "Camiseta de Verano" aquí.
-   **Fecha desde:**
    -   **Qué hace este ajuste:** Define la fecha y hora exactas en que esta regla de límite de cantidad se activa.
    -   **Efecto de cambiar este ajuste:** El límite solo se aplicará a las compras realizadas en o después de esta fecha/hora.
    -   **Valor recomendado:** Establezca la fecha y hora de inicio precisas para su promoción o restricción.
    -   **Escenario / ejemplo de comerciante:** Desea que el límite comience el 1 de agosto de 2024 a las 9:00 AM.
-   **Fecha hasta:**
    -   **Qué hace este ajuste:** Define la fecha y hora exactas en que esta regla de límite de cantidad expira.
    -   **Efecto de cambiar este ajuste:** Después de esta fecha/hora, el límite ya no se aplicará, y los clientes podrán comprar cualquier stock disponible.
    -   **Valor recomendado:** Establezca la fecha y hora de finalización precisas para su promoción o restricción.
    -   **Escenario / ejemplo de comerciante:** Desea que el límite termine el 7 de agosto de 2024 a las 5:00 PM.
-   **Cantidad:**
    -   **Qué hace este ajuste:** Especifica el número máximo de unidades del producto seleccionado que se pueden comprar dentro del rango "Fecha desde" y "Fecha hasta".
    -   **Efecto de cambiar este ajuste:** Este es el límite real aplicado. Si un cliente intenta añadir más de esta cantidad a su carrito dentro del rango de fechas activo, se le impedirá.
    -   **Valor recomendado:** La cantidad máxima específica que desea permitir.
    -   **Escenario / ejemplo de comerciante:** Desea limitar las compras a 5 unidades por cliente durante el período especificado. Introduciría "5" aquí.
-   **Activo (Interruptor On/Off):**
    -   **Qué hace este ajuste:** Alterna el estado activo de esta regla de límite de cantidad específica.
    -   **Efecto de cambiar este ajuste:**
        -   *On:* La regla está activa y aplicará el límite de cantidad durante su rango de fechas especificado.
        -   *Off:* La regla está inactiva y no aplicará ningún límite de cantidad, incluso si su rango de fechas es actual. Esto es útil para pausar temporalmente una regla sin eliminarla.
    -   **Valor recomendado:** "On" para reglas activas, "Off" para reglas que desea deshabilitar temporalmente.
    -   **Escenario / ejemplo de comerciante:** Ha configurado un límite para una venta de Black Friday, pero decide posponerla. En lugar de eliminar la regla, puede cambiarla a "Off" y luego a "On" cuando esté listo.
-   **Botón Guardar:**
    -   **Qué hace este ajuste:** Guarda todos los cambios que ha realizado en la regla de límite de cantidad.
    -   **Efecto de cambiar este ajuste:** Aplica la regla nueva o actualizada a la aplicación de cantidad de producto de su tienda.

**Efecto de los cambios:**
-   **Añadir una nueva regla:** Se creará un nuevo límite de cantidad y se activará (si se establece en "On") durante su rango de fechas especificado, restringiendo las compras del producto seleccionado.
-   **Modificar una regla existente:** Los cambios (por ejemplo, producto, fechas, cantidad, estado activo) actualizarán inmediatamente cómo se aplica el límite.
-   **Eliminar una regla:** El límite de cantidad se eliminará permanentemente, y no se aplicarán restricciones a ese producto para ese rango de fechas (a menos que existan otras reglas).

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**
1.  **Planifique sus promociones/restricciones:** Antes de configurar, decida qué productos necesitan límites, cuáles deben ser las cantidades máximas y las fechas y horas exactas de inicio/fin.
2.  **Navegue a "Límite de cantidad de compra de producto por fecha":** Vaya a **Catálogo > Límite de cantidad de compra de producto por fecha**.
3.  **Añada nuevas reglas:** Haga clic en "Añadir nuevo" para cada producto que desee limitar. Rellene cuidadosamente el Producto, Fecha desde, Fecha hasta, Cantidad y asegúrese de que "Activo" esté en "On".
4.  **Revise y ajuste:** Revise regularmente su lista de reglas para asegurarse de que sigan siendo relevantes y estén configuradas correctamente. Utilice el interruptor "Activo" para deshabilitar temporalmente las reglas si es necesario.
5.  **Supervise los comentarios de los clientes:** Preste atención a cualquier consulta de los clientes relacionada con los límites de cantidad para asegurarse de que las reglas sean claras y funcionen según lo previsto.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista                                       | Ajuste / Opción                     | Predeterminado / Recomendado | Propósito e Impacto
El módulo "Cantidad máxima de producto disponible para comprar por fecha" de MyPresta.eu es una herramienta potente para controlar la disponibilidad de productos. Le permite establecer cantidades máximas de compra específicas para un producto dentro de un rango de fecha y hora definido. Esto es crucial para gestionar el stock limitado, crear urgencia para promociones o gestionar la disponibilidad de productos especiales.

## 3. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL). Estas son comunes y suelen estar habilitadas por defecto en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 4. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 4.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración inicial que encuentra después de instalar el módulo o al hacer clic en "Configurar" desde el Gestor de módulos.

-   **Qué hace este ajuste:** Esta página suele contener un simple interruptor para habilitar o deshabilitar la funcionalidad general del módulo.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* El módulo comprobará y aplicará activamente los límites de cantidad de producto que defina.
    -   *Cuando está deshabilitado:* El módulo estará inactivo y no se aplicarán límites de cantidad, independientemente de las reglas que haya configurado.
-   **Valor recomendado:** "SÍ" (Habilitado) para asegurar que el módulo esté activo y aplicando sus reglas de cantidad.
-   **Escenario / ejemplo de comerciante:** Después de la instalación, debe asegurarse de que este ajuste esté habilitado para comenzar a usar las funciones del módulo. Si alguna vez necesita suspender temporalmente todos los límites de cantidad (por ejemplo, durante una ventana de mantenimiento del sitio), puede deshabilitarlo aquí.

### 4.2 Pantalla de administración dedicada: Límite de cantidad de compra de producto por fecha (Back Office > Catálogo > Límite de cantidad de compra de producto por fecha)
Este es el centro principal para crear, gestionar y revisar todos sus límites de cantidad de producto basados en fechas.

**Nombre de la pantalla y ubicación del menú:**
Puede acceder a esta pantalla navegando a **Catálogo > Límite de cantidad de compra de producto por fecha** en el menú de su Back Office de PrestaShop.

**Acciones y ajustes disponibles:**
Esta pantalla muestra una lista de todas las reglas de límite de cantidad existentes. Desde aquí, puede añadir nuevas reglas, editar las existentes o eliminarlas.

#### **Columnas de la tabla de listado:**
-   **ID:** Un identificador interno único para cada regla de límite de cantidad específica. Útil para referencia técnica.
-   **Producto:** El nombre del producto al que se aplica esta regla específica. Esto le ayuda a identificar rápidamente qué producto se está limitando.
-   **Fecha desde:** La fecha y hora exactas (por ejemplo, "2024-08-01 09:00:00") en que este límite de cantidad comienza a aplicarse.
-   **Fecha hasta:** La fecha y hora exactas (por ejemplo, "2024-08-07 17:00:00") en que este límite de cantidad deja de aplicarse.
-   **Cantidad:** El número máximo de unidades del producto especificado que un cliente puede comprar dentro del período "Fecha desde" y "Fecha hasta".
-   **Activo:** Un simple indicador "Sí" o "No" (a menudo un interruptor de palanca) que muestra si la regla está actualmente habilitada.

#### **Añadir / Editar una regla de límite de cantidad:**
Cuando hace clic en el botón "Añadir nuevo" o hace clic para editar una regla existente, aparecerá un formulario con los siguientes campos:

-   **Límite de cantidad de compra de producto por fecha:** Este es el título del formulario, que indica que está definiendo una nueva o editando una existente.
-   **ID Producto:**
    -   **Qué hace este ajuste:** Este es un campo de búsqueda donde escribe el nombre o ID del producto al que desea aplicar el límite. A medida que escribe, aparecerán sugerencias, lo que le permitirá seleccionar el producto correcto.
    -   **Efecto de cambiar este ajuste:** Vincula directamente esta regla de límite de cantidad a un producto específico de su catálogo.
    -   **Valor recomendado:** Seleccione siempre el producto exacto que desea limitar.
    -   **Escenario / ejemplo de comerciante:** Está realizando una oferta especial en "Granos de café orgánico". Escribiría "Granos de café orgánico" y lo seleccionaría del menú desplegable.
-   **Fecha desde:**
    -   **Qué hace este ajuste:** Le permite seleccionar la fecha y hora exactas del calendario en que debe comenzar esta restricción de cantidad. Normalmente incluye un selector de fecha y un selector de hora.
    -   **Efecto de cambiar este ajuste:** El módulo solo comenzará a aplicar el límite de cantidad para las compras realizadas en o después de esta fecha y hora específicas.
    -   **Valor recomendado:** Establezca esto al inicio exacto de su período promocional o cuando la restricción deba entrar en vigor.
    -   **Escenario / ejemplo de comerciante:** Desea que un límite comience al principio de un día hábil, por lo que lo establece en "2024-09-01 00:00:00".
-   **Fecha hasta:**
    -   **Qué hace este ajuste:** Le permite seleccionar la fecha y hora exactas del calendario en que debe finalizar esta restricción de cantidad. Al igual que "Fecha desde", incluye un selector de fecha y un selector de hora.
    -   **Efecto de cambiar este ajuste:** Después de esta fecha y hora específicas, el límite de cantidad definido en esta regla ya no estará activo, y los clientes podrán comprar cualquier stock disponible.
    -   **Valor recomendado:** Establezca esto al final exacto de su período promocional o cuando la restricción deba levantarse.
    -   **Escenario / ejemplo de comerciante:** Desea que el límite termine al cierre de un día hábil, por lo que lo establece en "2024-09-07 23:59:59".
-   **Cantidad:**
    -   **Qué hace este ajuste:** Este es un campo de entrada numérico donde especifica el número máximo de unidades del producto seleccionado que un solo cliente puede comprar dentro del rango definido "Fecha desde" y "Fecha hasta".
    -   **Efecto de cambiar este ajuste:** Este valor es el núcleo de la restricción. Si un cliente intenta añadir más de esta cantidad a su carrito (o ya tiene más en su carrito) durante el período activo, el módulo intervendrá.
    -   **Valor recomendado:** La cantidad máxima específica que desea permitir. Por ejemplo, "1" para un límite de uno por cliente, o "10" para un límite de compra a granel.
    -   **Escenario / ejemplo de comerciante:** Para asegurar una distribución justa de un artículo de edición limitada, establece la cantidad en "2" por cliente.
-   **Activo (Interruptor On/Off):**
    -   **Qué hace este ajuste:** Este es un interruptor de palanca (a menudo etiquetado como "On" y "Off") que controla si esta regla de límite de cantidad específica está actualmente activa y es aplicada por el módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *On:* La regla está activa y aplicará su límite de cantidad durante su rango de fechas especificado.
        -   *Off:* La regla está inactiva y no aplicará ningún límite de cantidad, incluso si su rango de fechas es actual. Esto es útil para preparar reglas con antelación o pausarlas temporalmente sin eliminarlas.
    -   **Valor recomendado:** "On" para las reglas que desea que estén activas, "Off" para las reglas que está preparando o ha suspendido temporalmente.
    -   **Escenario / ejemplo de comerciante:** Ha creado una regla para una venta de vacaciones, pero las vacaciones aún están a un mes. Puede establecerla en "Off" hasta que se acerque la fecha, luego cambiarla a "On" cuando esté listo.
-   **Botón Guardar:**
    -   **Qué hace este ajuste:** Confirma todos los cambios que ha realizado en el formulario en la base de datos.
    -   **Efecto de cambiar este ajuste:** La regla de límite de cantidad nueva o actualizada se aplicará inmediatamente a la aplicación de cantidad de producto de su tienda.

**Efecto de los cambios:**
-   **Añadir una nueva regla:** Se creará una nueva restricción. Si se marca como "Activa" y dentro de su rango de fechas, comenzará inmediatamente a limitar las compras para el producto especificado.
-   **Modificar una regla existente:** Cualquier cambio en el producto, las fechas, la cantidad o el estado activo se reflejará instantáneamente en cómo el módulo aplica los límites.
-   **Eliminar una regla:** El límite de cantidad se eliminará permanentemente, y el producto ya no estará sujeto a esa restricción específica para ese rango de fechas.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**
1.  **Identifique los productos para los límites:** Determine qué productos requieren restricciones de cantidad (por ejemplo, novedades, artículos en oferta, productos de alta demanda).
2.  **Defina los parámetros:** Para cada producto, decida la cantidad máxima y las fechas/horas exactas de inicio y fin de la restricción.
3.  **Cree reglas:** Navegue a **Catálogo > Límite de cantidad de compra de producto por fecha** y haga clic en "Añadir nuevo". Rellene todos los campos cuidadosamente, asegurándose de que las fechas y horas sean precisas. Establezca "Activo" en "On".
4.  **Revise y pruebe:** Después de crear las reglas, pruébelas en su front office (por ejemplo, intente añadir más de la cantidad permitida a su carrito) para asegurarse de que funcionan como se espera.
5.  **Supervise y ajuste:** Esté atento a sus ventas e inventario. Si se extiende una promoción o cambia el stock, actualice los campos "Fecha hasta" o "Cantidad" de sus reglas según sea necesario. Utilice el interruptor "Activo" para deshabilitar temporalmente las reglas sin eliminarlas si las circunstancias cambian.

### 4.3 Tabla de referencia rápida de configuración

| Pantalla / Vista                                       | Ajuste / Opción                     | Predeterminado / Recomendado | Propósito e Impacto
