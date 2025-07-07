Este proyecto es una aplicación que funciona como el "cerebro" de una tienda online, hecha con NestJS. Lo que permite es crear, ver, actualizar y borrar información sobre usuarios, productos, pedidos y categorías. Todo está guardado en una base de datos MySQL, y el sistema está organizado de forma clara para que cada cosa tenga su lugar (por ejemplo, las categorías tienen productos, y los pedidos pertenecen a usuarios). Para que funcione, levantas una base de datos (que puedes hacer con Docker para que sea más fácil), instalas las dependencias y enciendes el servidor. Luego puedes ver y probar todo desde el navegador con Swagger o con Postman. En resumen, es un proyecto bien organizado que permite manejar toda la información básica que tendría una tienda online.
Buenas prácticas en la estructura del proyecto (arquitectura modular).

CRUD completo (Create, Read, Update, Delete) para varias entidades.

Validaciones de datos utilizando class-validator y class-transformer.

Manejo adecuado de errores mediante HttpException y HttpStatus.

Conexión a base de datos MySQL mediante TypeORM, con al menos 4 entidades relacionadas.

Documentación de las rutas con Swagger y pruebas de los endpoints usando Postman.

Código organizado y subido a un repositorio de GitHub.

 Descripción General
La API implementa la gestión de una tienda en línea, incluyendo las siguientes entidades relacionadas:

Usuario

Producto

Pedido

Categoría

Relaciones entre las entidades:
Un Producto pertenece a una Categoría (ManyToOne / OneToMany).

Un Pedido puede tener varios Productos (ManyToMany).

Un Pedido está relacionado con un Usuario (ManyToOne / OneToMany).

Se construyó un CRUD completo para las entidades Usuario, Producto, Categoría y Pedido.

Instalación y ejecución
1. Levantar la base de datos con Docker (opcional)
En la raíz del proyecto ejecuta:

bash
Copiar
Editar
docker-compose up -d
Esto levantará:

Un contenedor MySQL

Un Adminer (interfaz web para administrar la base de datos) accesible en:

http://localhost:8080
Credenciales por defecto:

Opción	Valor
Servidor	db
Usuario	root
Contraseña	tu_password
Base de datos	tienda

2. Instalar las dependencias del proyecto
Ejecuta el siguiente comando en la raíz del proyecto:


npm install
3. Ejecutar el servidor NestJS en desarrollo
Levanta el servidor ejecutando:


npm run start:dev
La API estará disponible en:
http://localhost:3000

La documentación Swagger estará en:
http://localhost:3000/api

 Comandos útiles

npm run start:dev       # Inicia el servidor en modo desarrollo
docker-compose up -d    # Levanta la base de datos MySQL y Adminer
docker-compose down     # Detiene y elimina los contenedores Docker
