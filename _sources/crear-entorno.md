# Configuración de Jupyter Notebook y Entorno de Python en VSCode

## Paso 1: Descargar e Instalar VSCode

1. Descarga VSCode desde https://code.visualstudio.com/.
2. Instala el programa siguiendo las instrucciones del instalador.

## Paso 2: Instalar Python

1. Descarga Python desde https://www.python.org/downloads/.
2. Durante la instalación:
    - Asegúrate de activar la opción Add Python to PATH.
    - Selecciona la instalación personalizada y marca pip para instalar el gestor de paquetes.

## Paso 3: Instalar la Extensión de Python y de Jupyter en VSCode

1. Abre VSCode.
2. Dirígete al menú de **Extensiones** en la barra lateral izquierda.
3. Busca Python en la barra de búsqueda.
4. Selecciona la extensión desarrollada por **Microsoft** y haz clic en **Install**.
5. Repite desde el paso 2 para la extensión de Jupyter.

<div style="text-align: center;">
  <img src="_images/paso_5_1.png" alt="Configuración VSCode">
</div>
<br>

## Paso 4: Crear un Entorno Virtual

1. Abre el terminal integrado en VSCode desde el menú **View > Terminal** o presionando Ctrl + ~ o.

<div style="text-align: center;">
  <img src="_images/paso_5_2.png" alt="Terminal Integrado">
</div>
<br>

2. Navega hasta tu carpeta de proyecto.

```bash
cd Actividad2
```
3. Ejecuta el siguiente comando para crear un entorno virtual:

```bash
python -m venv virtamintic
```
4. Activa el entorno virtual:
    - En Windows:
```bash
virtamintic\Scripts\activate
```
5. Verifica que el entorno virtual está activado revisando que (virtamintic) aparece al inicio de la línea en el terminal.

<div style="text-align: center;">
  <img src="_images/paso_5_3.png" alt="Terminal Integrado" width="70%">
</div>
<br>

## Paso 5: Instalar las Librerias Necesarias

1. Usa pip para instalar las librerías requeridas para tu proyecto. Por ejemplo:

```bash
pip install pyodbc pandas sqlalchemy matplotlib
```

## Paso 6: Abrir la Carpeta del Proyecto y Creación de un Jupyter Notebook

1. En VSCode Carga la carpeta del proyecto seleccionando **File > Open Folder...**

<div style="text-align: center;">
  <img src="_images/paso_5_4.png" alt="Cargar Carpeta del Proyecto" width="70%">
</div>
<br>

2. Ubica la ruta de la carpeta del proyecto.

<div style="text-align: center;">
  <img src="_images/paso_5_5.png" alt="Seleccionar Carpeta" width="70%">
</div>
<br>

3. Haz clic en el ícono **New File** del Explorador de **VSCode** para crear un nuevo Jupyter Notebook, asígnale un nombre con extensión `.ipynb`

<div style="text-align: center;">
  <img src="_images/paso_5_6.png" alt="Crear Notebook" width="70%">
</div>
<br>

4. Selecciona el kernel asociado al ambiente **virtamintic** creado anteriormente.

<div style="text-align: center;">
  <img src="_images/paso_5_7.png" alt="Selección Kernel" width="70%">
</div>
<br>

¡Ahora estás listo para interactuar de manera avanzada con SQL Server desde Python!