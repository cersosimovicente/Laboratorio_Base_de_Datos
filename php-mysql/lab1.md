# Ejercicios PHP y MySql
### Ejercicio 1: Conexión a la Base de Datos
Conectar a una base de datos MySQL utilizando PHP.
```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "mi_base_de_datos";

// Crear la conexión
$conn = new mysqli($servername, $username, $password, $dbname);

// Verificar la conexión
if ($conn->connect_error) {
    die("La conexión ha fallado: " . $conn->connect_error);
}
echo "Conexión exitosa";
?>
```
## Ejercicio 2: Crear una Tabla
```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL UNIQUE
);
```
```php
<?php
$sql = "CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL UNIQUE
)";

if ($conn->query($sql) === TRUE) {
    echo "Tabla 'usuarios' creada exitosamente";
} else {
    echo "Error al crear la tabla: " . $conn->error;
}
?>
```
## Ejercicio 3: Insertar Datos
Descripción: Insertar un nuevo usuario en la tabla "usuarios".
SQL
```sql
INSERT INTO usuarios (nombre, email) VALUES ('Juan Pérez', 'juan@example.com');
```
PHP
```php
<?php
$sql = "INSERT INTO usuarios (nombre, email) VALUES ('Juan Pérez', 'juan@example.com')";

if ($conn->query($sql) === TRUE) {
    echo "Nuevo registro creado exitosamente";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
?>
```
## Ejercicio 4: Seleccionar Datos
Descripción: Seleccionar todos los usuarios de la tabla "usuarios".
SQL:
```sql
SELECT * FROM usuarios;
```
PHP:
```php
<?php
$sql = "SELECT id, nombre, email FROM usuarios";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Nombre: " . $row["nombre"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "0 resultados";
}
?>
```
## Ejercicio 5: Actualizar Datos
Descripción: Actualizar el email de un usuario específico.
SQL:
```sql
UPDATE usuarios SET email='nuevo_email@example.com' WHERE id=1;
```
PHP:
```php
<?php
$sql = "UPDATE usuarios SET email='nuevo_email@example.com' WHERE id=1";

if ($conn->query($sql) === TRUE) {
    echo "Registro actualizado exitosamente";
} else {
    echo "Error actualizando el registro: " . $conn->error;
}
?>
```
## Ejercicio 6: Eliminar Datos
Descripción: Eliminar un usuario específico de la tabla "usuarios".
SQL:
```sql
DELETE FROM usuarios WHERE id=1;
```
PHP:
```php
<?php
$sql = "DELETE FROM usuarios WHERE id=1";

if ($conn->query($sql) === TRUE) {
    echo "Registro eliminado exitosamente";
} else {
    echo "Error eliminando el registro: " . $conn->error;
}
?>
```
## Ejercicio 7: Preparar una Consulta SQL
Descripción: Utilizar sentencias preparadas para insertar datos.
PHP:
```php
<?php
$stmt = $conn->prepare("INSERT INTO usuarios (nombre, email) VALUES (?, ?)");
$stmt->bind_param("ss", $nombre, $email);

// Establecer los parámetros y ejecutar
$nombre = "Ana Gómez";
$email = "ana@example.com";
$stmt->execute();

$nombre = "Luis Rodríguez";
$email = "luis@example.com";
$stmt->execute();

echo "Nuevos registros creados exitosamente";

$stmt->close();
?>
```
## Ejercicio 8: Contar Registros
Descripción: Contar el número de usuarios en la tabla "usuarios".
SQL:
```sql
SELECT COUNT(*) as total FROM usuarios;
```
PHP
```php
<?php
$sql = "SELECT COUNT(*) as total FROM usuarios";
$result = $conn->query($sql);
$row = $result->fetch_assoc();
echo "Total de usuarios: " . $row['total'];
?>
```
## Ejercicio 9: Filtrar Datos
Descripción: Seleccionar usuarios cuyo nombre comienza con 'A'.
```sql
SELECT * FROM usuarios WHERE nombre LIKE 'A%';
```
PHP:
```php
<?php
$sql = "SELECT id, nombre, email FROM usuarios WHERE nombre LIKE 'A%'";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Nombre: " . $row["nombre"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "0 resultados";
}
?>
```
## Ejercicio 10: Paginar Resultados
Descripción: Obtener usuarios con paginación, mostrando 5 por página.
SQL:
```sql
SELECT * FROM usuarios LIMIT 5 OFFSET 0;
```
PHP
```php
<?php
$limit = 5;
$page = 1;
$offset = ($page - 1) * $limit;

$sql = "SELECT id, nombre, email FROM usuarios LIMIT $limit OFFSET $offset";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Nombre: " . $row["nombre"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "0 resultados";
}
?>
```
## Conexión Cierre
PHP:
Recordar cerrar la conexión a la base de datos al finalizar tus operaciones.
```php
<?php
$conn->close();
?>
```


