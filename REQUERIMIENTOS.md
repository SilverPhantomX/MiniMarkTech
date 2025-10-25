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

### *2. Usuarios*

#### - Administrador
    -Gestion de los perfiles
    -Acceso total a la base de datos
    -Gestiona las actualizaciones de stock por inventario
    -Permisos de encargado de bodega y de venta

#### - Encargado de bodega
    -Actualiza el stock al recibir mercadería
    -Actualiza el stock al realizar inventario
    -Gestiona los productos que tienen que ser mermados

#### - Ventas
    -Registra las ventas realizadas en tiempo real
    -Consulta la disponibilidad de stock
    -Consulta el precio de los productos

### *3. Funciones necesarias*

En esta sección se detallan las funciones principales que el sistema de base de datos de MiniMarkTech deberá permitir, tanto para la gestión de productos como de clientes, proveedores y ventas.

*3.1. Gestión de productos*

- Registrar nuevos productos con su nombre, código, categoría, precio y stock.
- Actualizar la información de un producto (por ejemplo, cambio de precio o cantidad).
- Eliminar productos descontinuados.
- Consultar listado de productos y su stock disponible.
- Generar alertas cuando el stock esté bajo el mínimo establecido.

*3.2. Gestión de ventas*

- Registrar una nueva venta (con fecha, hora, cajero, productos vendidos y total).
- Calcular el total automáticamente según los productos seleccionados.
- Emitir boleta o factura
- Consultar ventas diarias, semanales o mensuales.
- Registrar forma de pago (efectivo, tarjeta, etc.).

*3.3. Gestión de clientes*

- Registrar clientes frecuentes (nombre, RUT, teléfono, correo).
- Consultar historial de compras por cliente.
- Aplicar descuentos o promociones a clientes registrados.

*3.4. Gestión de proveedores*

- Registrar proveedores (nombre, contacto, tipo de productos que suministra).
- Registrar pedidos a proveedores.
- Actualizar estado de pedidos (pendiente, recibido, cancelado).
- Consultar historial de compras a cada proveedor.

*3.5. Gestión de usuarios del sistema*

- Registrar y administrar usuarios (por ejemplo, cajero, administrador).
- Asignar niveles de acceso según el rol.
- Registrar inicio y cierre de sesión de cada usuario.

*3.6. Reportes y consultas*

- Generar reportes de ventas por periodo.
- Mostrar los productos más vendidos.
- Consultar ganancias totales y promedio diario.
- Exportar reportes en formato PDF o Excel.

*3.7. Seguridad y respaldo*

- Realizar copias de seguridad automáticas.
- Restaurar la base de datos desde un respaldo.
- Validar datos ingresados (por ejemplo, evitar duplicados).

 
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
    

###  *8 Requerimientos no funcionales*

#### - Seguridad:
    1. El usuario con el rol de trabajador deberá ingresar al sistema con su rut y contraseña que será creada por un usuario con el rol de administrador. De la misma manera para un administrador.
    2. El primer usuario con el rol de administrador será ingresado por nosotros y a partir de ahi podrá crear mas usuario con roles de administrador o trabajador.
    3. Los usuarios con rol de administrador podrán restringir el acceso a los trabajadores según sea necesario.

#### - Rendimiento:
    1. Las consultas a la API no deber tomar mas de dos segundos bajo carga normal en promedio.

#### - Mantenibilidad:
    1. Se utilizara GitHub para el control de versiones en caso de corrección de bugs o añadir mejoras.
    2. En caso de que se añadan nuevos modulos a la arquitectura del sistema este deberá permitir seguir usando el sistema principal con normalidad.

#### - Usabilidad:
    1. La interfaz del sistema debe ser intuitiva con menus claros y opciones visibles.
    2. Se garantizará que el personal del sistema podrá utilizarlo en poco tiempo o con una capacitación mínima.


*9. Plazo deseado*

###*10. Definicion de alcance y presupuesto*


*10.1 Alcance del proyecto*

El presente proyecto contempla el desarrollo e implementación de la API del sistema MiniMarkTech, diseñada para optimizar la gestión de inventario, ventas, proveedores y clientes en un minimarket.
El alcance técnico se limita al desarrollo del backend mediante el uso de Express.js (Node.js) y MongoDB como base de datos principal, entregando una infraestructura escalable, segura y preparada para futuras integraciones con interfaces web o móviles.

Alcance funcional:

- Desarrollo de una API RESTful con endpoints que permitan realizar operaciones CRUD sobre las entidades del sistema: productos, clientes, proveedores, usuarios y ventas.
- Implementación de autenticación y autorización de usuarios, diferenciando roles (administrador y trabajador).
- Gestión de alertas de stock bajo con consultas automáticas.
- Generación de reportes de ventas e inventario exportables en formato JSON o PDF.
- Implementación de control de errores, validaciones de datos y registros de actividad.
- Configuración de seguridad y respaldo de datos mediante integración con MongoDB Atlas o servidor propio.

Fuera del alcance:

- No se incluye desarrollo de interfaz visual (web o móvil).
- No se contempla integración con sistemas externos de facturación, contabilidad o e-commerce.
- No se considera hosting ni mantenimiento post-entrega, salvo contratación adicional.
- No se desarrollarán módulos de delivery o catálogo en línea.

*10.2 Presupuesto estimado*

El presupuesto del proyecto contempla los costos asociados al análisis, desarrollo, pruebas y documentación técnica de la API.

Recursos requeridos:

Equipo de desarrollo:
- 1 Líder técnico / backend senior.
- 2 Desarrolladores backend.
- 1 QA tester / analista funcional.
- Duración estimada: 6 a 8 semanas de trabajo.
- Tecnologías y herramientas:
- Node.js + Express.js (entorno de desarrollo gratuito).
- MongoDB Atlas (plan estándar de 5 GB).
- Postman (para pruebas).
- GitHub o GitLab (control de versiones).
- Servicios de nube (opcional): AWS o Render para despliegue.

Estimación de costos:

- Análisis y diseño del sistema:
Modelado de datos, endpoints, seguridad
$250.000
- Desarrollo backend (API):
Implementación CRUD, autenticación, reportes
$750.000
- Pruebas y validación:
Testeo funcional, integración y corrección de errores
$200.000
- Documentación técnica
Manual de instalación y uso de la API
$100.000
- Total estimado del proyecto
$1.300.000 CLP


Observaciones:

- El presupuesto puede variar según ajustes en los requerimientos o ampliaciones del alcance.
- No incluye costos de hosting, dominios ni soporte posterior a la entrega.
- Se ofrece garantía técnica de 30 días posteriores a la implementación, exclusivamente para corrección de errores.


*11. Propuesta formal y cronograma de trabajo*

Propuesta formal
- Objetivo: Entregar una solución de gestión de inventario funcional en entorno Windows 10+, que permita registrar productos, gestionar stock, controlar usuarios y generar alertas de bajo inventario según los criterios definidos en este documento.
- Alcance de la entrega inicial (MVP):
  - Módulo de productos (CRUD).
  - Registro y control de movimientos de inventario (entradas/salidas/ajustes).
  - Gestión de usuarios y roles (Administrador, Trabajador).
  - Alertas de stock y registro de auditoría.
  - Documentación: manual de usuario, guía de instalación y procedimiento de backup/restauración.
- Entregables:
  - Código fuente en repositorio (GitHub).
  - Instalador o guía de despliegue para Windows.
  - Conjunto de pruebas de aceptación y resultados.
  - Plan de soporte y garantía (90 días + opciones de mantenimiento).

Cronograma de trabajo (sugerido)
- Duración total estimada: 10 semanas.
- Fase 0 — Inicio y definición (1 semana)
  - Actividades: kickoff, definición detallada de requisitos, validación del alcance.
  - Entregable: Documento de especificaciones finales y plan de proyecto.
- Fase 1 — Diseño (1 semana)
  - Actividades: diseño de arquitectura, modelo de datos y wireframes básicos.
  - Entregable: diagramas ER, mockups y plan de pruebas.
- Fase 2 — Implementación MVP (4 semanas)
  - Actividades: desarrollo de módulos de productos, movimientos, usuarios y alertas.
  - Entregable: versión funcional interna (build).
- Fase 3 — Integración y pruebas (2 semanas)
  - Actividades: pruebas unitarias, integración, corrección de errores y verificación de rendimiento.
  - Entregable: build para pruebas de aceptación.
- Fase 4 — Pruebas de aceptación y ajustes (1 semana)
  - Actividades: pruebas con usuarios, ajustes según feedback, documentación final.
  - Entregable: versión candidata a entrega.
- Fase 5 — Entrega, capacitación y despliegue (1 semana)
  - Actividades: instalación en entorno del cliente, capacitación a usuarios clave, entrega de documentación.
  - Entregable: entrega formal y aceptación del cliente.

Hitos y criterios de aceptación
- Hito 1: Aprobación del documento de especificaciones (Fase 0) — avance al 10%.
- Hito 2: Diseño aprobado y modelo de datos implementado (Fase 1) — avance al 20%.
- Hito 3: MVP funcional comprobado internamente (Fase 2) — avance al 70%.
- Hito 4: Pruebas de aceptación completadas y correcciones aplicadas (Fase 4) — avance al 90%.
- Hito 5: Entrega final, capacitación y aceptación formal del cliente (Fase 5) — avance al 100%.

Asunciones y condiciones
- El cronograma asume disponibilidad de recursos del cliente para validaciones y pruebas (usuarios clave).
- El alcance indicado corresponde al MVP; nuevas funcionalidades serán planificadas como fases posteriores.
- Tiempo de respuesta para retroalimentación del cliente: máximo 5 días hábiles por ciclo de revisión.

Opcional: Plan de mantenimiento
- Período de garantía incluido: 90 días (corrección de defectos).
- Opcional contrato de soporte posterior con SLA según requerimientos del cliente.

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

### *13. Soporte y mantemiento*
Una vez entregado el sistema, se proporcionará un período de soporte técnico y mantenimiento durante 4 meses, con el objetivo de asegurar la estabilidad, corregir posibles errores y realizar ajustes menores.
#### - Alcance del soporte: 
    1. Correción de errores en las funcionalidades principales (gestión de productos, modificación de precios, gestión de usuarios).
    2. Ajustes menores como la interfaz o reportes según los requerimientos del cliente.
    3. Asistencia técnica remota en caso de que el cliente requiera solucionar algún problema con urgencia.

#### - Respaldo: 
    1. Se realizaran backups semanales de la base de datos los cuales estaran resguardados en un repositorio.
    2. En caso de pérdida de datos o corrupción de estos se restaurará a partir de la última copia de seguridad disponible.

#### - Tiempos de respuesta (SLA):
    1. Errores criticos que afecten a la funcionalidad completa o parcial del software se solucionarán en un plazo máximo de 24 horas.
    2. Errores menores o mejoras solicitadas por el clientes se aplicarán en un rango de 24 horas a 72 horas como plazo máximo.

*14. Requisitos Futuros*

Como principal requisito aumentar la capacidad del sistema para gestionar mayor cantidad productos y perfiles permitiendo escalar proporcionalmente junto al negocio.






||||
| :- | :-: | -: |

