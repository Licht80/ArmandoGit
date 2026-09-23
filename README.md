# Inventario

Aplicación web para registrar y consultar productos almacenados en una base de datos. Permite llevar un control sencillo del nombre, la cantidad, el estado y la fecha de registro de cada producto.

## ¿Qué hace el proyecto?

- Muestra los productos registrados en una tabla.
- Permite registrar el nombre y la cantidad de un producto.
- Indica si cada producto está **Disponible** o **Sin existencia**.
- Muestra la fecha en la que se registró cada producto.
- Valida que los campos del formulario estén completos y que la cantidad sea numérica.

## Tecnologías utilizadas

- PHP 7.4 o superior.
- MySQL o MariaDB.
- PDO con la extensión `pdo_mysql` para conectarse a la base de datos.
- HTML5 y CSS3.

## ¿Qué se necesita instalar?


## Instalación y configuración

### 1. Obtener el proyecto

Clona el repositorio y entra en su carpeta:

```bash
git clone https://github.com/judas0102me/inventario.git
cd inventario
```

### 2. Crear la base de datos


### 3. Configurar la conexión

El archivo `config/conexion.php` contiene las credenciales locales y no se versiona por seguridad. Créalo a partir del archivo de ejemplo:

```bash
cp config/conexion_ejemplo.php config/conexion.php
```

Edita `config/conexion.php` y coloca los datos de tu instalación:

```php
$servidor = '127.0.0.1';
$baseDatos = 'inventario';
$usuario = 'root';
$contrasena = '';
```

No subas este archivo al repositorio si contiene credenciales reales.

## ¿Cómo se ejecuta?

### Opción A: servidor integrado de PHP

Con MySQL o MariaDB activo, ejecuta desde la carpeta del proyecto:

```bash
php -S localhost:8000
```

Abre `http://localhost:8000` en el navegador.

### Opción B: Apache



## Uso

1. Escribe el nombre del producto.
2. Introduce la cantidad disponible.
3. Selecciona **Registrar producto**.
4. El producto aparecerá en la tabla de productos registrados.

La aplicación utiliza consultas preparadas para insertar productos y escapa el nombre mostrado en la tabla. Para un entorno de producción se recomienda usar variables de entorno, autenticación y permisos de usuario.
