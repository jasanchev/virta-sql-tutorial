# Creación y Verificación de una Tabla con Registros en SQL Server Usando Python

Este tutorial guía a través del proceso de creación de una tabla en SQL Server, la inserción de registros usando Python y la verificación de los datos tanto desde el código como en SQL Server Management Studio (SSMS).

## Paso 1: Creación de la Tabla `movies`

1. **Definir la consulta de creación de tabla:**
 ```
 create_table_query = """
                        CREATE TABLE movies (
                        product_id INT PRIMARY KEY,
                        product_name VARCHAR(100),
                        product_price REAL
                        );
"""
try:
    cursor.execute(create_table_query)
    print("Query ejecutado con éxito")
except Exception as e:
    print("Error en el query: {e}")
```
2. **Resultado esperado:**

En el Jupyter Notebook, deberías ver el mensaje:

```python
Query ejecutado con éxito
```
3. **Verificación en SSMS:**
    - En el **Object Explorer**, navega hasta tu base de datos.
    - Expande la carpeta **Tables** para verificar que la tabla productos ha sido creada.

<div style="text-align: center;">
  <img src="_images/paso_6_1.png" alt="Verificación Tabla SSMS">
</div>
<br>

## Paso 2: Inserción de Registro en la Tabla

1. **Definir la consulta de inserción de registros:**

```
insert_data_query = """
                INSERT INTO movies (
                    id,
                    title,
                    release_year,
                    country,
                    duration,
                    language,
                    certification,
                    gross,
                    budget
                )
                VALUES
                    (1, 'Teenage Mutant Ninja Turtles: Out of the Shadows', 2016, 'USA', 112, 'English', 'PG-13', 81638674, 135000000),
                    (2, 'The 5th Wave', 2016, 'USA', 112, 'English', 'PG-13', 34912982, 38000000),
                    (3, 'The Angry Birds Movie', 2016, 'USA', 97, 'English', 'PG', 107225164, 73000000),
                    (4, 'The BFG', 2016, 'UK', 117, 'English', 'PG', 52792307, 140000000),
                    (5, 'The Boss', 2016, 'USA', 99, 'English', 'R', 63034755, 29000000),
                    (6, 'The Boy', 2016, 'USA', 97, 'English', 'PG-13', 35794166, 10000000),
                    (7, 'The Conjuring 2', 2016, 'USA', 134, 'English', 'R', 102310175, 40000000),
                    (8, 'The Forest', 2016, 'USA', 93, 'English', 'PG-13', 26583369, 10000000),
                    (9, 'The Huntsman Winter''s War', 2016, 'USA', 120, 'English', 'PG-13', 47952020, 115000000),
                    (10, 'The Infiltrator', 2016, 'UK', 127, 'English', 'R', 14946229, 25000000),
                    (11, 'The Jungle Book', 2016, 'UK', 106, 'English', 'PG', 362645141, 175000000),
                    (12, 'The Legend of Tarzan', 2016, 'USA', 110, 'English', 'PG-13', 124051759, 180000000),
                    (13, 'The Masked Saint', 2016, 'Canada', 105, 'English', 'PG-13', 123777, 3500000),
                    (14, 'The Neon Demon', 2016, 'France', 118, 'English', 'R', 1330827, 7000000),
                    (15, 'The Perfect Match', 2016, 'USA', 96, 'English', 'R', 9658370, 5000000);
"""

try:
    cursor.execute(insert_data_query)
    print("Query ejecutado con éxito")
except Exception as e:
    print("Error en el query: {e}")
```

2. **Resultado esperado:**
    - Mensaje en el Jupyter Notebook:

    ```python
    Query ejecutado con éxito
    ```
3. **Visualización de la Tabla Creada en Python**

Utiliza el siguiente código para verificar los registros insertados directamente en Python:

```python
import warnings
from tabulate import tabulate

# Ignorar advertencias específicas de pandas
warnings.filterwarnings("ignore", message="pandas only supports SQLAlchemy")

vista_query = "SELECT * FROM movies"

try:
    result = pd.read_sql(vista_query, conn)
except Exception as e:
    print(f"Error en el Query: {e}")

# result
# print(result.to_string(index=False))
print(tabulate(result, headers='keys', tablefmt='psql', showindex=False))
```

**Salida esperada:**

<div style="text-align: center;">
  <img src="_images/paso_6_3.png" alt="Salida Esperada Python">
</div>
<br>

4. **Verificar en SSMS:**
    - Realizar una consulta SQL en SSMS para confirmar la inserción:
    ```sql
    SELECT * FROM movies
    ```
    - Deberías observar los registro insertados en la tabla `movies`

<div style="text-align: center;">
  <img src="_images/paso_6_2.png" alt="Verificación Registros SSMS">
</div>
<br>

---
**¡Felicidades!**

Has creado una tabla, agregado registros y verificado los datos tanto desde Python como desde SSMS. Ahora puedes expandir este proyecto con más funcionalidades como índices o catálogos.