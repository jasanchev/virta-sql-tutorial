# Creación de una Nueva Instancia de SQL Server 2022

```{admonition} Importante
:class: note
Para crear una nueva instancia de SQL Server, se asume que ya está instalada una única instancia de <b>SQL Server Express 2022</b> y <b>SQL Server Management Studio 20</b>.
```

Si ya tiene una instancia corriendo y necesitas otra:

1. Reinstala SQL Server Express y selecciona **"Nueva instancia"** durante la instalación

<div style="text-align: center;">
  <img src="_images/paso_1_1.png" alt="Centro de Instalación de SQL Server" width="70%">
</div>
<br>

2. **Verificación de actualizaciones del producto:** una vez que la búsqueda de actualizaciones del producto esté comple, haz clic en el botón **Next >** (siguiente) para continuar con la instalación.

<div style="text-align: center;">
  <img src="_images/paso_1_2.png" alt="Verificación de Actualizaciones dle Producto" width="70%">
</div>
<br>

3. **Selección del tipo de instalación:** en esta pantalla, pudes elegir el tipo de instalación que deseas realizar. Cómo se trata de crear una nueva instancia de SQL Server, selecciona **"Perform a new installation of SQL Server 2022"** y luego clic en el botón **Next >** (siguiente) para continuar con el proceso.

<div style="text-align: center;">
  <img src="_images/paso_1_3.png" alt="Tipo de Instalación" width="70%">
</div>
<br>

4. En esta ventana debes aceptar los términos de la licencia y a continuación hacer clic en el botón **Next >**

<div style="text-align: center;">
  <img src="_images/paso_1_4.png" alt="Aceptar Licencia" width="70%">
</div>
<br>

5. **Extensiones de Azure para SQL Server:** Esta pantalla permite configurar la extensión de Azure para SQL Server, que es necesaria si deseas habilitar ciertas integraciones de Microsoft como **Defender for Cloud**, **Purview**, y **Azure Active Directory**. Sin embargo, si no tienes una cuenta de Azure o no necesitas estas funcionalidades, puedes continuar sin configurar esta extensión. Suponiendo que no tienes una cuenta en Azure, deshabilida el cuadro de verificación **Azure Extension for SQL Server** y haz clic en el botón **Next >**.

<div style="text-align: center;">
  <img src="_images/paso_1_5.png" alt="Extensiones de Azure" width="70%">
</div>
<br>

6. **Selección de características:** Si no estás seguro de qué características necesitas, puedes dejar los valores por defecto de esta ventana, sólo asegúrate que **Database Engine Services** esté activo. Las otras características pueden agregarse posteriormente si es necesario. Luego haz clic en el botón **Next >**.

<div style="text-align: center;">
  <img src="_images/paso_1_6.png" alt="Selección de Caraterísticas" width="70%">
</div>
<br>

7. **Configuración de la Instancia:** En esta pantalla, se define cómo será identificada la instancia de SQL Server que se está instalando. Una "instancia" es una instalación separada de SQL Server que puede operar de manera independiente en el mismo servidor.

    - Si no necesitas múltiples instancias, selecciona Default Instance. Esto simplifica el acceso a la base de datos y evita problemas de configuración.
    - Si planeas instalar varias instancias en el futuro, selecciona **Named Instance** e introduce un nombre único en el campo correspondiente (Por ejmplo, en éste caso nombramos la instancia VIRTA-MINTIC).
    - Verifica las instancias existentes en la lista para asegurarte de que no estás duplicando nombres o configuraciones.
    - Haz clic en el botón **"Next >"** para continuar.

<div style="text-align: center;">
  <img src="_images/paso_1_7.png" alt="Configuración de la Instancia" width="70%">
</div>
<br>

8. **Configuración del Servidor:** En esta pantalla del instalador de SQL Server 2022, se configuran las cuentas de servicio y las opciones de inicio para los servicios del servidor SQL. Simplemente hacemos clic en el botón **"Next >"**.

<div style="text-align: center;">
  <img src="_images/paso_1_8.png" alt="Configuración del Servidor" width="70%">
</div>
<br>

9. **Configuración del Motor de Base de Datos:** En esta pantalla se configuran las opciones de autenticación y administración del motor de base de datos SQL Server. Es un paso importante para garantizar un acceso seguro y adecuado a la base de datos.

    - Selecciona **Mixed Mode** y configura una contraseña segura para la cuenta **sa**. Esto será útil para crear scripts en Python que requieran autenticación SQL.
    - Asegúrate de que tu usuario actual esté en la lista de administradores de SQL Server.
    - Haz clic en **"Next >"** para continuar.

<div style="text-align: center;">
  <img src="_images/paso_1_9.png" alt="Configuración del Motor" width="70%">
</div>
<br>

10. **Culminación de la Instalación de la Nueva Instancia de SQL Server 2022:** Esta ventana indica que la instalación de SQL Server 2022 se ha completado con éxito, mostrando el estado final de las características instaladas.

<div style="text-align: center;">
  <img src="_images/paso_1_10.png" alt="Culminación de la Instalación" width="70%">
</div>
<br>

Haz clic en el botón **Close** para finalizar el asistente. Una vez cerrada la ventana, puedes proceder a configurar y utilizar la instancia recién creada.