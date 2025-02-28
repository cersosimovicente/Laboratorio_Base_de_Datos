# CONTENIDOS
## Introducciones
- QUÉ ES UNA BASE DE DATOS
- QUÉ ES UN SISTEMA DE GESTIÓN DE BASE DE DATOS (DBMS)
- TIPOS DE DATOS
- QUÉ ES UNA TABLA DE BASE DE DATOS
- MODELO RELACIONAL
## ELEMENTOS DEL MODELO RELACIONAL
- ATRIBUTOS CLAVES CAMPOS
- RELACIONES
- DIAGRAMAS ERD

# LENGUAJE DE CONSULTA ESTRUCTURADO SQL
- Lenguaje de Definición de Datos (DDL)
  - CREATE
  - DROP
  - ALTER
- Lenguaje de Manipulación de Datos (DML)
  - SELECT
  - INSERT
  - UPDATE
   -DELETE
# CLÁUSULAS Y OPERADORES
- SELECT DISTINCT
- WHERE
- ORDER BY
- GROUP BY
- HAVING
- AS
- Operadores Relacionales
- Operadores Lógicos
#### Operadores propios de SQL
- BETWEEN
- IN
- LIKE
#### Qué son las funciones de agregación
- MAX(),
- MIN(),
- COUNT(),
- SUM(),
- AVG().
# CONSULTAS MULTITABLAS
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
# SUBCONSULTAS


# Modelo Evaluación Integradora - MySQL

## Parte 1: Teoría (40 puntos)

### 1. Definiciones (10 puntos)
1. Explica qué es un **DBMS** y da un ejemplo.  
   **Respuesta:** Un Sistema de Gestión de Bases de Datos (DBMS) es un software que permite crear, gestionar y administrar bases de datos. Ejemplo: MySQL.

2. Menciona tres **tipos de datos** en SQL.  
   **Respuesta:** INT, VARCHAR, DATE.

### 2. Modelo Relacional (10 puntos)
1. ¿Qué es una **clave primaria**?  
   **Respuesta:** Un atributo (o conjunto) que identifica de forma única cada registro en una tabla.


2. Dibuja un **diagrama ERD** básico para una relación entre `Clientes` y `Pedidos` (1:N).  
   **Respuesta:**  
Clientes (id_cliente PK, nombre)
Pedidos (id_pedido PK, fecha, id_cliente FK → Clientes)

### 3. SQL (20 puntos)
1. Diferencias entre **DDL** y **DML** (ejemplos).  
**Respuesta:**  
- DDL (CREATE, ALTER, DROP) define estructuras.  
- DML (SELECT, INSERT, UPDATE) manipula datos.

2. ¿Para qué sirve `HAVING`?  
**Respuesta:** Filtra resultados de funciones de agregación después de `GROUP BY`.

---

## Parte 2: Práctica (60 puntos)

### 1. Creación de tablas (DDL) (15 puntos)
Crea una tabla `Productos` con:  
- `id_producto` (clave primaria, entero)  
- `nombre` (texto, máximo 50 caracteres)  
- `precio` (decimal)  
- `stock` (entero)  

**Respuesta:**  
```sql
CREATE TABLE Productos (
 id_producto INT PRIMARY KEY,
 nombre VARCHAR(50),
 precio DECIMAL(10,2),
 stock INT
);
```

### 2. Consultas básicas (DML) (20 puntos)
1. Selecciona todos los productos con stock menor a 10.
**Respuesta**
```sql
SELECT * FROM Productos WHERE stock < 10;
```
2. Calcula el precio promedio de los productos.
**Respuesta**
```sql
SELECT AVG(precio) AS promedio_precio FROM Productos;
```
### 3. Consultas multitabla (15 puntos)
1. Escribir una consulta que muestre el nombre del cliente y la cantidad de pedidos realizados.

### 4. Subconsultas (10 puntos)
1. Selecciona los productos con un precio mayor al promedio.

### Parte 3: Caso integrador (20 puntos)

#### Diseña una base de datos para una biblioteca con:

- Libros (id, título, año_publicacion)

- Autores (id, nombre)

- Relación: Un libro puede tener varios autores (tabla intermedia LibrosAutores).

1. Escribir el código DDL para las tablas.

2. Realiza una consulta que muestre título del libro y nombres de sus autores.

### Enunciado para la consulta SQL  
**Contexto:**  
Una biblioteca necesita generar un reporte que muestre el **título de cada libro** junto con **todos los autores que participaron en su creación**, listados en una sola columna y separados por comas.  


**Requerimiento:**  
Escribir una consulta SQL que:  
1. Relacione las tablas `Libros`, `LibrosAutores` y `Autores` mediante joins.  
2. Muestre el **título del libro** en una columna.  
3. En otra columna, agrupe **todos los nombres de los autores** asociados a ese libro en un solo campo, separados por comas (ej: "Autor1, Autor2").  
4. Asegúrese de que cada libro aparezca una única vez en el resultado, incluso si tiene múltiples autores.  

**Nota:** Utiliza alias para las tablas y funciones de agrupación adecuadas.  

