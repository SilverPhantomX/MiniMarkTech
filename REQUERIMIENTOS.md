||||
| :- | :-: | -: |

![](Aspose.Words.5aefcfe8-9428-4e88-92a8-b5a4171a0ab1.001.png)




<a name="_int_bbdufqov"></a>MiniMarkTech



**Integrantes**

Felipe Velásquez

Franko Zambrano

Christopher Córdoba

Ammylee Salamanca







**   




**1. Introducción**

El presente documento describe los requisitos de software del sistema MiniMarkTech, una herramienta diseñada para optimizar la gestión de inventario en un minimarket. Su propósito es facilitar el control de productos, mejorar la organización y reducir la posibilidad de quiebres de stock mediante alertas automáticas y consultas rápidas. Además, establece de manera estructurada las funcionalidades, restricciones, atributos y lineamientos técnicos que guiarán el desarrollo e implementación del sistema.

*1.1 Alcance*

La especificación de requisitos de este documento está dirigida para los usuarios 	que utilicen este sistema con el objetivo principal de gestionar procesos de	inventario (control de stock, etc) y administración de roles de usuarios.

*1.2 Propósito:*** 

El propósito del software es crear una herramienta eficaz para apoyar la gestión de inventario lo que permite llevar un listado de productos, registrar entrada y salida de mercadería y detectar cuando un producto esté casi sin stock permitiendo al propietario tener un control simple y confiable de la mercadería. 

*1.3 Lo mínimo que podrá hacer el programa:*

Podrá añadir o eliminar productos y controlar la entrada y salida de 		mercadería.  

*1.4 Ámbito del Sistema:*

`      `El Nombre del Sistema será **MiniMarkTech®**

**Que hará el sistema:** 

- Mantener un catálogo de productos organizado con sus respectivos datos como: nombre, código de barras, precio, stock y descripción
- Consultas rápidas de Stock
- Avisar cuando un producto este bajo en stock

**Que no hará el sistema:** 

- No generara facturas ni boletas
- No integrara sistema de contabilidad
- No tendrá catalogo Online ni delivery propio


**2. Descripciones**

`  `*2.1 Perspectiva del producto:*

- El sistema de gestión del inventario funcionará solamente dentro del local en donde se espera que el dueño, vendedor o trabajador del local lo utilice. En cuanto al hardware se requerirá cualquier computador de escritorio gama baja-media como mínimo con Windows 10 o superior y terminales con lectores de código de barras para la registrar los productos.

*2.2 Funciones del producto*

- Usuarios: Controles de niveles de acceso como trabajador, administrador. Registrar, modificar o eliminar de trabajadores o administradores.
- Gestión de inventario: Registrar productos nuevos, consultar el stock de estos y actualizar información.
- Control de stock: Alertar al usuario cuando queden pocas unidades de un producto.



*2.3 Características de los usuarios*

Este sistema va dirigido principalmente a 2 tipos de usuarios:

- Administradores: Manejo básico-intermedio de un sistema de inventario. Tienen acceso al control de stock de los productos, gestión del inventario; añadir, modificar o eliminar perfiles de trabajadores.
- Trabajadores: Conocimientos básicos, necesitan una interfaz simple para evitar confusiones al usar el sistema. Pueden gestionar el inventario.

*2.4 Restricciones*

- Limitaciones del hardware: Necesita como sistema operativo Windows 10 o superior. 
- Funciones de control: Administradores tendrán control sobre los perfiles de los usuarios incluyendo las funciones de los trabajadores. Los trabajadores podrán realizar controles de stock y gestión de inventario.
- Consideración acerca de la seguridad: Se implementan mecanismos de autenticación y control de acceso para asegurar que solo el personal autorizado pueda acceder a los datos sensibles del inventario.

*2.5 Suposiciones*

- Si el hardware del dispositivo se encuentra desactualizado este podría generar conflictos al momento de realizar cambios en el sistema.
- Si los productos del negocio son más de lo que se tiene previsto el sistema puede ralentizarse.
- En caso de intentar usar el sistema en otro sistema operativo que no sea Windows no podrá ejecutarse.

*1 nose*

*2 nose*

*3 Funciones necesarias*

*4 Datos a guardar*

*5 Reglas de negocio*

*6 Proridades*

### *7 Flujos Principales*

#### - Flujo de registro y control de inventario
    1. Se hace una lista de productos que pueden tener diferencias con el inventario 
    2. Se buscan los productos y se anota cuantos quedan
    3. El encargado inicia sesion en el sistema
    4. Actualiza el inventario con el stock correcto

#### - Flujo de compras (entrada)
    1. El encargado revisa los productos con bajos stock y revisa si existen alertas de bajo stock
    2. El encargado hace el pedido de los productos que sean necesarios 
    3. Al recibir la mercadería el encargado revisa si existen mermas o productos faltantes
    4. Los productos se ingresan al sistema mediante el SKU

#### - Flujo de venta (salida)
    1. El encargado de venta accede al sistema
    2. Escanea los productos que salen de la tienda
    3. El sistema descuenta los productos del stock cuando se hace la venta 
    

*8 Requerimientos no funcionales*

*9 Plazo deseado*

*10 Definicion de alcance y presupuesto*

*11 Propuesta formal*

*12 Criterios de aceptacion*

*13 Soporte y mantemiento*



*14 Requisitos Futuros*

Como principal requisito aumentar la capacidad del sistema para gestionar mayor cantidad productos y perfiles permitiendo escalar proporcionalmente junto al negocio.






||||
| :- | :-: | -: |

