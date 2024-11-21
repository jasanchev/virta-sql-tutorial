# Creación de un Login con SQL Authentication par Verificar el Servicio Conectado

```{admonition} Importante
:class: note
Para crear un login SQL Authentication que permita verificar el servicio conectado, se debe tener activa una instancia de **Microsoft SQL Server Management Studio (SSMS)**.
```
Este procedimiento permite crear un login para autenticación SQL en Microsoft SQL Server Management Studio (SSMS). Esto es útil para verificar que el servicio de SQL Server está correctamente configurado y aceptar conexiones externas.

## Pasos para Crear un Login:

1. **Abrir SSMS y conectar el servidor:**

- Inicia Microsoft SQL Server Management Studio.
- Conéctate al servidor donde deseas crear el login  utilizando el método de autenticación configurado (Windows Authentication o SQL Authentication)

2. **Navegar al nodo de seguridad:**

- En el panel izquiero (Object Explorer), expande el nodo del servidor conectado.
- Haz clic derecho en la carpeta **Security** y selecciona la opción **New > login...**.

<div style="text-align: center;">
  <img src="_images/paso_2_1.png" alt="Creación Login en SSMS">
</div>
<br>

3. **Configurar los detalles del nuevo login:**

- **En la ventana "Login - New", configura los siguientes campos:**
    - **Login Name:** Escribe un nombre para el nuevo login. Por ejemplo: `equipo10`.
    - **Authentication:** Selecciona **SQL Authentication**.
    - **Contraseña:** Especificar una contraseña para el usuario y confirma la misma contraseña.
    - Desmarca la casilla **Enforce password policy** si no deseas aplicar políticas de contraseña en este login.

<div style="text-align: center;">
  <img src="_images/paso_2_2.png" alt="Definir Nombre" width="70%">
</div>
<br>

4. **Asignar permisos y configuraciones adicionales:**

- Ve a la pestaña **Server Roles** y asigna roles de servidor, si es necesario. Por ejemplo, puedes asignar el rol de `sysadmin` para permisos administrativos.
- En la pestaña **User Mapping**, selecciona la base de datos a la que este usuario tendrá acceso y asigna roles específicos de la base de datos.

<div style="text-align: center;">
  <img src="_images/paso_2_3.png" alt="Server Roles" width="70%">
</div>
<br>

5. **Guarda los cambios:**

- Haz clic en el botón **OK** para finalizar la creación del nuevo login.

6. Cierra la sesión actual en SSMS

<div style="text-align: center;">
  <img src="_images/paso_2_4.png" alt="Cerrar sesión">
</div>
<br>

vuelve a conectarte al servidor utilizando el nombre de usuario y la contraseña del nuevo login creado.

<div style="text-align: center;">
  <img src="_images/paso_2_5.png" alt="Volver a conectar">
</div>
<br>

Si la conexión es exitosa, el login fue creado correctamente y está operativo.

<div style="text-align: center;">
  <img src="_images/paso_2_6.png" alt="Conexión exitosa">
</div>
<br>
