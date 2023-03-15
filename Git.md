**Control de versiones Git**
*-*Diseñado por Linus Torvalds.
*-*Funciona como una línea de tiempo que permite regresar a momentos específicos del código.
*-*git init empezar la carpeta repositorio, donde se van a guardar los cambios.
*-*Al instalar Git, al final nos da la opción de abrir una consola similar a la que se encuentra en linux.
*-*Git nos permite editar texto plano.

**Línea de comandos**
*-*mkdir: Crea una carpeta o directorio nuevo en Windows.
*-* cd + nombre de la carpeta: Para ingresar a alguna carpeta.
*-*cd ..: Para devolverme entre carpetas.
*-*touch: Crear archivos vacíos. Ej: vacio.txt
*-*cat nombre del archivo: Ver el contenido del archivo. cat vacio.txt
*-*history: Para ver el historial de comandos que he utilizado.
*-*rm: Eliminar un archivo.
*-*comando + --help: Muestra una guía del comando específico.
*-*ctrl + L: Limpiar la consola.
*-*pwd: Para saber en que carpeta estoy en el momento.
*-*ls -al: Para ver archivos ocultos.
*-*code: Para abrir VSC.
*-*git status: Estado del proyecto en el momento.
*-*git add: Añadir el archivo a la carpeta Git (Base de datos), para poder empezar a generar cambios.
*-*git rm --cached: Retirar el archivo de la base de datos. No funciona solo con git rm. No lo borra de la carpeta, solo de la base de datos de Git.
*-*git commit: Comando que envía los cambios al repositorio.
*-*git config: Para mostrar las configuraciones de git.
*-*Cuando hay un solo - se utiliza con letras, ej, ls -at. 
*-*Cuando son -- se utiliza con palabras, ej --global.
*-* git config --global: Configurar los usuarios.

**Crear un repositorio**
*-*Ubicarse en la carpeta principal de los archivos y escribir git init + enter.
*-*La carpeta está oculta, pero aparece un archivo .git, que es donde se van a generar los cambios.