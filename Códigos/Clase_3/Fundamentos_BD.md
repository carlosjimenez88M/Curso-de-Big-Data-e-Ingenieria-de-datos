************************
Conceptos básicos de SQL
************************

# CREATE

Este comando crea un objeto llamado EmpleadO. En este caso se creara una tabla.

####  Ejemplo
	
	# CREATE TABLE Empleado
	(
	id_empleado INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	nombre VARCHAR(50),
	apellido VARCHAR(50),
	direccion VARCHAR(255),
	ciudad VARCHAR(60),
	telefono VARCHAR(15),
	peso VARCHAR (5),
	edad (2),
	id_cargo_empleado INT
	)

# ALTER

Esta sentencia permite modificar la estructura de un objeto. Se pueden agregar/quitar campos a una tabla, modificar el tipo de un campo, agregar/quitar índices a una tabla, modificar un trigger, etc.

####  Ejemplo
	
	# ALTER TABLE 'NOMBRE_TABLA' ADD NUEVO_CAMPO INT;
	# ALTER TABLE 'NOMBRE_TABLA' DROP COLUMN NOMBRE_COLUMNA;

# DROP

Esta sentencia elimina un objeto de la base de datos. Puede ser una tabla, vista, índice, trigger, función, procedimiento o cualquier otro objeto.

####  Ejemplo
	
	# DROP TABLE 'NOMBRE_TABLA';
	# DROP SCHEMA 'ESQUEMA;'
	# DROP DATABASE 'NOMBRE_BASEDATOS';

# TRUNCATE

Este comando trunca todo el contenido de una tabla. La ventaja sobre el comando DROP, es que si se quiere borrar todo el contenido de la tabla, es mucho más rápido, especialmente si la tabla es muy grande. La desventaja es que TRUNCATE sólo sirve cuando se quiere eliminar absolutamente todos los registros, ya que no se permite la cláusula WHERE. Si bien, en un principio, esta sentencia parecería ser DML (Lenguaje de Manipulación de Datos), es en realidad una DDL, ya que internamente, el comando TRUNCATE borra la tabla y la vuelve a crear y no ejecuta ninguna transacción.

####  Ejemplo
	
	# TRUNCATE TABLE 'NOMBRE_TABLA';

# INSERT

Una sentencia INSERT de SQL agrega uno o más registros a una (y sólo una) tabla en una base de datos relacional.

Forma básica::

	# INSERT INTO ''tabla'' (''columna1'', [''columna2,... '']) VALUES (''valor1'', [''valor2,...''])
	
Las cantidades de columnas y valores deben ser iguales. Si una columna no se especifica, le será asignado el valor por omisión. Los valores especificados (o implícitos) por la sentencia INSERT deberán satisfacer todas las restricciones aplicables. Si ocurre un error de sintaxis o si alguna de las restricciones es violada, no se agrega la fila y se devuelve un error.

# UPDATE

Una sentencia UPDATE de SQL es utilizada para modificar los valores de un conjunto de registros existentes en una tabla.

####  Ejemplo
	
	# UPDATE mi_tabla SET campo1 = 'nuevo valor campo1' WHERE campo2 = 'N';

# DELETE

Una sentencia DELETE de SQL borra uno o más registros existentes en una tabla.

####  Ejemplo
	
	# DELETE FROM 'tabla' WHERE 'columna1' = 'valor1'


# Clausulas

Las cláusulas son condiciones de modificación utilizadas para definir los datos que desea seleccionar o manipular.

|Clausula|Descripción|
|:-------|:-----------|
FROM| Utilizada para especificar la tabla de la cual se van a seleccionar los registros
GROUP BY| Utilizada para agrupar los registros seleccionados en grupos específicos
ORDER BY| Utilizada para ordenar los registros seleccionados de acuerdo con un orden específico
WHERE| utilizada para hacer filtros sobre los registros de la clausula FROM

# Operadores
## Operadores logicos
|Operador|Uso|
|:-------|:-----------|
AND| Es el "y" lógico. Evalúa dos condiciones y devuelve un valor de verdad sólo si ambas son ciertas.
OR| Es el "o" lógico. Evalúa dos condiciones y devuelve un valor de verdad si alguna de las dos es cierta.
NOT| Negación lógica. Devuelve el valor contrario de la expresión.

## Operadores de comparacion
|Operador|Uso|
|:-------|:-----------|
<| Menor que
>| Mayor que
<=| Menor igual que
>=| Mayor igual que
<>| Distinto de
BETWEEN| Intervalo entre A y B


# Funciones de Agregado
|Función|Descripción|
|:-------|:-----------|
COUNT| Se utiliza para hacer un sobre conteo el número de registros de la sentencia SELECT
MAX| Se utiliza para devolver el mayor valor de un campo especificado
MIN| Se utiliza para devolver el menor valor de un campo especificado
SUM| Se utiliza para devolver la suma de todos los valores de un campo determinado
AVG| Se utiliza para calcular el promedio de los valores de un campo determinado

# Consultas
Sintaxis basica de una consulta SELECT:

    SELECT campo1, campo2, ..., campoN 
    FROM NOMBRE_TABLA;

    SELECT * 
    FROM NOMBRE_TABLA;

Sintaxis basica de una consulta con WHERE:

     SELECT campo1, campo2, ..., campoN
     FROM NOMBRE_TABLA
     WHERE <CONDICION>;

     SELECT *
     FROM NOMBRE_TABLA
     WHERE <CONDICION>;


Sintaxis basica de una consulta con GROUP BY:

    SELECT campo1, campo2, ..., campoN
    FROM NOMBRE_TABLA
    WHERE <CONDICION>
    GROUP BY campo1, campo2, ... campoN;

    SELECT nombre_campo 
    FROM NOMBRE_TABLA
    GROUP BY nombre_campo;

# LLave primaria
Sintaxis:
    
    CREATE TABLE test(
        auto_incre INTEGER  NOT NULL PRIMARY KEY
    ) 



