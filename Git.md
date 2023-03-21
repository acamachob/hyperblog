**Control de versiones Git**
*-*Diseñado por Linus Torvalds.
*-*Funciona como una línea de tiempo que permite regresar a momentos específicos del código.
*-*git init empezar la carpeta repositorio, donde se van a guardar los cambios.
*-*Al instalar Git, al final nos da la opción de abrir una consola similar a la que se encuentra en linux.
*-*Git nos permite editar texto plano.

**Línea de comandos**
*-*mkdir: Crea una carpeta o directorio nuevo en Windows.
_-_ cd + nombre de la carpeta: Para ingresar a alguna carpeta.
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
_-_ git config --global: Configurar los usuarios.
*-*git log + nombre del archivo: Visualizar los cambios que se han generado.
*-*git_show + nombre del archivo: Ver los cambios que se han realizado.
*-*Letra Q: Para salir de lo que muestra la consola en git show.
*-*git commit -am "Mensaje": Para agregar y guardar el mensaje de una vez, sin necesidad de hacer add y luego commit.

**Crear un repositorio**
*-*Ubicarse en la carpeta principal de los archivos y escribir git init + enter.
*-*La carpeta está oculta, pero aparece un archivo .git, que es donde se van a generar los cambios.

**Estado de un archivo**
*-*El staging es el lugar donde se guardan temporalmente los cambios, para luego ser llevados definitivamente al repositorio. El repositorio es el lugar donde se guardan todos los registros de los cambios realizados a los archivos.
*-*Para iniciar un repositorio, o sea, activar el sistema de control de versiones de Git en tu proyecto, solo debes ejecutar el comando git init.
_-_¿Qué es el área de staging?:El área de staging se puede ver como un limbo donde nuestros archivos están por ser enviados al repositorio o ser regresados a la carpeta del proyecto.
_-_¿Qué es git init?: git init es el comando que activa git en nuestro proyecto creando un espacio en memoria RAM llamado staging y una carpeta .git. Este comando se encargará de dos cosas: primero, crear una carpeta .git, donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; segundo, crear un área que conocemos como staging, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).

**Ciclo básico de un trabajo en Git**
*-*Cómo funciona el staging y el repositorio: ciclo básico de trabajo en git: El flujo de trabajo básico en git es algo así:
*-*Modificas una serie de archivos en tu directorio de trabajo.
*-*Preparas los archivos, añadiéndolos a tu área de preparación (staging).
*-*Confirmas los cambios (commit), lo que toma los archivos tal y como están en el área de preparación y almacena esa copia instantánea de manera permanente en tu directorio de git.

*-*Veamos a detalle las 3 secciones principales que tiene un proyecto en git.
*-*Working directory: El working directory es una copia de una versión del proyecto. Estos archivos se sacan de la base de datos comprimida en el directorio de git y se colocan en el disco para que los puedas usar o modificar.
*-*Staging area: Es un área que almacena información acerca de lo que va a ir en tu próxima confirmación. A veces se le denomina índice (index).
_-_.git directory (repository): En el repository se almacenan los metadatos y la base de datos de los objetos para tu proyecto. Es la parte más importante de git (carpeta .git) y es lo que se copia cuando clonas un repositorio desde otra computadora.

**Ciclo de vida o estados de los archivos en git**
*-*Cuando trabajamos con git, nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados, pero lo estudiaremos más adelante):
*-*Archivos tracked: Son los archivos que viven dentro de git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos git add y git commit.
*-*Archivos staged: Son archivos en staging. Viven dentro de git y hay registro de ellos porque han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando git commit.
*-*Archivos unstaged: Entiéndelos como archivos “tracked pero unstaged”. Son archivos que viven dentro de git pero no han sido afectados por el comando git add ni mucho menos por git commit. Git tiene un registro de estos archivos, pero está desactualizado, sus últimas versiones solo están guardadas en el disco duro.
*-*Archivos untracked: Son archivos que NO viven dentro de git, solo en el disco duro. Nunca han sido afectados por git add, así que git no tiene registros de su existencia.
*-*Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: staged y untracked. Esto pasa cuando guardas los cambios de un archivo en el área de staging (con el comando git add), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de staging.

**Comandos para mover archivos entre los estados de Git**
*-*Estos son los comandos más importantes que debes conocer:
*-*Git status: git status nos permite ver el estado de todos nuestros archivos y carpetas.
*-*Git add: git add nos ayuda a mover archivos del untracked o unstaged al estado staged. Podemos usar git nombre-del-archivo-o-carpeta para añadir archivos y carpetas individuales o git add -A para mover todos los archivos de nuestro proyecto (tanto untrackeds como unstageds).
*-*Git reset HEAD: Nos ayuda a sacar archivos del estado staged para devolverlos a su estado anterior. Si los archivos venían de unstaged, vuelven allí. Y lo mismo se venían de untracked.
*-*Git commit: Nos ayuda a mover archivos de unstaged a tracked. Esta es una ocasión especial, los archivos han sido guardados o actualizados en el repositorio. Git nos pedirá que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento m para escribirlo (git commit -m "mensaje").
*-*Git rm: Este comando necesita alguno de los siguientes argumentos para poder ejecutarse correctamente:
*-*git rm --cached: mueve los archivos que le indiquemos al estado untracked.
*-*git rm --force: elimina los archivos de git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

**AL trabajar con otras personas y actualizar el repositorio remoto**
*-*Git clone:
*-*Se usa en vez de git init.
*-*Trae los archivos al repositorio remoto a través de la url del repositorio.
*-*Se trae una copia del master al directorio local de trabajo y crea la base de datos de los cambios históricos al repositorio local, es decir, que al clonarlo, deja los cambios en Staging.
*-*Seguimos haciendo git add y git init para agregar los cambios al repositorio local.
*-*Pero cuando se quieren enviar al servidor, se realiza _git push_.
*-*Se usa _git fetch_ para traer una actualización que alguien le hizo al repositorio y lo deja de manera local.
*-*Para unir esta actualización que alguien subió al servidor con la mia, se utiliza _git merge_
*-*Comando _git pull_ fusiona los conceptos de fetch y merge. De esa manera, tengo una copia actualizada de lo que pase en el repositorio.

**Ramas**
*-*Master es la rama principal y la que tiene toda la historia de commits.
*-*Commit más reciente es el HEAD.
*-*Crear una rama, básicamente es crear una copia del último commit. Estos cambios no lo va a ver la rama master, hasta que no se fusione.
*-*_git commit -am_ Funciona para añadir y hacer los cambios de una sola vez a los archivos. Solo para archivos a los que ya se le han hecho modificaciones add .
*-*_git log --stat_ Muestra la cantidad de cambios realizados.
*-*_git branch_ Crea una nueva rama.
*-*_git checkout + nombre rama_ Para entrar a la rama o devolverme a la rama.
*-*_git merge_ Este comando siempre va a ocurrir en la rama en la que está, entonces por ejemplo, si quiero que quede en master, debo arrancar el comando merge allí.
*-*ls -al: Para ver las carpetas públicas y privadas.
*-*_git log --all_ Muestra todo lo que se ha hecho en las ramas que haya tenido el proyecto.
*-*_git log --all --graph_ Muestra todo lo que se ha hecho en las ramas que haya tenido el proyecto.

**Resolver un conflicto: Dos líneas iguales**
*-*Sintáxis del conflicto: Cuando aparecen signos >>>>>> o <<<<<<
*-*El conflicto que aparece, también puede ser leído en el blog de notas que se encuentra en la carpeta donde está el archivo.
*-*El conflicto, también se puede solucionar en VSC, dejando la opción que desee. Funciona como un control de cambios.

**Llaves públicas y privadas**
*-*Las llaves _ssh_ no son por proyecto, sino por persona.
*-*Cambiar el correo:
    *-*Si se desea cambiar el email que se tiene configurado en Github, primero a través de git bash, nos ubicamos en el usuario principal c/users/andeu.
    *-*Luego le colocamos el comando _git config --global user.email + el correo que quieras cambiar entre comillas_, ej: git config --global user.email "acamachob9009@gmail.com"
    *-*Una vez cambiado, podemos volver a ver el status de la configuración con _git config -l_ y debe aparecer el nuevo correo.
*-*Configurar las llaves:
    *-*Estar en el home, es decir en el usuario principal c/users/andeu.
    *-*Estando allí colocamos _ssh-keygen -t rsa -b 4096 -C "acamachob9009@gmail.com"_
    *-*En la parte donde nos dice donde quedará guardada, no se escribe nada.
    *-*Si queremos, le podemos colocar una contraseña adicional, cuando nos la pida, que por seguridad sería lo mejor.
    *-*Una vez se realiza el proceso, se genera una key fongerprint y una randomart image que confirma que la llave es de verdad.
    *-*Una vez creada la llave, el sistema operativo (Windows-Linux se configura igual) debe saber que la llave existe para poderla utilizar en el servidor, para esto se hace lo siguiente:
        *-*Revisar que el servidor de llave esté prendido para que se pueda hacer la conexión, esto se hace con el comando _eval $(ssh-agent -s)_ Al dar enter, debe salir Agent pid + un número que es distinto en cada máquina. Agent, el servidor corre; pid, identificador del proceso y número que indica que el proceso está corriendo.
        *-*Nota: Para no escribir toda la ruta de acceso en git bash, con el símbolo ~ que básicamente es una variable que tiene el nombre de mi carpeta home.
        *-*Agregar la llave privada al servidor: Con el comando _ssh-add ~/.ssh/id_rsa_. Luego me pide la contraseña y luegi al darle enter, me debe aparecer identy added o identidad añadida.
        *-*Cada laptop, debe tener una llave. No es buena idea compartir la llave en todos los equipos que tengamos, por temas de seguridad.
*-*Vincular el repositorio con mi github local
    *-*Ubicarnos en la carpeta donde tenemos el proyecto.
    *-*Decirle a github que vamos a agregar un origen remoto de nuestros archivos con el comando _git remote add origin https://github.com/acamachob/hyperblog.git.
    *-*Al colocar _git remote_, aparece origin.
    *-*Al colocar _git remote -v_, aparecen dos líneas que indican que podemos hacer fetch y push.
    *-*Por las actualizaciones de github, ya no es rama master sino main. Para cambiar la palabra, se utiliza el comando _git branch -m main_, ya con esto cambia a main y ahora si se puede realizar el push.
    *-*_git push origin main_ comando para enviar al servidor de github.
    *-*_git pull origin main --allow-unrelated-histories_ Para forzar la unión de archivos entre el remoto y el servidor github.
    *-*_NOTA_ Antes de realizar la actualización del local hacia el remoto, debo traerme los cambios del remoto hacia el local con el comando _git pull_

**Etiquetas**
*-*_git log --all --graph --decorate --oneline_ Comando para ver más a detalle las modificaciones que se han hecho en el proyecto. Para acortar el comando, se puede utilizar un alias, que consiste en colocar el nombre que le queremos colocar , seguido de un = y el comando entre comillas "git log --all --graph --decorate --oneline". Ejemplo: arbolito = "git log --all --graph --decorate --oneline". Al colocarlo en consola, el ya entiende que con colocar arbolito, ya funciona todo el comando.
*-*Todo programador puede crear sus propios alias.
*-*Tags para colocarlos delante de cada modificación y que sea más fácil acceder a ella. Se recomienda colocar v0.1 y así sucesivamente para indicar cada cambio. Ejemplo: git tag -a v0.1 -m "resultado de las primeras clases del curso" + el número largo que aparece en cada commit. git tag -a v0.1 -m "resultado de las primeras clases del curso" 3de9f50
*-*_git tag_ Muestra la lista de todos los tags.
*-*_git show-ref --tags_ Muestra a que número largo esta asociado y la versión.
*-*_git push origin --tag_ Para subir al servidor mi tag.
*-*_git tag -d dormido_ Para eliminar el tag localmente.
*-*Para eliminar el tag también del repositorio, con el comando _git push origin :refs/tags/dormido_ Esta es la referencia interna que borra el tag del servidor github.

**Enviar diferentes ramas al servidor**
*-*Cambiar de rama con _git checkout cabecera_.
*-*Para ver información completa de las ramas: _git show-branch_ ó _git show-branch --all_
*-*Comando _gitk_ me muestra en un programa aparte, la información de la evolución del proyecto. Es práctico, pero es recomendable aprender desde la consola.

**Pull request**
*-*Pull request es una funcionalidad de Github (en Gitlab llamada merge request y en Bitbucket push request), en la que un colaborador pide que revisen sus cambios antes de hacer merge a una rama, normalmente master (ahora conocida como main).

Al hacer un pull request, se genera una conversación que pueden seguir los demás usuarios del repositorio, así como autorizar y rechazar los cambios.

_Cómo se realiza un pull request_
*-*Se trabaja en una rama paralela los cambios que se desean git checkout -b <rama>.
*-*Se hace un commit a la rama git commit -am '<Comentario>'.
*-*Se suben al remoto los cambios git push origin <rama>.
*-*En GitHub se hace el pull request comparando la rama master con la rama del fix.
*-*Uno, o varios colaboradores revisan que el código sea correcto y dan feedback (en el chat del pull request).
*-*El colaborador hace los cambios que desea en la rama y lo vuelve a subir al remoto (automáticamente jala la historia de *-*los cambios que se hagan en la rama, en remoto).
*-*Se aceptan los cambios en GitHub.
*-*Se hace merge a master desde GitHub.
*-*Importante: Cuando se modifica una rama, también se modifica el pull request.

**Fork**
*-*Cuando una persona quiere colaborar con el proyecto, pero no está aceptado como colaborador, se usa el _fork_
*-*Fork, una copia del estado actual del proyecto y clonarlo como un proyecto mio. Solo aplica para proyectos públicos.
*-*Si el dueño del proyecto actualiza el proyecto, tengo que actualizar mi fork con esos cambios de proyecto.
*-*_git remote add upstream https://github.com/armandovv/Dasansor-Frontend.git_ crea otra fuente nueva para traer datos a la rama main. Para mantener las ramas del usuario principal con el secundario, quien le hará modificaciones al proyecto, pero no directamente al master.

**Git Ignore**
*-*No todos los archivos se deben subir al repositorio.
*-*Se crea un archivo dentro del proyecto, en la raíz del proyecto local, que se llame .gitignore, que es una lista donde se van a relacionar los archivos que no se van a subir o los que se van a ignorar.









