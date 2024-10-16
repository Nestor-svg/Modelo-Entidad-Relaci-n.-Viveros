# Modelo-Entidad-Relación.-Viveros
### Descripción de cada una de las entidades definidas.
- Cliente: Representa a las personas o empresas que compran productos en el vivero. El cliente tiene un atributo de Tipo que puede ser "Tajinaste Plus" o "Normal", lo que indica diferentes categorías o programas de clientes.
- Compra: Entidad que registra las transacciones realizadas por los clientes. Tiene un atributo Fecha, lo que indica el momento en que se realiza la compra.
- Vivero: Representa el lugar donde se gestionan los productos de jardinería. Tiene atributos relacionados con la Georreferenciación (Latitud y Longitud) para ubicar su localización.
- Empleado: Representa a las personas que trabajan en el vivero. Tiene un atributo de Histórico, lo que puede indicar si el empleado ha trabajado en un determinado periodo o está activo.
- Productos: Entidad que engloba los productos disponibles en el vivero. Cada producto tiene un atributo de Stock, que indica la cantidad disponible.
- Zona: Representa áreas del vivero o almacén donde se ubican los productos. Tiene un atributo de Tipo con las posibles opciones "Exterior", "Interior" o "Almacén", lo que permite clasificar la zona.
  
### Descripción y ejemplos ilustrativos del dominio de cada uno de los atributos de las entidades y de las relaciones.
- Cliente: Tipo:
  - Tajinaste Plus: Clientes que forman parte de un programa de fidelidad o VIP.
  - Normal: Clientes regulares sin afiliaciones especiales.
- Compra: Fecha: Fecha en que se realiza una compra. Ejemplo: 15/10/2024.
- Vivero: Georreferenciación:
  - Latitud: Coordenada de latitud del vivero. Ejemplo: 28.12345.
  - Longitud: Coordenada de longitud del vivero. Ejemplo: -15.65432.
- Empleado: Histórico: Registro que indica si el empleado está activo o es parte del historial. Ejemplo: "Activo" o "Histórico".
- Producto: Stock: Cantidad de unidades de un producto disponible. Ejemplo: 120 unidades.
- Zona: Tipo:
  - Exterior: Área fuera del vivero, utilizada para plantas o productos de exterior.
  - Interior: Área dentro del vivero.
  - Almacén: Espacio donde se guardan productos para almacenamiento.

### Descripción de cada una de las relaciones definidas. Describa con detalle la cardinalidad de cada relación.
- Compra - Cliente: Un cliente puede hacer múltiples compras, pero una compra es realizada por un solo cliente. Esta es una relación de 1 a N, donde un cliente puede estar asociado a muchas compras, pero una compra está asociada a un solo cliente.
- Compra - Productos: Relación que indica qué productos fueron adquiridos en cada compra. Un producto puede ser parte de muchas compras, y una compra puede incluir muchos productos. Esta relación es de tipo N a N.
- Vivero - Productos: Un vivero tiene productos. Esta relación implica que los productos están almacenados en el vivero, y es de 1 a N, ya que un vivero puede contener muchos productos, pero un producto pertenece a un único vivero (en este modelo específico).
- Empleado - Vivero: Un empleado trabaja en un vivero. Esta relación es de N a 1, ya que un empleado trabaja en un solo vivero, pero un vivero puede tener muchos empleados.
- Empleado - Zona: Un empleado está asignado a una zona. Esta es una relación de N a N, ya que un empleado puede estar asignado a varias zonas, y una zona puede tener a varios empleados asignados.

### Si las considera necesarias en su modelo, añada las restricciones semánticas propuestas.
- Restricción de unicidad: Cada Empleado solo puede estar asignado a un único Histórico o registro activo a la vez. Si se encuentra en el histórico, no puede estar activo.
- Restricción de stock: El Producto debe tener un Stock mayor o igual a cero. No se permiten cantidades negativas de productos.
- Restricción de georreferenciación: El Vivero debe tener siempre valores válidos de Latitud y Longitud, y estos deben estar dentro de los rangos geográficos válidos (-90 a 90 para latitud, -180 a 180 para longitud).
- Restricción de zona: Cada Zona debe estar claramente clasificada como "Exterior", "Interior" o "Almacén". No se permiten zonas sin clasificación.
