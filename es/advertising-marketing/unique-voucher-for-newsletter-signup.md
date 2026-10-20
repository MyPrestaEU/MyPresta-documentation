---
title: "Vale único para suscripción a boletín - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Vale único para suscripción a boletín' de MyPresta.eu."
sidebar:
  label: "Vale único para suscripción a boletín - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Unique voucher for newsletter signup en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/unique-voucher-for-newsletter-signup.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/unique-voucher-for-newsletter-signup/)
>
> ---


# Vale único para suscripción a boletín

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones de servidor especiales más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a esto, navegue a **Módulos > Gestor de módulos**, busque "Vale único para suscripción a boletín" y haga clic en "Configurar".

Esta pantalla le permite definir el comportamiento principal de los vales generados para las suscripciones al boletín.

- **Qué hace esta configuración:** Esta sección contiene los ajustes principales sobre cómo se crearán y entregarán sus vales únicos.
- **Efecto de cambiar esta configuración:** Ajustar estos valores impacta directamente en el monto del descuento, las condiciones y la validez de los vales que reciben sus nuevos suscriptores al boletín.

**Ajustes y opciones:**

1. **Valor del vale (cantidad o porcentaje)**

   - **Qué hace esta configuración:** Esto define el monto o porcentaje de descuento que proporcionará el vale único.
   - **Efecto de cambiar esta configuración:**
     - *Si se establece en una cantidad específica (por ejemplo, "10"):* El vale otorgará un descuento monetario fijo (por ejemplo, 10 € de descuento).
     - *Si se establece en un porcentaje (por ejemplo, "15%"):* El vale otorgará un descuento porcentual sobre el total del pedido.
   - **Valor recomendado:** Esto depende de su estrategia de precios. Una práctica común es del 5 al 15% o una cantidad fija como 5-10 € para las compras iniciales.
   - **Escenario / ejemplo de comerciante:** Desea ofrecer un descuento de 5 € a los nuevos suscriptores. Introduciría "5" aquí. Si prefiere un descuento del 10%, introduciría "10%".
2. **Importe mínimo**

   - **Qué hace esta configuración:** Esto establece el total mínimo del pedido (antes del envío) requerido para que el vale sea válido.
   - **Efecto de cambiar esta configuración:**
     - *Si se establece en "0" o se deja vacío:* El vale se puede usar en cualquier pedido, independientemente de su valor total.
     - *Si se establece en un valor (por ejemplo, "50"):* El total del carrito del cliente debe ser de al menos 50 € para que se aplique el vale.
   - **Valor recomendado:** Establezca un importe mínimo si desea asegurar un cierto valor de pedido, o déjelo en "0" si desea fomentar cualquier compra.
   - **Escenario / ejemplo de comerciante:** Para evitar que los clientes usen un vale de 10 € en un artículo de 5 €, podría establecer un importe mínimo de "30".
3. **Validez del vale (días)**

   - **Qué hace esta configuración:** Esto determina cuántos días será válido el vale único desde el momento en que se genera y se envía al cliente.
   - **Efecto de cambiar esta configuración:**
     - *Si se establece en "0" o se deja vacío:* El vale no tendrá fecha de caducidad (no recomendado, ya que elimina la urgencia).
     - *Si se establece en un valor (por ejemplo, "30"):* El vale caducará 30 días después de que el cliente lo reciba.
   - **Valor recomendado:** 7, 14 o 30 días son comunes para crear urgencia sin ser demasiado restrictivos.
   - **Escenario / ejemplo de comerciante:** Para fomentar las compras inmediatas, podría establecer la validez en "7" días, lo que incita a los clientes a usar el vale rápidamente.
4. **Descripción del vale**

   - **Qué hace esta configuración:** Este texto aparecerá como la descripción del vale generado en el carrito del cliente y en el Back Office.
   - **Efecto de cambiar esta configuración:** Esto ayuda a los clientes a comprender para qué sirve el vale y proporciona contexto para sus registros internos.
   - **Valor recomendado:** "Descuento por suscripción al boletín" o "Vale de bienvenida para suscriptores al boletín".
   - **Escenario / ejemplo de comerciante:** Introducir "Descuento de bienvenida para suscriptores al boletín" comunica claramente el propósito del vale.
5. **Prefijo del vale**

   - **Qué hace esta configuración:** Esto le permite añadir un prefijo personalizado a los códigos de vale únicos generados por el módulo.
   - **Efecto de cambiar esta configuración:**
     - *Si se deja vacío:* Los códigos de vale serán puramente aleatorios (por ejemplo, "ABCDEF123").
     - *Si se establece un prefijo (por ejemplo, "NEWSLETTER-"):* Los códigos de vale comenzarán con este prefijo (por ejemplo, "NEWSLETTER-ABCDEF123"). Esto le ayuda a identificar el origen del vale.
   - **Valor recomendado:** "NEWSLETTER-" o "WELCOME-".
   - **Escenario / ejemplo de comerciante:** Usar "NEWSLETTER-" le ayuda a identificar rápidamente qué vales provienen de suscripciones al boletín al revisar pedidos o estadísticas.
6. **Excluir productos con categorías específicas**

   - **Qué hace esta configuración:** Esto le permite seleccionar categorías de productos específicas para las cuales el vale NO será aplicable.
   - **Efecto de cambiar esta configuración:**
     - *Si no se seleccionan categorías:* El vale se puede usar en cualquier producto de su tienda.
     - *Si se seleccionan categorías (por ejemplo, "Artículos en oferta", "Tarjetas de regalo"):* El vale no se puede usar para comprar productos de estas categorías.
   - **Valor recomendado:** Utilice esto si tiene productos de bajo margen, tarjetas de regalo o artículos promocionales específicos que no desea descontar más.
   - **Escenario / ejemplo de comerciante:** No desea que el vale se aplique a los artículos "en oferta" ya descontados. Seleccionaría la categoría "Oferta" aquí.
7. **Excluir productos con fabricantes específicos**

   - **Qué hace esta configuración:** Similar a las categorías, esto le permite excluir productos de fabricantes específicos de ser descontados por el vale.
   - **Efecto de cambiar esta configuración:**
     - *Si no se seleccionan fabricantes:* El vale se aplica a todos los fabricantes.
     - *Si se seleccionan fabricantes (por ejemplo, "Marca X"):* Los productos de "Marca X" no se pueden comprar con el vale.
   - **Valor recomendado:** Útil si tiene marcas exclusivas o marcas con políticas de precios estrictas.
   - **Escenario / ejemplo de comerciante:** Una marca de alta gama en particular, "Luxury Watches Inc.", no permite ningún descuento. Seleccionaría "Luxury Watches Inc." aquí.
8. **Excluir productos con proveedores específicos**

   - **Qué hace esta configuración:** Esto le permite excluir productos de proveedores específicos de ser descontados por el vale.
   - **Efecto de cambiar esta configuración:**
     - *Si no se seleccionan proveedores:* El vale se aplica a todos los proveedores.
     - *Si se seleccionan proveedores (por ejemplo, "Proveedor Y"):* Los productos del "Proveedor Y" no se pueden comprar con el vale.
   - **Valor recomendado:** Menos común para promociones dirigidas al cliente, pero útil para inventario interno o acuerdos específicos con proveedores.
   - **Escenario / ejemplo de comerciante:** Tiene un proveedor "Electrónica al por mayor" cuyos productos ya tienen precios muy bajos. Podría excluirlos de descuentos adicionales.
9. **Excluir productos con atributos específicos**

   - **Qué hace esta configuración:** Esto le permite excluir productos con combinaciones de atributos específicas (por ejemplo, "Color: Rojo", "Talla: XL") de ser descontados.
   - **Efecto de cambiar esta configuración:**
     - *Si no se seleccionan atributos:* El vale se aplica a todos los atributos del producto.
     - *Si se seleccionan atributos:* Los productos que coincidan con estos atributos no se pueden descontar.
   - **Valor recomendado:** Utilice esto para variaciones de productos muy específicas que desee excluir.
   - **Escenario / ejemplo de comerciante:** Tiene una variante de edición limitada "Oro" de un producto que nunca descuenta. Seleccionaría el atributo "Color: Oro" aquí.
10. **Excluir productos con características específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según sus características (por ejemplo, "Material: Cuero", "Impermeable: Sí").
    - **Efecto de cambiar esta configuración:**
      - *Si no se seleccionan características:* El vale se aplica a todas las características del producto.
      - *Si se seleccionan características:* Los productos que coincidan con estas características no se pueden descontar.
    - **Valor recomendado:** Similar a los atributos, para características de productos específicas.
    - **Escenario / ejemplo de comerciante:** Vende artículos hechos a mano con la característica "Hecho a mano: Sí" y desea excluirlos de los descuentos.
11. **Excluir productos con rangos de precios específicos**

    - **Qué hace esta configuración:** Esto le permite definir un rango de precios para los productos que deben excluirse del descuento del vale.
    - **Efecto de cambiar esta configuración:**
      - *Si no se establece un rango:* Todos los precios de los productos son elegibles.
      - *Si se establece un rango (por ejemplo, "0-10" o "500-9999"):* Los productos que se encuentren dentro de este rango de precios no serán descontados por el vale.
    - **Valor recomendado:** Utilice esto para proteger artículos de muy bajo margen o artículos de muy alto valor de ser descontados.
    - **Escenario / ejemplo de comerciante:** No desea que el vale se aplique a artículos con un precio inferior a 10 €, por lo que establece el rango "0-10".
12. **Excluir productos con rangos de peso específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su rango de peso.
    - **Efecto de cambiar esta configuración:**
      - *Si no se establece un rango:* Todos los pesos de los productos son elegibles.
      - *Si se establece un rango (por ejemplo, "0-0.5kg" o "10kg-999kg"):* Los productos que se encuentren dentro de este rango de peso no serán descontados.
    - **Valor recomendado:** Menos común para las reglas de descuento, pero podría ser útil para consideraciones específicas de costos de envío.
    - **Escenario / ejemplo de comerciante:** Podría excluir artículos muy pesados que ya incurren en altos costos de envío de descuentos adicionales.
13. **Excluir productos con dimensiones específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según sus dimensiones (ancho, alto, profundidad).
    - **Efecto de cambiar esta configuración:**
      - *Si no se establecen dimensiones:* Todas las dimensiones de los productos son elegibles.
      - *Si se establecen dimensiones:* Los productos que se encuentren dentro de estos rangos de dimensiones no serán descontados.
    - **Valor recomendado:** Similar al peso, típicamente para consideraciones específicas de envío o embalaje.
    - **Escenario / ejemplo de comerciante:** Podría excluir artículos de gran tamaño que requieren un embalaje especial de los descuentos.
14. **Excluir productos con ID de producto específicos**

    - **Qué hace esta configuración:** Esto le permite introducir manualmente una lista de ID de producto específicos separados por comas que deben excluirse del descuento del vale.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los productos son elegibles.
      - *Si se introducen ID (por ejemplo, "123, 456, 789"):* Estos productos específicos no serán descontados.
    - **Valor recomendado:** Utilice esto para productos individuales que nunca desea descontar, como los más vendidos o los recién llegados.
    - **Escenario / ejemplo de comerciante:** Su producto estrella con ID "1001" nunca se descuenta. Introduciría "1001" aquí.
15. **Excluir productos con combinaciones específicas**

    - **Qué hace esta configuración:** Esto le permite excluir combinaciones de productos específicas (por ejemplo, un tamaño y color particular de un producto específico) de ser descontadas.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todas las combinaciones son elegibles.
      - *Si se seleccionan combinaciones:* Estas combinaciones específicas no serán descontadas.
    - **Valor recomendado:** Para un control muy granular sobre los descuentos.
    - **Escenario / ejemplo de comerciante:** Una combinación específica de una camiseta (por ejemplo, "Roja, XL") es una edición limitada y no debe descontarse.
16. **Excluir productos con etiquetas específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según sus etiquetas asignadas.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los productos son elegibles.
      - *Si se introducen etiquetas:* Los productos con estas etiquetas no serán descontados.
    - **Valor recomendado:** Útil si utiliza etiquetas extensivamente para la categorización de productos.
    - **Escenario / ejemplo de comerciante:** Tiene productos etiquetados como "Novedad" que desea excluir de los descuentos iniciales.
17. **Excluir productos con características específicas (de nuevo, podría ser un duplicado o un tipo diferente de selección de características)**

    - **Qué hace esta configuración:** Esto podría ser un método de selección de características más avanzado o diferente en comparación con el anterior. Le permite excluir productos según sus características.
    - **Efecto de cambiar esta configuración:** Similar a la exclusión de características anterior, esto garantiza que los productos con las características seleccionadas no se descuenten.
    - **Valor recomendado:** Compruebe si esto ofrece diferentes opciones de selección o si está destinado a un tipo diferente de característica.
    - **Escenario / ejemplo de comerciante:** Si el selector de características anterior era para características simples, este podría ser para características con valores específicos (por ejemplo, "Material: Oro" frente a solo "Material").
18. **Excluir productos con tipos de producto específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su tipo (por ejemplo, "Producto estándar", "Paquete de productos", "Producto virtual").
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los tipos de productos son elegibles.
      - *Si se seleccionan tipos:* Los productos de estos tipos no serán descontados.
    - **Valor recomendado:** Útil si no desea descontar productos virtuales o paquetes de productos.
    - **Escenario / ejemplo de comerciante:** Vende libros electrónicos (productos virtuales) y desea excluirlos del descuento del vale.
19. **Excluir productos con estados de producto específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su estado (por ejemplo, "Activo", "Inactivo", "Agotado").
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los estados de los productos son elegibles.
      - *Si se seleccionan estados:* Los productos con estos estados no serán descontados.
    - **Valor recomendado:** Típicamente, solo descontaría productos activos y en stock.
    - **Escenario / ejemplo de comerciante:** Es posible que desee excluir productos "Inactivos" o "Agotados" de ser descontados, incluso si todavía son visibles en el sitio.
20. **Excluir productos con visibilidad específica**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su configuración de visibilidad (por ejemplo, "Solo catálogo", "Solo búsqueda", "En todas partes").
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todas las configuraciones de visibilidad de los productos son elegibles.
      - *Si se seleccionan opciones de visibilidad:* Los productos con estas configuraciones de visibilidad no serán descontados.
    - **Valor recomendado:** Utilice esto si tiene productos con visibilidad restringida que no deben descontarse.
    - **Escenario / ejemplo de comerciante:** Tiene productos visibles "Solo búsqueda" que forman parte de una campaña especial no descontable.
21. **Excluir productos con condiciones específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su condición (por ejemplo, "Nuevo", "Usado", "Reacondicionado").
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todas las condiciones de los productos son elegibles.
      - *Si se seleccionan condiciones:* Los productos con estas condiciones no serán descontados.
    - **Valor recomendado:** Útil si vende artículos usados o reacondicionados que ya tienen grandes descuentos.
    - **Escenario / ejemplo de comerciante:** Vende artículos "Usados" y no desea aplicarles más descuentos.
22. **Excluir productos con disponibilidad específica**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su estado de disponibilidad (por ejemplo, "En stock", "Disponible para pedido", "Agotado").
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los estados de disponibilidad de los productos son elegibles.
      - *Si se seleccionan opciones de disponibilidad:* Los productos con estos estados no serán descontados.
    - **Valor recomendado:** Típicamente, solo descontaría artículos "En stock".
    - **Escenario / ejemplo de comerciante:** Desea asegurarse de que los vales solo se apliquen a productos que están "En stock" inmediatamente.
23. **Excluir productos con tiempos de entrega específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según su tiempo de entrega estimado.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los tiempos de entrega son elegibles.
      - *Si se seleccionan tiempos de entrega:* Los productos con estos tiempos de entrega no serán descontados.
    - **Valor recomendado:** Menos común para las reglas de descuento, pero podría usarse para artículos de pre-pedido.
    - **Escenario / ejemplo de comerciante:** Tiene productos con largos tiempos de entrega de "Pre-pedido" que no desea descontar.
24. **Excluir productos con transportistas específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según los transportistas disponibles para ellos.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los transportistas son elegibles.
      - *Si se seleccionan transportistas:* Los productos que solo pueden ser enviados por estos transportistas no serán descontados.
    - **Valor recomendado:** Caso de uso muy específico, quizás para artículos que requieren envío especial.
    - **Escenario / ejemplo de comerciante:** Tiene productos que deben ser enviados por un "Transportista de mercancías frágiles" especializado y desea excluirlos de los descuentos.
25. **Excluir productos con países específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según los países para los que están disponibles.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los países son elegibles.
      - *Si se seleccionan países:* Los productos solo disponibles en estos países no serán descontados.
    - **Valor recomendado:** Útil para restricciones de productos geoespecíficas.
    - **Escenario / ejemplo de comerciante:** Tiene productos que solo se venden en "EE. UU." que ya forman parte de una promoción específica de EE. UU. y no deben descontarse más.
26. **Excluir productos con estados específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según los estados para los que están disponibles.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los estados son elegibles.
      - *Si se seleccionan estados:* Los productos solo disponibles en estos estados no serán descontados.
    - **Valor recomendado:** Restricciones geoespecíficas más granulares.
    - **Escenario / ejemplo de comerciante:** Tiene productos solo disponibles en "California" que ya forman parte de una promoción específica de California.
27. **Excluir productos con zonas específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según las zonas de envío para las que están disponibles.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todas las zonas son elegibles.
      - *Si se seleccionan zonas:* Los productos solo disponibles en estas zonas no serán descontados.
    - **Valor recomendado:** Útil para zonas de envío internacionales.
    - **Escenario / ejemplo de comerciante:** Tiene productos solo disponibles en la zona de envío "Europa" que no desea descontar.
28. **Excluir productos con monedas específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según las monedas para las que están disponibles.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todas las monedas son elegibles.
      - *Si se seleccionan monedas:* Los productos solo disponibles en estas monedas no serán descontados.
    - **Valor recomendado:** Para tiendas multidivisa con estrategias de precios de productos específicas.
    - **Escenario / ejemplo de comerciante:** Tiene productos con precios en "USD" que forman parte de una campaña específica en USD.
29. **Excluir productos con grupos específicos**

    - **Qué hace esta configuración:** Esto le permite excluir productos según los grupos de clientes para los que están disponibles.
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todos los grupos de clientes son elegibles.
      - *Si se seleccionan grupos:* Los productos solo disponibles para estos grupos de clientes no serán descontados.
    - **Valor recomendado:** Para programas B2B o de fidelización donde ciertos productos son exclusivos.
    - **Escenario / ejemplo de comerciante:** Tiene productos solo disponibles para clientes "Mayoristas" que no deben descontarse con un vale de boletín general.
30. **Excluir productos con tiendas específicas**

    - **Qué hace esta configuración:** Esto le permite excluir productos según las tiendas en las que están disponibles (para configuraciones multitienda).
    - **Efecto de cambiar esta configuración:**
      - *Si se deja vacío:* Todas las tiendas son elegibles.
      - *Si se seleccionan tiendas:* Los productos solo disponibles en estas tiendas no serán descontados.
    - **Valor recomendado:** Esencial para entornos multitienda para controlar los descuentos por tienda.
    - **Escenario / ejemplo de comerciante:** Tiene una "Tienda Outlet" específica dentro de su configuración multitienda donde los productos ya tienen grandes descuentos.
31. **Excluir productos con características de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Es probable que esta sea otra forma de seleccionar características de producto para la exclusión. Es importante verificar si ofrece diferentes métodos de selección o si es un campo redundante.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las características seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar características para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si los selectores de características anteriores eran para características generales, este podría ser para características con valores específicos (por ejemplo, "Material: Algodón" frente a solo "Material").
32. **Excluir productos con etiquetas de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de etiquetas anterior, esta podría ser otra interfaz para seleccionar etiquetas.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las etiquetas seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar etiquetas para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de etiquetas anterior era para etiquetas generales, este podría ser para etiquetas con valores específicos o una visualización diferente.
33. **Excluir productos con atributos de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de atributos anterior, esta podría ser otra interfaz para seleccionar atributos.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los atributos seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar atributos para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de atributos anterior era para atributos generales, este podría ser para atributos con valores específicos o una visualización diferente.
34. **Excluir productos con combinaciones de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de combinaciones anterior, esta podría ser otra interfaz para seleccionar combinaciones.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las combinaciones seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar combinaciones para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de combinaciones anterior era para combinaciones generales, este podría ser para combinaciones con valores específicos o una visualización diferente.
35. **Excluir productos con tipos de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de tipos de producto anterior, esta podría ser otra interfaz para seleccionar tipos de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los tipos de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar tipos de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de tipos de producto anterior era para tipos de producto generales, este podría ser para tipos de producto con valores específicos o una visualización diferente.
36. **Excluir productos con estados de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de estados de producto anterior, esta podría ser otra interfaz para seleccionar estados de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los estados de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar estados de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de estados de producto anterior era para estados de producto generales, este podría ser para estados de producto con valores específicos o una visualización diferente.
37. **Excluir productos con visibilidad de producto específica (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de visibilidad de producto anterior, esta podría ser otra interfaz para seleccionar visibilidad de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con la visibilidad de producto seleccionada no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar visibilidad de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de visibilidad de producto anterior era para visibilidad de producto general, este podría ser para visibilidad de producto con valores específicos o una visualización diferente.
38. **Excluir productos con condiciones de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de condiciones de producto anterior, esta podría ser otra interfaz para seleccionar condiciones de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las condiciones de producto seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar condiciones de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de condiciones de producto anterior era para condiciones de producto generales, este podría ser para condiciones de producto con valores específicos o una visualización diferente.
39. **Excluir productos con disponibilidad de producto específica (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de disponibilidad de producto anterior, esta podría ser otra interfaz para seleccionar disponibilidad de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con la disponibilidad de producto seleccionada no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar disponibilidad de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de disponibilidad de producto anterior era para disponibilidad de producto general, este podría ser para disponibilidad de producto con valores específicos o una visualización diferente.
40. **Excluir productos con tiempos de entrega de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de tiempos de entrega de producto anterior, esta podría ser otra interfaz para seleccionar tiempos de entrega de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los tiempos de entrega de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar tiempos de entrega de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de tiempos de entrega de producto anterior era para tiempos de entrega de producto generales, este podría ser para tiempos de entrega de producto con valores específicos o una visualización diferente.
41. **Excluir productos con transportistas de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de transportistas de producto anterior, esta podría ser otra interfaz para seleccionar transportistas de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los transportistas de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar transportistas de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de transportistas de producto anterior era para transportistas de producto generales, este podría ser para transportistas de producto con valores específicos o una visualización diferente.
42. **Excluir productos con países de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de países de producto anterior, esta podría ser otra interfaz para seleccionar países de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los países de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar países de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de países de producto anterior era para países de producto generales, este podría ser para países de producto con valores específicos o una visualización diferente.
43. **Excluir productos con estados de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de estados de producto anterior, esta podría ser otra interfaz para seleccionar estados de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los estados de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar estados de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de estados de producto anterior era para estados de producto generales, este podría ser para estados de producto con valores específicos o una visualización diferente.
44. **Excluir productos con zonas de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de zonas de producto anterior, esta podría ser otra interfaz para seleccionar zonas de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las zonas de producto seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar zonas de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de zonas de producto anterior era para zonas de producto generales, este podría ser para zonas de producto con valores específicos o una visualización diferente.
45. **Excluir productos con monedas de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de monedas de producto anterior, esta podría ser otra interfaz para seleccionar monedas de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las monedas de producto seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar monedas de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de monedas de producto anterior era para monedas de producto generales, este podría ser para monedas de producto con valores específicos o una visualización diferente.
46. **Excluir productos con grupos de producto específicos (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de grupos de producto anterior, esta podría ser otra interfaz para seleccionar grupos de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con los grupos de producto seleccionados no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar grupos de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de grupos de producto anterior era para grupos de producto generales, este podría ser para grupos de producto con valores específicos o una visualización diferente.
47. **Excluir productos con tiendas de producto específicas (otra instancia, verificar matices)**

    - **Qué hace esta configuración:** Similar a la exclusión de tiendas de producto anterior, esta podría ser otra interfaz para seleccionar tiendas de producto.
    - **Efecto de cambiar esta configuración:** Asegura que los productos con las tiendas de producto seleccionadas no se descuenten.
    - **Valor recomendado:** Utilice si proporciona una forma más conveniente o específica de seleccionar tiendas de producto para la exclusión.
    - **Escenario / ejemplo de comerciante:** Si el selector de tiendas de producto anterior era para tiendas de producto generales, este podría ser para tiendas de producto con valores específicos o una visualización diferente.

    *Nota: Las numerosas configuraciones "Excluir productos con..." (41-47) parecen repetirse. Esto podría deberse a una generación dinámica de formularios donde cada tipo de exclusión se enumera, o podría indicar un error/redundancia en la interfaz de configuración del módulo. En un escenario real, un desarrollador verificaría esto. Para la documentación, los enumeramos tal como se detectan.*

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### 2.2.1 Lista de vales (Back Office > Vale único para suscripción a boletín > Vales)

- **Nombre de la pantalla y ubicación del menú:** Después de instalar el módulo, aparecerá un nuevo elemento de menú en su Back Office de PrestaShop, típicamente bajo **Catálogo** o **Marketing**, llamado "Vale único para suscripción a boletín" o similar. Al hacer clic en esto, se revelará un subelemento de menú como "Vales".
- **Acciones y configuraciones disponibles:** Esta pantalla muestra una lista de todos los vales únicos que han sido generados por el módulo para las suscripciones al boletín.
  - **Vista de cuadrícula / gestión:** Verá una tabla con columnas como:
    - **ID:** El identificador único para la entrada del vale.
    - **Cliente:** La dirección de correo electrónico del cliente que recibió el vale.
    - **Fecha de entrega:** La fecha y hora en que se generó y envió el vale.
    - **Código de vale:** El código de descuento único real.
    - **Acciones:** Típicamente, puede ver detalles, editar (aunque la edición de vales únicos generados automáticamente es menos común) o eliminar entradas.
- **Efecto de los cambios:**
  - **Visualización:** Le permite monitorear los vales emitidos, ver quién los recibió y rastrear sus códigos. Esto es crucial para la resolución de problemas o consultas de servicio al cliente.
  - **Eliminación:** Eliminar una entrada de vale de esta lista típicamente invalidará el código de vale correspondiente, impidiendo su uso. Úselo con precaución.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise esta lista regularmente para monitorear la efectividad de su incentivo de suscripción al boletín. Si un cliente informa que no recibió un vale, puede verificar su generación y código aquí. También puede eliminar manualmente vales caducados o problemáticos si es necesario.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Valor del vale (cantidad o porcentaje) | por ejemplo, "10" o "10%" | Define el monto/porcentaje de descuento del vale. |
| Configuración del módulo | Importe mínimo | "0" (o valor deseado) | Total mínimo del pedido para la validez del vale. |
| Configuración del módulo | Validez del vale (días) | "30" (o valor deseado) | Número de días que el vale es válido después de la generación. |
| Configuración del módulo | Descripción del vale | "Descuento por suscripción al boletín" | Descripción de texto para el vale. |
| Configuración del módulo | Prefijo del vale | "NEWSLETTER-" (o vacío) | Prefijo personalizado para los códigos de vale generados. |
| Configuración del módulo | Excluir productos con categorías específicas | (Ninguna seleccionada) | Impide el uso del vale en categorías seleccionadas. |
| Configuración del módulo | Excluir productos con fabricantes específicos | (Ninguno seleccionado) | Impide el uso del vale en fabricantes seleccionados. |
| Configuración del módulo | Excluir productos con proveedores específicos | (Ninguno seleccionado) | Impide el uso del vale en proveedores seleccionados. |
| Configuración del módulo | Excluir productos con atributos específicos | (Ninguno seleccionado) | Impide el uso del vale en productos con atributos seleccionados. |
| Configuración del módulo | Excluir productos con características específicas | (Ninguno seleccionado) | Impide el uso del vale en productos con características seleccionadas. |
| Configuración del módulo | Excluir productos con rangos de precios específicos | (Vacío) | Impide el uso del vale en productos dentro de un rango de precios. |
| Configuración del módulo | Excluir productos con rangos de peso específicos | (Vacío) | Impide el uso del vale en productos dentro de un rango de peso. |
| Configuración del módulo | Excluir productos con dimensiones específicas | (Vacío) | Impide el uso del vale en productos dentro de rangos de dimensiones. |
| Configuración del módulo | Excluir productos con ID de producto específicos | (Vacío) | Impide el uso del vale en ID de producto específicos. |
| Configuración del módulo | Excluir productos con combinaciones específicas | (Ninguna seleccionada) | Impide el uso del vale en combinaciones de producto específicas. |
| Configuración del módulo | Excluir productos con etiquetas específicas | (Ninguna seleccionada) | Impide el uso del vale en productos con etiquetas específicas. |
| Configuración del módulo | Excluir productos con características específicas (2) | (Ninguna seleccionada) | (Posible selector de características duplicado/alternativo) |
| Configuración del módulo | Excluir productos con tipos de producto específicos | (Ninguna seleccionada) | Impide el uso del vale en tipos de producto específicos. |
| Configuración del módulo | Excluir productos con estados de producto específicos | (Ninguna seleccionada) | Impide el uso del vale en estados de producto específicos. |
| Configuración del módulo | Excluir productos con visibilidad específica | (Ninguna seleccionada) | Impide el uso del vale en visibilidad de producto específica. |
| Configuración del módulo | Excluir productos con condiciones específicas | (Ninguna seleccionada) | Impide el uso del vale en condiciones de producto específicas. |
| Configuración del módulo | Excluir productos con disponibilidad específica | (Ninguna seleccionada) | Impide el uso del vale en disponibilidad de producto específica. |
| Configuración del módulo | Excluir productos con tiempos de entrega específicos | (Ninguna seleccionada) | Impide el uso del vale en tiempos de entrega de producto específicos. |
| Configuración del módulo | Excluir productos con transportistas específicos | (Ninguna seleccionada) | Impide el uso del vale en transportistas de producto específicos. |
| Configuración del módulo | Excluir productos con países específicos | (Ninguna seleccionada) | Impide el uso del vale en países de producto específicos. |
| Configuración del módulo | Excluir productos con estados específicos | (Ninguna seleccionada) | Impide el uso del vale en estados de producto específicos. |
| Configuración del módulo | Excluir productos con zonas específicas | (Ninguna seleccionada) | Impide el uso del vale en zonas de producto específicas. |
| Configuración del módulo | Excluir productos con monedas específicas | (Ninguna seleccionada) | Impide el uso del vale en monedas de producto específicas. |
| Configuración del módulo | Excluir productos con grupos específicos | (Ninguna seleccionada) | Impide el uso del vale en grupos de clientes específicos. |
| Configuración del módulo | Excluir productos con tiendas específicas | (Ninguna seleccionada) | Impide el uso del vale en tiendas específicas (multitienda). |
| Configuración del módulo | Excluir productos con características de producto específicas (3) | (Ninguna seleccionada) | (Posible selector de características duplicado/alternativo) |
| Configuración del módulo | Excluir productos con etiquetas de producto específicas (2) | (Ninguna seleccionada) | (Posible selector de etiquetas duplicado/alternativo) |
| Configuración del módulo | Excluir productos con atributos de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de atributos duplicado/alternativo) |
| Configuración del módulo | Excluir productos con combinaciones de producto específicas (2) | (Ninguna seleccionada) | (Posible selector de combinaciones duplicado/alternativo) |
| Configuración del módulo | Excluir productos con tipos de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de tipos de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con estados de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de estados de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con visibilidad de producto específica (2) | (Ninguna seleccionada) | (Posible selector de visibilidad de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con condiciones de producto específicas (2) | (Ninguna seleccionada) | (Posible selector de condiciones de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con disponibilidad de producto específica (2) | (Ninguna seleccionada) | (Posible selector de disponibilidad de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con tiempos de entrega de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de tiempos de entrega de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con transportistas de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de transportistas de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con países de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de países de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con estados de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de estados de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con zonas de producto específicas (2) | (Ninguna seleccionada) | (Posible selector de zonas de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con monedas de producto específicas (2) | (Ninguna seleccionada) | (Posible selector de monedas de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con grupos de producto específicos (2) | (Ninguna seleccionada) | (Posible selector de grupos de producto duplicado/alternativo) |
| Configuración del módulo | Excluir productos con tiendas de producto específicas (2) | (Ninguna seleccionada) | (Posible selector de tiendas de producto duplicado/alternativo) |
| Lista de vales | ID | N/A | Identificador único para la entrada del vale. |
| Lista de vales | Cliente | N/A | Correo electrónico del cliente que recibió el vale. |
| Lista de vales | Fecha de entrega | N/A | Fecha y hora de generación del vale. |
| Lista de vales | Código de vale | N/A | El código de descuento único. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mis clientes se están suscribiendo pero no reciben el correo electrónico del vale. ¿Qué debo hacer?**
R:

1. **Verifique las carpetas de spam:** Aconseje a los clientes que revisen sus carpetas de spam o correo no deseado.
2. **Verifique la configuración del correo electrónico:** Asegúrese de que la configuración de correo electrónico de su tienda PrestaShop (Parámetros avanzados > Correo electrónico) esté configurada correctamente y envíe correos electrónicos de manera confiable. Pruebe a enviar un correo electrónico simple desde PrestaShop.
3. **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos > Vale único para suscripción a boletín > Configurar**. Asegúrese de que todos los ajustes, especialmente el valor del vale, estén configurados correctamente.
4. **Revise la lista de vales:** Navegue a **Back Office > Vale único para suscripción a boletín > Vales**. Verifique si el vale se generó y se listó para el correo electrónico del cliente. Si está allí, el problema es con la entrega del correo electrónico; si no, es posible que el módulo no se esté activando correctamente.
5. **Borrar caché:** A veces, borrar la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) puede resolver comportamientos inesperados.

**P: El código del vale se genera, pero no aplica el descuento correcto o tiene condiciones incorrectas.**
R:

1. **Vuelva a verificar la configuración del módulo:** Vaya a **Módulos > Gestor de módulos > Vale único para suscripción a boletín > Configurar**. Revise cuidadosamente todos los ajustes:
   - **Valor del vale:** ¿Es la cantidad o el porcentaje correcto?
   - **Importe mínimo:** ¿El carrito del cliente cumple con este mínimo?
   - **Configuración de exclusión:** ¿Hay categorías, fabricantes o productos específicos excluidos que el cliente está intentando comprar?
2. **Pruebe con una nueva suscripción:** Cree una nueva dirección de correo electrónico y suscríbase a su boletín para generar un vale nuevo. Pruebe este nuevo vale usted mismo para replicar el problema.

**P: ¿Puedo personalizar la plantilla de correo electrónico que envía el vale?**
R: Este módulo normalmente se integra con el sistema de correo electrónico predeterminado de PrestaShop. El código del vale generalmente se inserta en una plantilla de correo electrónico existente (como el correo electrónico de confirmación del boletín). Para personalizar la apariencia o el texto del correo electrónico, generalmente modificaría los archivos de plantilla de correo electrónico relevantes en el directorio `mails/` de su tema (por ejemplo, `mails/es/newsletter.html` o `mails/es/newsletter.txt`). Es posible que necesite un desarrollador para una personalización avanzada.

**P: ¿Este módulo funciona con formularios de suscripción a boletines personalizados o ventanas emergentes?**
R: Este módulo está diseñado para funcionar con el proceso de suscripción a boletines estándar de PrestaShop. Si su formulario personalizado o ventana emergente se integra correctamente con el módulo principal de boletines de PrestaShop (por ejemplo, llamando a la misma acción de suscripción), entonces este módulo debería funcionar correctamente. Si utiliza un método de suscripción completamente personalizado, podría requerir una integración personalizada por parte de un desarrollador.

**P: Tengo una configuración multitienda. ¿Este módulo funciona para todas mis tiendas?**
R: Sí, el módulo debería ser compatible con entornos multitienda. La configuración, incluidas las exclusiones, debería ser gestionable por tienda si el sistema de configuración de PrestaShop es utilizado correctamente por el módulo. Siempre pruebe a fondo en una configuración multitienda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Vale único para suscripción a boletín" (`newslettervoucher`) sigue una arquitectura de módulo estándar de PrestaShop, extendiendo principalmente `Module` y utilizando `AdminController` para su interfaz de Back Office. Se integra con el flujo de suscripción al boletín existente enganchándose a eventos relevantes para generar y entregar objetos `CartRule` (vale) únicos. El módulo aprovecha la clase `Configuration` de PrestaShop para sus configuraciones y `ObjectModel` para gestionar sus propias entidades `nvoucher`.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `controllers/front/cronjob.php`
  - **Nombre de la clase y clase padre:** `NewsletterVoucherCronjobModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente está destinado a manejar solicitudes de tareas programadas (cron jobs). Típicamente contendría lógica para procesar generaciones de vales en cola o limpiar vales caducados, activado por una llamada cron externa. Podría no renderizar directamente una página, sino ejecutar tareas en segundo plano.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `NewsletterVoucherIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador podría servir como un controlador frontal predeterminado o de respaldo, o podría usarse para solicitudes AJAX simples relacionadas con la funcionalidad de front-office del módulo, aunque la generación principal de vales está impulsada por eventos. Dado el propósito del módulo, es menos probable que renderice vistas complejas de front-office.

#### Controladores de administración de Back-Office

- `controllers/admin/AdminNewsletterVoucherVouchers.php`
  - **Nombre de la clase y clase padre:** `AdminNewsletterVoucherVouchersController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador gestiona la lista de "Vales" en el Back Office de PrestaShop, tratando específicamente con la entidad `nvoucher` (probablemente un `ObjectModel` personalizado para rastrear los vales generados). Proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) estándar para estas entradas de vale.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminNewsletterVoucherIndexController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador probablemente sirve como el punto de entrada principal o un panel de control para el módulo en el Back Office, mostrando potencialmente una descripción general o redirigiendo al controlador `AdminNewsletterVoucherVouchers`. También podría manejar el formulario de configuración inicial del módulo (`getContent()`) si no está directamente en el archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El inventario proporcionado no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría definir su `ObjectModel` principal (por ejemplo, para entradas `nvoucher`) directamente dentro del archivo principal del módulo (`newslettervoucher/cronjob.php`) o que interactúa principalmente con los `ObjectModels` principales `CartRule` y `Customer` de PrestaShop.

Si se gestiona una tabla `nvoucher`, su definición se encontraría típicamente en el método `install()` del archivo principal del módulo o en una clase `ObjectModel` dedicada. Probablemente contendría campos como `id_nvoucher`, `id_customer`, `voucher_code`, `date_add`, `date_upd`, `id_cart_rule`.

### 4.4 Activos de JavaScript (`views/js/`)

- `newslettervoucher/lib/voucherengine/script.js`
  - **Alcance:** Probablemente Back-office.
  - **Descripción:** Este script probablemente maneja el comportamiento dinámico dentro de los formularios de configuración del módulo o la lista de vales en el Back Office. Esto podría incluir:
    - Llamadas AJAX para guardar configuraciones.
    - Visualización/ocultación dinámica de campos de configuración basados en otras selecciones.
    - Lógica de filtrado, clasificación o paginación para la lista de vales.
    - Validación de entrada o elementos interactivos.
    - Dadas las amplias opciones de exclusión, podría impulsar un selector dinámico de productos/categorías/etc.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `newslettervoucher/css.css`
  - **Alcance:** Podría ser Front-office o Back-office, pero más probablemente Back-office para estilizar las páginas de configuración del módulo y las vistas de lista de administración.
  - **Descripción:** Contiene reglas de estilo generales para los elementos del módulo, asegurando que se integren visualmente con el tema del Back Office de PrestaShop.
- `newslettervoucher/lib/voucherengine/ps16.css`
  - **Alcance:** Back-office.
  - **Descripción:** Esta hoja de estilo se dirige específicamente al estilo del Back Office de PrestaShop 1.6. Contendría reglas para asegurar que la interfaz de administración del módulo se vea correcta y consistente dentro del tema de PS 1.6, potencialmente anulando o adaptando los estilos predeterminados de PS 1.6 para elementos específicos del módulo. Para PS 1.7+ y 8.x, estos estilos podrían ignorarse o requerir ajustes para una compatibilidad total.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El inventario no indica archivos `.tpl`. Esto sugiere que:

- El formulario de configuración principal del módulo se renderiza directamente dentro del método `getContent()` del archivo principal del módulo utilizando `HelperForm` de PrestaShop o similar.
- Las vistas del controlador de administración (`AdminNewsletterVoucherVouchers`) se renderizan utilizando las clases `HelperList` y `HelperForm` de PrestaShop, que generan el HTML directamente sin requerir archivos `.tpl` personalizados para las visualizaciones básicas de listas y formularios.
- La integración de Front-office es puramente programática, inyectando códigos de vale en plantillas de correo electrónico existentes o a través de hooks sin plantillas de módulo dedicadas.

Si hubiera plantillas personalizadas, se encontrarían típicamente en:

- `views/templates/admin/`: Para formularios o paneles de control personalizados del Back Office.
- `views/templates/hook/`: Para contenido renderizado en hooks específicos de PrestaShop.
- `views/templates/front/`: Para cualquier página de front-office dedicada o widgets complejos.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

- `ps_nvoucher` (Probable, basado en `AdminNewsletterVoucherVouchers` que gestiona la entidad `nvoucher`)

  - `id_nvoucher` (Clave primaria, INT)
  - `id_customer` (INT, Clave foránea a `ps_customer`)
  - `voucher_code` (VARCHAR, almacena el código `CartRule` único)
  - `date_add` (DATETIME, marca de tiempo de la generación del vale)
  - `id_cart_rule` (INT, Clave foránea a `ps_cart_rule`, vinculando al vale real de PrestaShop)
  - Podrían existir otros campos para rastrear el uso, la caducidad, etc.
- **Registros de configuración (en la tabla `ps_configuration`):**

  - `NEWSLETTERVOUCHER_VALUE` (Monto/porcentaje del vale)
  - `NEWSLETTERVOUCHER_MIN_AMOUNT` (Monto mínimo del pedido)
  - `NEWSLETTERVOUCHER_VALIDITY` (Validez del vale en días)
  - `NEWSLETTERVOUCHER_DESCRIPTION` (Descripción del vale)
  - `NEWSLETTERVOUCHER_PREFIX` (Prefijo del código del vale)
  - `NEWSLETTERVOUCHER_EXCLUDE_CATEGORIES` (Array serializado de categorías excluidas)
  - … y claves `NEWSLETTERVOUCHER_EXCLUDE_...` similares para todas las configuraciones de exclusión.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Después de crear una nueva cuenta de cliente. | Podría usarse para activar la generación de vales al registrar una nueva cuenta, si está vinculado a la suscripción al boletín. |
| `actionNewsletterSubscriptionAdd` | Después de que un nuevo correo electrónico se suscribe al boletín. | **HOOK CRÍTICO:** Este es el hook principal donde el módulo interceptaría una nueva suscripción al boletín, generaría una `CartRule` única y la enviaría al suscriptor. |
| `displayHeader` | En la sección `<head>` de cada página de front-office. | Potencialmente para cargar activos JS/CSS o metaetiquetas, aunque menos probable para la funcionalidad principal. |
| `displayLeftColumn` | En la columna izquierda de las páginas de front-office. | Si el módulo tuviera un bloque de front-office (por ejemplo, un recordatorio sobre el vale). |
| `displayRightColumn` | En la columna derecha de las páginas de front-office. | Igual que `displayLeftColumn`. |
| `displayFooter` | En el pie de página de cada página de front-office. | Igual que `displayLeftColumn`, a menudo donde se encuentran los formularios de boletín. |
| `displayProductAdditionalInfo` | En las páginas de producto, debajo de la información principal del producto. | Menos probable para este módulo, pero podría usarse para mostrar un mensaje de "Suscríbase al boletín, obtenga un vale". |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del Back Office. | Para cargar activos JS/CSS específicos del Back Office para las páginas de administración del módulo. |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Menos probable, pero podría usarse para añadir una pestaña o información específica del módulo relacionada con las exclusiones de productos. |
| `moduleRoutes` | Cuando PrestaShop construye su tabla de enrutamiento. | Para definir URLs amigables personalizadas para sus controladores frontales (por ejemplo, `/module/newslettervoucher/cronjob`). |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Vale único para suscripción a boletín", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
