# Ejercicios: CRUD básico

## Parte I – Consultas para la base de datos de SoftUni

Importar la base de datos SoftUni (`soft_uni.sql`)  
Analice detenidamente la estructura de los datos

### 1. Encuentre toda la información sobre los departamentos

Escriba una consulta SQL para encontrar toda la información disponible sobre los departamentos. Ordene la información por id.

Ejemplo:
| department_id | name         | manager_id |
| ------------- | ------------ | ---------- |
| 1             | Engineering  | 12         |
| 2             | Tool Design  | 4          |
| 3             | Sales        | 273        |
| ...           | ...          | ...        |

**Respuesta:**

### 2. Encuentre todos los nombres de los departamentos

Escriba una consulta SQL para buscar todos los nombres de departamento. Ordene la información por id.

Ejemplo:
| name          |
| ------------- |
| Engineering   |
| Tool Design   |
| Sales         |
| ...           |

**Respuesta:**

### 3. Encuentre el salario de cada empleado

Escriba una consulta SQL para encontrar el nombre, apellido y salario de cada empleado. Ordene la información por id.

Ejemplo:
| first_name | last_name | salary    |
| ---------- | --------- | --------- |
| Guy        | Gilbert   | 12500.00  |
| Kevin      | Brown     | 13500.00  |
| Roberto    | Tamburello| 43300.00  |
| ...        | ...       | ...       |

**Respuesta:**

### 4. Encuentre el nombre completo de cada empleado

Escriba una consulta SQL para encontrar el nombre, el segundo nombre y el apellido de cada empleado. Ordene la información por id.

Ejemplo:
| first_name | middle_name | last_name |
| ---------- | ------------| ----------|
| Guy        | R           | Gilbert   |
| Kevin      | F           | Brown     |
| Roberto    | NULL        | Tamburello|
| ...        | ...         | ...       |

**Respuesta:**

### 5. Encuentre la dirección de correo electrónico de cada empleado

Escriba una consulta SQL para encontrar la dirección de correo electrónico de cada empleado (por su nombre y apellido). Tenga en cuenta que el dominio de correo electrónico es `softuni.bg`. Los correos electrónicos deben verse como "John.Doe@softuni.bg". La columna producida debe llamarse `full_email_address`.

Ejemplo:
| full_email_address          |
| --------------------------- |
| Guy.Gilbert@softuni.bg      |
| Kevin.Brown@softuni.bg      |
| Roberto.Tamburello@softuni.bg|
| ...                         |

**Respuesta:**

### 6. Encuentre todos los salarios de los empleados

Escriba una consulta SQL para encontrar los salarios de todos los empleados diferentes. Mostrar solo los salarios.

Ejemplo:
| salary   |
| -------- |
| 12500.00 |
| 13500.00 |
| 43300.00 |
| ...      |

**Respuesta:**

### 7. Encuentre toda la información sobre los empleados

Escriba una consulta SQL para encontrar toda la información sobre los empleados cuyo puesto de trabajo es "Representante de ventas". Ordene la información por id.

Ejemplo:
| id  | first_name | last_name | middle_name | job_title               | dept_id | mngr_id | hire_date | salary  | address_id |
| --- | ---------- | --------- | ----------- | ----------------------- | ------- | ------- | --------- | ------- | ---------- |
| 275 | Michael    | Blythe    | G           | Sales Representative    | 3       | 268     | ...       | 23100.00| 60         |
| 276 | Linda      | Mitchell  | C           | Sales Representative    | 3       | 268     | ...       | 23100.00| 170        |
| 277 | Jillian    | Carson    | NULL        | Sales Representative    | 3       | 268     | ...       | 23100.00| 61         |
| ... | ...        | ...       | ...         | ...                     | ...     | ...     | ...       | ...     | ...        |

**Respuesta:**

### 8. Encuentre los nombres de todos los empleados por salario en el rango

Escriba una consulta SQL para encontrar el nombre, apellido y cargo de todos los empleados cuyo salario esté en el rango [20000, 30000]. Ordene la información por id.

Ejemplo:
| first_name | last_name | job_title              |
| ---------- | --------- | ---------------------- |
| Rob        | Walters   | Senior Tool Designer   |
| Thierry    | D'Hers    | Tool Designer          |
| JoLynn     | Dobney    | Production Supervisor  |
| ...        | ...       | ...                    |

**Respuesta:**

### 9. Encuentre los nombres de todos los empleados

Escriba una consulta SQL para encontrar el nombre completo de todos los empleados cuyo salario es 25000, 14000, 12500 o 23600. El nombre completo es una combinación de nombre, segundo nombre y apellido (separados por un solo espacio) y deben estar en una columna llamada `full_name`.

Ejemplo:
| full_name          |
| ------------------ |
| Guy R Gilbert      |
| Thierry B D'Hers   |
| JoLynn M Dobney    |
| ...                |

**Respuesta:**

### 10. Encuentre a todos los empleados sin gerente

Escriba una consulta SQL para encontrar nombres y apellidos de aquellos empleados que no tienen un gerente.

Ejemplo:
| first_name | last_name |
| ---------- | --------- |
| Ken        | Sanchez   |
| Svetlin    | Nakov     |
| ...        | ...       |

**Respuesta:**

### 11. Encuentre todos los empleados con un salario superior a 50000

Escriba una consulta SQL para encontrar el nombre, apellido y salario de aquellos empleados que tienen un salario superior a 50000. Ordenarlos en orden decreciente por salario.

Ejemplo:
| first_name | last_name | salary    |
| ---------- | --------- | --------- |
| Ken        | Sanchez   | 125500.00 |
| James      | Hamilton  | 84100.00  |
| ...        | ...       | ...       |

**Respuesta:**

### 12. Encuentra los 5 empleados mejor pagados

Escriba una consulta SQL para encontrar nombres y apellidos sobre los 5 empleados mejor pagados ordenados descendentemente por su salario.

Ejemplo:
| first_name | last_name |
| ---------- | --------- |
| Ken        | Sanchez   |
| James      | Hamilton  |
| ...        | ...       |

**Respuesta:**

### 13. Encuentre a todos los empleados excepto a los de marketing

Escriba una consulta SQL para encontrar el nombre y apellido de todos los empleados cuyo ID de departamento sea diferente de 4.

Ejemplo:
| first_name | last_name     |
| ---------- | ------------- |
| Guy        | Gilbert       |
| Roberto    | Tamburello    |
| Rob        | Walters       |
| ...        | ...           |

**Respuesta:**

### 14. Ordenar tabla de empleados

Escriba una consulta SQL para ordenar todos los registros de la tabla `employees` según los siguientes criterios:
1. Primero por salario en orden decreciente.
2. Luego por nombre alfabético.
3. Luego por apellido descendente.
4. Luego por segundo nombre alfabéticamente.
5. Ordene la información por id.

Ejemplo:
| id  | first_name | last_name | middle_name | job_title               | dept_id | mngr_id | hire_date | salary   | address_id |
| --- | ---------- | --------- | ----------- | ----------------------- | ------- | ------- | --------- | -------- | ---------- |
| 109 | Ken        | Sanchez   | J           | Chief Executive Officer | 16      | NULL    | ...       | 125500.00| 177        |
| 148 | James      | Hamilton  | R           | Vice President of Production | 7   | 109     | ...       | 84100.00 | 158        |
| 273 | Brian      | Welcker   | S           | Vice President of Sales | 3       | 109     | ...       | 72100.00 | 134        |
| ... | ...        | ...       | ...         | ...                     | ...     | ...     | ...       | ...      | ...        |

**Respuesta:**

### 15. Crear Vista empleados con salarios

Escriba una consulta SQL para crear una vista `v_employees_salaries` con el nombre, los apellidos y el salario de cada empleado.

Ejemplo:
| first_name | last_name | salary    |
| ---------- | --------- | --------- |
| Guy        | Gilbert   | 12500.00  |
| Kevin      | Brown     | 13500.00  |
| ...        | ...       | ...       |

**Respuesta:**

### 16. Crear Vista empleados con títulos de trabajo

Escriba una consulta SQL para crear `v_employees_job_titles` de vista con el nombre completo del empleado y el cargo. Cuando el segundo nombre es NULL, reemplácelo con una cadena vacía (`''`).

Ejemplo:
| full_name         | job_title             |
| ----------------- | --------------------- |
| Guy R Gilbert     | Production Technician |
| Kevin F Brown     | Marketing Assistant   |
| Roberto Tamburello| Engineering Manager   |
| ...               | ...                   |

**Respuesta:**

### 17. Distintos títulos de trabajo

Escriba una consulta SQL para encontrar todos los títulos de trabajo distintos. Ordene el resultado por título de trabajo alfabéticamente.

Ejemplo:
| job_title                 |
| ------------------------- |
| Accountant                |
| Accounts Manager          |
| Accounts Payable Specialist|
| ...                       |

**Respuesta:**

### 18. Encuentre los primeros 10 proyectos iniciados

Escriba una consulta SQL para encontrar los primeros 10 proyectos iniciados. Seleccione toda la información sobre ellos y ordénelos por fecha de inicio, luego por nombre. Ordene la información por id.

Ejemplo:
| id  | name            | description                             | start_date          | end_date            |
| --- | --------------- | --------------------------------------- | ------------------- | ------------------- |
| 6   | HL Road Frame   | Research design and development of HL Road | 1998-05-02 00:00:00 | 2003-06-01 00:00:00 |
| 2   | Cycling Cap     | Research design and development of C    | 2001-06-01 00:00:00 | 2003-06-01 00:00:00 |
| 5   | HL Mountain Frame| Research design and development of HL M | 2001-06-01 00:00:00 | 2003-06-01 00:00:00 |
| ... | ...             | ...                                     | ...                 | ...                 |

**Respuesta:**

### 19. Últimos 7 empleados contratados

Escriba una consulta SQL para encontrar los últimos 7 empleados contratados. Seleccione su nombre, apellido y fecha de contratación.

Ejemplo:
| first_name | last_name | hire_date            |
| ---------- | --------- | -------------------- |
| Rachel     | Valdez    | 2005-07-01 00:00:00  |
| Lynn       | Tsoflias  | 2005-07-01 00:00:00  |
| Syed       | Abbas     | 2005-04-15 00:00:00  |
| ...        | ...       | ...                  |

**Respuesta:**

### 20. Aumentar los salarios

Escriba una consulta SQL para aumentar los salarios de todos los empleados que están en el departamento de Ingeniería, Diseño de Herramientas, Marketing o Servicios de Información en un 12%. A continuación seleccione la columna `salary` en la tabla `employees`.

Ejemplo:
| salary    |
| --------- |
| 12500.00  |
| 15120.00  |
| 48496.00  |
| 33376.00  |
| ...       |

**Respuesta:**

## Parte II – Consultas para la base de datos de geografía

Importar la base de datos geography (`geography.sql`)  
Analice detenidamente la estructura de los datos

### 21. Todos los picos de la montaña

Muestra todos los picos de las montañas en orden alfabético.

Ejemplo:
| peak_name           |
| ------------------- |
| Aconcagua           |
| Banski Suhodol      |
| Batashki Snezhnik   |
| ...                 |

**Respuesta:**

### 22. Países más grandes por población

Encuentra los 30 países más grandes de Europa por población. Muestra el nombre del país y la población. Ordene los resultados por población (de mayor a menor) y luego por país alfabéticamente.

Ejemplo:
| country_name | population   |
| ------------ | ------------ |
| Russia       | 140702000    |
| Germany      | 81802257     |
| France       | 64768389     |
| ...          | ...          |

**Respuesta:**

### 23. Países y moneda (Euro / No Euro)

Encuentre todos los países junto con información sobre su moneda. Muestra el nombre del país, el código del país e información sobre su moneda: "Euro" o "No Euro". Ordene los resultados por nombre de país alfabéticamente.

Ejemplo:
| country_name | country_code | currency    |
| ------------ | ------------ | ----------- |
| Afghanistan  | AF           | Not Euro    |
| Åland        | AX           | Euro        |
| Albania      | AL           | Not Euro    |
| ...          | ...          | ...         |

**Respuesta:**

## Parte III – Consultas para la base de datos de Diablo

Importar la base de datos diablo (`diablo.sql`)  
Analice detenidamente la estructura de los datos

### 24. Todos los personajes de Diablo

Muestra el nombre de todos los caracteres en orden alfabético.

Ejemplo:
| name         |
| ------------ |
| Amazon       |
| Assassin     |
| Barbarian    |
| ...          |

**Respuesta:**

