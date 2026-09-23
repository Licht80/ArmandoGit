# Inventario

Aplicación web sencilla para registrar y consultar productos almacenados en una base de datos MySQL o MariaDB.

## Funcionalidades

- Mostrar los productos registrados.
- Registrar el nombre y la cantidad de un producto.
- Indicar si un producto está disponible o agotado.
- Mostrar la fecha de registro.
- Validar que los campos del formulario estén completos.

## Tecnologías

- PHP 7.4 o superior
- MySQL o MariaDB
- PDO para la conexión con la base de datos
- HTML y CSS

## Estructura del proyecto

```text
inventario/
├── base_datos.sql          # Estructura y datos iniciales de la base de datos
├── guardar.php             # Procesa el registro de productos
├── index.php               # Página principal y listado de productos
├── config/
│   └── conexion.php        # Configuración de la conexión a la base de datos
└── css/
    └── estilos.css         # Estilos de la aplicación
```

## Requisitos

1. Tener instalado PHP.
2. Tener instalado y ejecutándose MySQL o MariaDB.
3. Tener habilitada la extensión `pdo_mysql` de PHP.
4. Contar con un servidor web local, como Apache mediante XAMPP, WAMP o MAMP.

## Instalación

### 1. Copiar el proyecto

Coloca la carpeta `inventario` dentro del directorio público de tu servidor web. Por ejemplo, en XAMPP:

```text
htdocs/inventario
```

### 2. Crear la base de datos

Puedes importar el archivo `base_datos.sql` desde phpMyAdmin o desde la consola de MySQL/MariaDB.

Desde la consola:

```bash
mysql -u root -p < base_datos.sql
```

El script crea la tabla `productos` con algunos registros de ejemplo. Como el archivo no crea automáticamente la base de datos, ejecuta antes:

```sql
CREATE DATABASE inventario CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Después selecciona la base de datos e importa nuevamente el script:

```sql
USE inventario;
```

### 3. Configurar la conexión

Edita `config/conexion.php` y verifica estos valores:

```php
$servidor = 'localhost';
$baseDatos = 'inventario';
$usuario = 'root';
$contrasena = '';
```

Cambia el usuario, la contraseña, el servidor o el nombre de la base de datos según tu instalación local.

### 4. Iniciar la aplicación

Con Apache y MySQL/MariaDB activos, abre en el navegador:

```text
http://localhost/inventario/
```

También puedes usar el servidor integrado de PHP desde la carpeta del proyecto:

```bash
php -S localhost:8000
```

En ese caso, visita:

```text
http://localhost:8000
```

## Uso

1. Escribe el nombre del producto.
2. Introduce la cantidad disponible.
3. Selecciona **Registrar producto**.
4. El producto aparecerá en la tabla de productos registrados.

Los productos con una cantidad mayor que cero se muestran como **Disponible**. Los productos con cantidad igual a cero se muestran como **Sin existencia**.

## Notas

- La aplicación utiliza consultas preparadas para insertar productos.
- No se deben utilizar credenciales de desarrollo en un entorno de producción.
- Para producción, se recomienda mover las credenciales de conexión a variables de entorno y añadir autenticación y permisos de usuario.
