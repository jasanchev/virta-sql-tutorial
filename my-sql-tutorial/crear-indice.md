# Crear y Asociar Índices al Catálogo Full-Text al Catálogo desde Python

## Paso 1: Crear un Índice Full-Text y Asociarlo al Catálogo

Un índice Full-Text se utiliza para habilitar la búsqueda de texto completo en una tabla y una columna específica. Para crear este índice, necesitas asegurarte de que la tabla tenga una clave primaria.

1. **Verificar la clave primaria e índice en SSMS**

Antes de crear el índice Full-Text, verifica que la tabla tenga una clave primaria. Esto es necesario porque el índice Full-Text se asocia a la clave primaria.

- **Abrir SSMS:**
    1. Conéctate a tu base de datos en SSMS.
    2. En el **Object Explorer**, navega a la tabla donde deseas crear el índice (en este caso, `movies`).
    3. Expande las carpetas **Columns** y **Indexes**.

- **Verifica la clave primaria:**
    - Asegúrate de que la columna clave (`id`) tenga un índice marcado como `(PK)` en la carpeta Indexes.

<div style="text-align: center;">
    <img src="_images/paso_8_1.png" alt="Índice PK" width="70%">
</div>
<br>

**Nota: El nombre del índice primario es necesario para el siguiente paso. En este caso, el índice primario se llama** `PK_movies_3213E83F43C0E526`.

2. **Crear el Índice Full-Text desde Python**

Utilizando el nombre del índice primario, ejecutaremos el script en Python para crear el índice Full-Text.

```python
create_index_query = """
                    CREATE FULLTEXT INDEX ON movies (title)
                    KEY INDEX PK__movies__3213E83F43C0E526
                    WITH STOPLIST = SYSTEM;
                    """

try:
    cursor.execute(create_index_query)
    print("Índice FTS creado con éxito")
except Exception as e:
    print(f"Error en el índice: {e}")
```

**Resultado esperado:**

- Si todo está correctamente configurado, deberías ver en consola:

```python
Índice FTS creado con éxito
```

3. **Verificar el Índice en SSMS**

- **Abrir SSMS:**

    1. Navega nuevamente al **Object Explorer**.
    2. Ve a **Storage -> Full Text Catalogs** -> Expande `catalogo_movies`.
    3. Asegúrate de que la tabla `movies` esté listada en el catálogo con la columna `title` indexada.

<div style="text-align: center;">
    <img src="_images/paso_8_2.png" alt="Verificar Índice SSMS" width="70%">
</div>
<br>

## Paso 2: Ejecutar Consultas Full-Text desde Python

1. **Requisitos previos**

- Asegúrate de que:
    1. El índice Full-Text está correctamente configurado.
    2. La tabla `movies` tiene un índice Full-Text asociado al catálogo catalogo_movies.
    3. Puedes realizar búsquedas en la columna `title`.

2. **Ejemplo: Consulta utilizando** `CONTAINS`

La consulta `CONTAINS` busca palabras clave o frases específicas en las columnas indexadas.

A continuación, un código en Python que ejecuta una consulta `CONTAINS` Full-Text para buscar registros en la tabla movies:

```python
contains_query="""
                SELECT * FROM movies
                WHERE CONTAINS(title, 'Demon')
            """

try:
    contains_result = cursor.execute(contains_query).fetchall()
    for row in contains_result:
        print(row)
except Exception as e:
    print(f"Error en el CONTAINS: {e}")
```
**Resultado esperado:**

- Si la consulta FTS está correctamente configurada, deberías ver en consola:

```python
(14, 'The Neon Demon', 2016, 'France', 118, 'English', 'R', Decimal('1330827.00'), Decimal('7000000.00'))
```

3. **Ejemplo: Consulta utilizando** `FREETEXT`

La consulta `FREETEXT` busca registros que coincidan con el significado o contexto de las palabras clave, sin requerir coincidencia exacta.

A continuación, un código en Python que ejecuta una consulta `FREETEXT` Full-Text para buscar registros en la tabla movies:

```python
freetext_query="""
                SELECT * FROM movies
                WHERE FREETEXT(title, 'The Neon')
            """

try:
    freetext_result = cursor.execute(freetext_query).fetchall()
    for row in freetext_result:
        print(row)
except Exception as e:
    print(f"Error en el FREETEXT: {e}")
```

**Resultado esperado:**

- Si la consulta FTS está correctamente configurada, deberías ver en consola:

```python
(14, 'The Neon Demon', 2016, 'France', 118, 'English', 'R', Decimal('1330827.00'), Decimal('7000000.00'))
```

---

Con este enfoque, puedes ejecutar consultas FTS desde Python y verificar los resultados tanto en el script como en SSMS.