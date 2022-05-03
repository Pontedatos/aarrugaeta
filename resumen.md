# Resumen de los contenidos de la asignatura
Este archivo contiene un resumen de los conocimientos adquiridos a lo largo del cuatrimestre en la asignatura Periodismo de datos. Para poder explicarlos de la forma más clara posible hemos decidido organizar la exposición de lo aprendido continuando el orden que seguimos durante el desarrollo de las clases. 

## 1. Instalación de un programa de emulación de la terminal
Como en mi caso, mi sistema operativo es Windows he tenido que instalar dos programas de emulación de la terminal: [WSL] ](https://docs.microsoft.com/es-es/windows/wsl/) y [Cygwin]( https://www.cygwin.com/).  En la primera clase práctica solamente instalamos WSL y Cygwin fue instalado algunas semanas más tarde, pero por la similitud de los procesos los voy a explicar de manera conjunta. 

### WSL: Instalación de Ubuntu
En el caso de *WSL*, la instalación la hicimos a través de la PowerShell de Windows, la terminal desarrollada por Microsoft. Para hacerlo, tuvimos que abrir una sesión como administradores, y ejecutar el comando `wsl --install -d Ubuntu`. Una vez se ha instalado reiniciamos el ordenador y accedimos al programa. Al iniciarlo por primera vez nos pidió que creáramos un usuario y una contraseña para el usuario UNIX, que es el usuario administrador. 

### Cygwin: Unix en Windows
Para instalar *Cygwin*, tuvimos que descargar de su [web](https://www.cygwin.com/) su instalador, ya que no es una herramienta nativa de Microsoft.

Cuando ejecutamos el instalador, lo primero, nos preguntó desde dónde queríamos instalarlo, y seleccionamos la opción «Instalar desde Internet». Lo siguiente fue elegir dónde instalar el programa y lo hicimos en la ruta que se establece por defecto. A continuación, elegimos el _mirror_, que al estar nosotros en España escogimos un dominio `.es`. Tras realizar esto tuvimos que instalar los paquetes `libcurl4`, `wget`, `ca-certificates-letsencrypt`, `lynx`, `nano` y `openssl`.

## 2. Configuración del programa
Una vez instalados los programas configuramos algunas cuestiones para facilitarnos su uso. 

### Establecer alias
Lo primero que hicimos fue crear un alias en la terminal para ahorrarnos escribir toda la ruta de nuestra carpeta. Es decir, para que en vez teclear, por ejemplo, `cd ‘/mnt/c/Users/usuaria/Documentos/Apuntes/Periodismo de Datos/’`, tecleáramos en nuetro caso, `micasa`, y el programa nos llevara ya a esta ruta.  Para ello, editamos el archivo de configuración de Bash. Desde la línea de comandos, escribimos el comando `echo` y enviamos la salida con `>>` al final del archivo `.bashrc`: `echo “alias micasa=“cd ‘/mnt/c/Users/usuario/Documentos/Apuntes/Periodismo de Datos/’” >> $HOME/.bashrc`. Con esto cada vez accedamos a Ubuntu o a Cygwin al teclear el alias en la terminal nos lleva de manera inmediata a la ruta asignada. Para ver el archivo de configuración del alias lo podemos hacer con `cat $HOME/.bashrc` y para editarlo con `nano $HOME/.bashrc`.

### Cambiar la home de Cygwin a la de Windows
En Cygwin cambiamos la ruta de nuestra “casa” de nuestro usuario para que fuera la misma que la de Windows. Para ello editamos el archivo «hogar» o «casa» de nuestro usuario para que sea la de Windows. Editamos el archivo `nsswith.conf` con `nano`: `nano /etc/nsswith.conf` poniendo `db_home: windows` al final del archivo. Guardamos (CTRL + O) y cerramos (CTRL + X) para que se conserven los cambios. Para comprobar que funcionaba al volver a abrir el programa escribimos `pwd` a lo que nos debía contestar Cerramos Cygwin y volvemos a entrar para que se actualice. Comprobamos con `pwd`: `/cygdrive/c/Users/usuario`. 

### Configurar git
A continuación, tuvimos que configurar nuestro usuario de GitHub en la terminal, ya que esto permite vincular los cambios que se hacen en nuestros archivos locales con nuestro repositorio en línea. Para ello, en nuestra terminal, escribimos `git config --global user.name nuestrousuario` (en mi caso “aarrugaeta”), y luego `git config --global user.email correogithub` (siendo el correogithub el correo utilizado para crear la cuenta en GitHub). 

## 3. Configuración de un programa de edición de texto
También hemos aprendido a editar los textos de nuestros archivos directamente desde la terminal. Para ello utilizamos nano, el editor de texto de Linux. Antes de empezar a utilizarlo como tal lo configuramos para que el texto se adaptara a la resolución de la pantalla y que apareciera el número de líneas. Esto lo hicimos ejecutando `nano $HOME/.nanorc` y poniendo lo siguiente en el editor: 

`# Ajustar el texto a pantalla`

`set softwrap`

`# Numerar las líneas`

`set linenumbers`

Con Cygwin el método fue diferente. Copiamos directamente el archivo de configuración de `nano`  con `cp /etc/nanorc .nanorc`, y lo editamos: `nano .nanorc`. Una vez dentro buscamos con CTRL + W “linenumbers” y en la línea (`# set linenumbers`) le quitamos la #. Volvemos a buscar con CTRL + W “softwrap” y en la línea (`# set softwrap`) le quitamos la #. 

## 4. Configuración y funcionamiento de un gestor de paquetes/programas del emulador de la terminal
El gestor de paquetes de Ubuntu es `apt`y viene ya incorporado al programa. El de Cygwin es `apt-cyg` y hay que instalarlo. Para ello ejecutamos `lynx -source rawgit.com/transcode-open/apt-cyg/master/apt-cyg > apt-cyg` y luego `install apt-cyg /bin`. El gestor de paquetes nos permitirá instalar herramientas en un futuro, como lolcat.

## 5. Consultar la versión del lenguaje de SHELL utilizado
Para comprobar la versión del lenguaje de Shell utilizado usamos la variable de entorno `$0`, que la consultaremos con `echo $0` y nos devolverá la Shell utilizamos, que tanto para Cygwin como para WSL es Bash. Para comprobar la versión de Bash hay dos opciones: la primera, usar la variable de entorno `$BASH_VERSION`, con `echo`; la segunda, mediante el propio `bash`, especificando la opción `--help`: `bash --help`. 

## 6. Consultar el valor de la variable de entorno PATH
Para concocer la variable de entorno `$PATH`, lo hacemos con `echo $PATH`. La terminal nos devuelve las rutas en las que se encuentran instalados los programas que puede ejecutar la terminal. 

## 7. Comandos utilizados y ejemplos
*Los comandos tienen la siguiente estructura: comando / opciones / argumentos*

- `ls`: listar un directorio (ver qué archivos y carpetas hay en la ruta en la que estamos). Si queremos ver el directorio actual, no hace falta especificar la ruta. 
- `cd`: acceder a un directorio en específico. Si escribimos solo `cd` vamos al directorio raíz. `cd ..`, nos sube un directorio. Con `cd -` nos lleva al último sitio en el que estábamos.
- `pwd`: indica en qué ruta estamos actualmente.
- `mkdir`: crea una carpeta nueva especificando su nombre.
- `cat`: previsualizar el archivo en la propia terminal. Por ejemplo, `cat README.md`. 
- `mv`: mueve o corta las carpetas o archivos de sitio, pero también sirve para renombrarlos. Si queremos mover la carpeta de periodismo de datos (`/mnt/c/Users/usuario/Documentos/periodismo-de-datos`) a otro lado, escribimos: `mv /mnt/c/Users/usuario/Documentos/periodismo-de-datos /mnt/c/Users/usuario/Documentos/Apuntes/` . Como vemos, después de `mv` escribimos la ruta de origen y lo siguiente es el directorio de destino. Si queremos renombrar, escribimos `mv periodismo-de-datos nuevo-nombre`.
 - `cp`: copia carpetas o archivos. La sintaxis es la misma que para `mv`. 
 - `nano` → editar textos. Para editar con `nano`, tenemos que escribir `nano` seguido del nombre del archivo. Si estamos en la carpeta de la asignatura, por ejemplo, escribimos `nano README.md`. Para guardar CTRL + O, y para salir CTRL + X.
 - `echo`: sirve para que la terminal nos devuelva un texto. Si queremos que la terminal nos diga Hola, escribimos `echo Hola`. 
- `&&`: ejecutar dos comandos en una misma línea o de una vez. Por ejemplo, si queremos crear una carpeta y luego situarnos dentro, escribimos: `mkdir carpeta && cd carpeta`.
- `|`: pasar de una salida a una entrada. Por ejemplo, si queremos hacer un `cat` para leer un archivo pero visualizarlo con `less`, escribimos `cat README.md | less`.
- `man`: nos dice qué hace un comando y nos muestra todas las opciones posibles. Por ejemplo, si queremos saber qué hace `ls` y qué opciones podemos usar hacemos `man ls`. Por defecto, utiliza el visor `| more`, que para avanzar por el documento tenemos que ir clickando en la barra espaciadora, y para salir pulsar la tecla `q`. También está disponible `| less` (`man ls | less`)
- `env`: visualizar en pantalla todas las variables de entorno. Si lo usamos con `| less`, es un visor más ameno porque son demasiadas variables y no caben en la pantalla: `env | less`. 
  - `touch`: crea un archivo nuevo. Por ejemplo, si queremos crear un README.md en nuestra carpeta, escribimos `touch README.md` y ya está creado.
  - `tree`: como `ls` pero con más opciones. Con `tree -L 1` le decimos cuántos niveles queremos ver. También podemos poner `tree -L 2` o `tree -L 3`, según el nivel de detalle (mayor el número mayor el grado de detalle).
  - `rm`: eliminar archivos o directorios. Hay que tener cuidado porque los elimina de forma definitiva, los archivos no van a la papelera.
  - `wget`: descargar un archivo/contenido de una web. Tenemos que copiar el enlace de lo que nos queramos descargar. 
  - `curl`: igual que wget pero con más opciones.

