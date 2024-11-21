# Crear una Base de Datos en SQL Server Management Studio (SSMS)

A continuación, se presenta un tutorial detallado para crear una base de datos en SQL Server Management Studio (SSMS).

## Paso 1: Abrir SQL Server Management Studio

1. Abre **SQL Server Management Studio**.

2. Conéctate a la instancia de SQL Server donde deseas crear la base de datos.

    - Selecciona el nombre del servidor (**VIRTAMINTIC**), el método de autenticación (SQL Server o Windows), e ingresa las credenciales si es necesario.
    - Haz clic en **Connect**.

<div style="text-align: center;">
  <img src="_images/paso_3_1.png" alt="Conectar Instancia" width="70%">
</div>
<br>

## Paso 2: Navegar al Explorador de Objetos

1. Una vez conectado, localiza el Object Explorer (Explorador de Objetos) en el panel izquierdo.
2. Expande el nodo correspondiente al servidor al que estás conectado.
3. Busca la carpeta Databases (Bases de datos).

<div style="text-align: center;">
  <img src="_images/paso_3_2.png" alt="Carpeta Databases">
</div>
<br>

## Paso 3: Creación de la Nueva Base de Datos

1. Haz clic derecho en la carpeta **Databases**
2. Selecciona la opción **New Database...** (Nueva base de datos)

<div style="text-align: center;">
  <img src="_images/paso_3_3.png" alt="Creación de la nueva BD">
</div>
<br>

## Paso 4: Configurar los Detalles de la Base de Datos

1. En la ventana emergente:
    - En el campo **Database Name**, ingresa el nombre de la base de datos (en nuestro ejemplo, `films_db`).
    - Opcionalmente, puedes configurar las ubicaciones de los archivos de datos (MDF) y de registro de transacciones (LDF) en las pestañas inferiores si necesitas personalizar la ruta.

2. Verifica las configuraciones predeterminadas en las pestañas:
    - **Options:** Ajusta el modelo de recuperación, el nivel de compatibilidad, entre otros.
    - **Filegroups:** Puedes administrar grupos de archivos si es necesario.

<div style="text-align: center;">
  <img src="_images/paso_3_4.png" alt="Creación de la nueva BD" width="70%">
</div>
<br>

## Paso 5: Crear la Base de Datos

1. Una vez que hayas configurado todo, haz clic en **OK**.
2. La base de datos será creada y aparecerá en la carpeta Databases en el Explorador de Objetos.

## Paso 6: Verificar la Base de Datos Creada

1. Expande la carpeta **Databases** en el Explorador de Objetos.
2. Verifica que la nueva base de datos (`films_db`, en este caso) esté listada.
3. Expande la base de datos para ver carpetas como **Tables**, **Views**, **Stored Procedures**, entre otras.

<div style="text-align: center;">
  <img src="_images/paso_3_5.png" alt="Verificación BD">
</div>
<br>

## Paso 7: (Opcional) Ejecutar un Script para Crear una Base de Datos

Si prefieres usar un script SQL para crear una base de datos, puedes ejecutar el siguiente código en una nueva consulta:

```sql
CREATE DATABASE films_db;
GO
```

- Para ejecutar el script:
<br>
    1. Haz clic en el botón **New Query** (Nueva consulta) en la barra superior.

    <div style="text-align: center;">
        <img src="_images/paso_3_6.png" alt="Nuevo Query">
    </div>
    <br>
    2. Copia el script anterior, pégalo en la ventana de consulta y haz clic en **Execute** (Ejecutar).
<br>
    <div style="text-align: center;">
        <img src="_images/paso_3_7.png" alt="Ejecución del Script y Verificación">
    </div>
    <br>
    
## Notas Finales
- La base de datos recién creada estará lista para ser utilizada.
- Asegúrate de otorgar permisos necesarios si la base de datos será usada por usuarios específicos.
- Puedes comenzar a crear tablas y otros objetos dentro de la base de datos desde el Explorador de Objetos o a través de scripts SQL.

¡Ahora estás listo para gestionar tu base de datos en SSMS!
