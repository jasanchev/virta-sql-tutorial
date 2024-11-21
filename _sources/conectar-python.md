# Conectar la Instancia de SQL Server (VIRTAMINTIC) desde Python

Este tutorial muestra cómo establecer una conexión desde Python a una instancia de SQL Server (VIRTAMINTIC) y verificar la conexión exitosa. También incluye la visualización de la salida en un entorno de Jupyter Notebook.

## Paso 1: Importar las Librerías Necesarias

Primero, asegúrate de instalar las librerías necesarias para interactuar con SQL Server. En el entorno de Jupyter Notebook, puedes importar las siguientes librerías:

```python
import pyodbc
import pandas as pd
from sqlalchemy import text
```
## Paso 2: Configurar los Parámetros de Conexión

Define los detalles necesarios para conectarte a la instancia de SQL Server. Asegúrate de tener configurado el ODBC correspondiente:

```python
# Configuración de los parámetros de conexión
server = 'SANCHEZJAIME\\VIRTAMINTIC' # Nombre del DSN configurado en ODBC
database = 'films_db' # Nombre de la base de datos creada en SQL Server
username = 'equipo10' # Usuario del Servidor SQL
password = '12345678' # Contraseña del Servidor SQL
driver = 'ODBC Driver 17 for SQL Server' # Driver configurado
```

## Paso 3: Crear la cadena de conexión

A continuación, crea una cadena de conexión usando los parámetros definidos:

```python
conn_str = (
    f"DRIVER={driver};"
    f"SERVER={server};"
    f"DATABASE={database};"
    f"UID={username};"
    f"PWD={password}"
)
```

## Paso 4: Establecer la Conexión

Usa el módulo `pyodbc` para conectarte al servidor y verificar la conexión:

```python
try:
    # Establecer la conexión
    conn = pyodbc.connect(conn_str) # Conexión al servidor
    conn.autocommit = True # Para evitar problemas con transacciones
    cursor = conn.cursor() # Creación del cursor
    
    # Ejecutar una consulta
    print("Conexión exitosa") # Salida
    
except Exception as e:
    print("Error en la conexión:", e)
```
## Paso 5: Verificar la Salida de Jupyter Notebook

Al ejecutar el código en una celda de Jupyter Notebook, deberías ver la salida similar a esta si la conexión es exitosa:

```python
Conexión exitosa
```

¡Ahora estás listo para interactuar de manera avanzada con SQL Server desde Python!
