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

*2.4 *Prioridades*

Prioridad alta: 
- Realizar gestión del inventario (añadir, modificar, eliminar productos).
- Gestionar precios de los productos.

Prioridad media:
- Gestionar controles de acceso según el rol del usuario (administrador o trabajador).

Prioridad baja:
- Sistema de notificaciones (alertar al usuario cuando queden pocas unidades de un producto).

*2.5 Suposiciones*

- Si el hardware del dispositivo se encuentra desactualizado este podría generar conflictos al momento de realizar cambios en el sistema.
- Si los productos del negocio son más de lo que se tiene previsto el sistema puede ralentizarse.
- En caso de intentar usar el sistema en otro sistema operativo que no sea Windows no podrá ejecutarse.

*1. Problema del negocio*

*2. Usuarios*

*3. Funciones necesarias*
 
*4. Datos a guardar*

Estos datos sera la informacion principal de cada tabla que debomos formar estos seran los datos sobre;
- Productos: nombre, descripccion, codigo de barras, precio unitario, proveedores y Stock.
- Proveedores: Nombre, contacto, direccion.
- Usuraios: Nombres, contraseñas, rol,
contacto.
- Configuracion del local: Nombre del local, direccion, horario atencion.
- registro de movimientos: metodos de pago, moneda, cantidad, producto.

*5. Reglas de negocio*

*6. Proridades*

Prioridad alta: 
- Realizar gestión del inventario (añadir, modificar, eliminar productos).
- Gestionar precios de los productos.

Prioridad media:
- Gestionar controles de acceso según el rol del usuario (administrador o trabajador).

Prioridad baja:
- Sistema de notificaciones (alertar al usuario cuando queden pocas unidades de un producto).


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
    

*8. Requerimientos no funcionales*

*9. Plazo deseado*

*10. Definicion de alcance y presupuesto*

*11. Propuesta formal y cronograma de trabajo*

*12. Criterios de aceptacion y garantias*

Criterios de aceptación (mínimos y verificables)
- Productos
  - Se puede crear, leer, actualizar y eliminar un producto con los campos: nombre, código de barras, descripción, precio_unitario (>=0), stock_actual (>=0) y stock_minimo.
  - Al añadir un producto con un código de barras existente, el sistema rechazará la operación y mostrará un mensaje claro.
- Movimientos de inventario
  - Se registran entradas, salidas y ajustes; cada movimiento actualiza el stock del producto correspondiente y crea un registro de auditoría con usuario, fecha/hora y motivo.
- Alertas de stock
  - Cuando stock_actual <= stock_minimo, el sistema genera una alerta visible en la interfaz y registra la fecha_hora de la alerta.
- Gestión de usuarios y permisos
  - Se puede crear un usuario con rol (Administrador o Trabajador).
  - Inicio de sesión con credenciales funciona; las acciones están restringidas según el rol (por ejemplo, solo Administrador puede gestionar usuarios).
- Plataforma y despliegue
  - El instalador o guía de instalación permite desplegar y ejecutar la aplicación en Windows 10 o superior.

Garantías y soporte
- Período de garantía: corrección de defectos reportados durante 90 días posteriores a la entrega.
  - Parche crítico: respuesta inicial en 48 horas hábiles.
  - Corrección de defectos no críticos: dentro de 15 días hábiles, según prioridad acordada.
- Alcance de la garantía: la garantía cubre defectos funcionales según los criterios de aceptación; no cubre integraciones externas no especificadas (p.ej. facturación o contabilidad).
- Soporte post-garantía: opciones de contrato de mantenimiento y soporte con tiempos de respuesta y alcance acordados por separado.

Criterio de aceptación final:
- El cliente valida la entrega cuando todas las pruebas de aceptación documentadas pasan en el entorno de prueba y la documentación requerida ha sido entregada.

*13. Soporte y mantemiento*

*14. Requisitos Futuros*

Como principal requisito aumentar la capacidad del sistema para gestionar mayor cantidad productos y perfiles permitiendo escalar proporcionalmente junto al negocio.






||||
| :- | :-: | -: |

