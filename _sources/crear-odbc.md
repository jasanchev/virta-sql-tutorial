# Configuración del ODBC para SQL Server

En este tutorial, aprenderás a conectar una instancia de SQL Server con Python utilizando ODBC. Este proceso requiere configurar correctamente el ODBC y escribir un script en Python para realizar la conexión.

## Paso 1: Abrir el Administrador de ODBC

1. En tu computadora, presiona `Windows + S` y busca **"ODBC Data Sources (64-bit)"**.
2. Haz clic en la aplicación para abrirla.

## Paso 2: Crear un Nuevo DSN:

1. En el Administrador ODBC, selecciona la pestaña **DSN de sistema** y haz clic en el botón **Agregar...**.

<div style="text-align: center;">
  <img src="_images/paso_4_1.png" alt="Administrador ODBC">
</div>
<br>

2. Selecciona el controlador **ODBC Driver 17 for SQL Server** de la lista de controladores disponibles y haz clic en **Finalizar**.

<div style="text-align: center;">
  <img src="_images/paso_4_2.png" alt="Elegir Controlador">
</div>
<br>

## Paso 3: Configurar el Nombre y el Servidor

1. Asigna un nombre al origen de datos, por ejemplo: **VIRTAMINTIC**.
2. En el campo Server, escribe el nombre del servidor SQL al que deseas conectarte, por ejemplo: `SANCHEZJAIME\VIRTAMINTIC`.
Haz clic en **Siguiente >**.

<div style="text-align: center;">
  <img src="_images/paso_4_3.png" alt="Configurar Servidor">
</div>
<br>

## Paso 4: Autenticación

1. Selecciona la opción **With SQL Server authentication using a login ID and password entered by the user**.
2. Ingresa el Login ID (por ejemplo, `equipo10`) y su contraseña.
3. Haz clic en **Siguiente >**.

<div style="text-align: center;">
  <img src="_images/paso_4_4.png" alt="Autenticación">
</div>
<br>

## Paso 5: Seleccionar la Base de Datos

1. Activa la casilla Change the default database to: y selecciona la base de datos deseada, por ejemplo: `films_db`.
2. Haz clic en **Siguiente >**.

<div style="text-align: center;">
  <img src="_images/paso_4_5.png" alt="Selección Base de Datos">
</div>
<br>

## Paso 6: Opciones Avanzadas

1. En esta ventana puedes dejar las opciones avanzadas por defecto.
2. Haz clic en **Finalizar**.

<div style="text-align: center;">
  <img src="_images/paso_4_6.png" alt="Opciones Avanzadas">
</div>
<br>

## Paso 7: Probar la Conexión

1. En la ventana emergente con el resumen de configuración, haz clic en **Test Data Source...**.

<div style="text-align: center;">
  <img src="_images/paso_4_7.png" alt="Probar Data Source">
</div>
<br>

2. Si todo está configurado correctamente, aparecerá el mensaje **TESTS COMPLETED SUCCESSFULLY!**. Haz clic en **OK**.

<div style="text-align: center;">
  <img src="_images/paso_4_8.png" alt="Configuración Correcta">
</div>
<br>

## Paso 8: Confirmar y Guardar

1. Vuelve a la ventana del Administrador ODBC. Verás el nuevo DSN de sistema creado en la lista.
2. Haz clic en **Aceptar** para cerrar el Administrador ODBC.

<div style="text-align: center;">
  <img src="_images/paso_4_9.png" alt="Confirmación">
</div>
<br>



¡Listo! Ahora tienes configurado un origen de datos ODBC para conectarte a tu instancia de SQL Server.


