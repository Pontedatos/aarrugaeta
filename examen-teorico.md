# Exámen teórico de Periodismo de datos (18-05-2022)
**Nombre de la alumna:** Ane Arrugaeta Bergara

**Grupo:** Periodismo y Humanidades (Grupo 63)
## Preguntas cortas
### Preguntas obligatorias

**1. ¿Quién es Philip Meyer?**

Philip Meyer es quien inventa el término _periodismo de precisión_. Es un periodista estadounidense que mientras trabajó en The Miami Herald entre 1958 y 1962 llevó a cabo una investigación sobre el alto coste de los seguros escolares contra incendios y huracanes. Cruzando los nombres del consejo de funcionarios que establecían los precios con las empresas de seguros llegó a ver que el 65% de la financiación de las campañas electorales de los miembros del consejo estaban financiadas por estas empresas de seguros. Supone un hito para el periodismo de datos porque analiza una registro de información, lo trata y llega a ver, visualizar, una información que sin tratar estos datos en bruto no se podría conocer.

**2. ¿Quién fue Florence Nightingale?**

Fue una enfermera, escritora y estadística considerada pionera de la enfermería moderna. Durante la Guerra de Crimea entre 1853 y 1856 se percató de cómo los elementos y el entorno que envolvían a los heridos influía en el desarrollo de su enfermedad y de la mortalidad. Identificó distintas variables, como el ruido, la ventilación, la limpieza del agua, la luz, la limpieza general… que eran determinantes en la evolución de los pacientes. Se la considera precedente o punto de partida del periodismo de datos porque lo que hace es observar toda una serie de variables, datos del entorno desestructurados, analizarlos y llegar a una hipótesis. Es un poco lo que plantea el periodismo de datos, pero a través de datos recogidos en registros electrónicos. 

### Preguntas Bloque C

**1. ¿Cómo creamos un directorio? Si quisiéramos crear dos directorios, ¿podríamos hacerlo de una sola vez? Razona tu respuesta.**

El comando que utilizamos para crear un directorio a través de la terminal es `mkdir nombre-directorio` y si queremos crear dos directorios a la vez simplemente tendremos que hacer `mkdir nombre-directorio1 nombre-directorio2`. El comando que manda ejecutar la acción es `mkdir`, mientras que `nombre-directorio`sería el argumento sobre el que se ejerce la acción, en este caso crear el directorio que se llamará así.

**2. ¿Cómo vemos los archivos y directorios ocultos al listar un directorio?**

Para ver los archivos y directorios ocultos hacemos `ls -a` y si queremos verlos en detalle `ls -la`.

**3. ¿En qué se diferencian las rutas absolutas de las relativas? Pon ejemplos de ambas.**

Una ruta absoluta es aquella en la que se representa la ruta completa del recurso. Es decir, se parte desde el directorio raíz hasta llegar al recurso, por ejemplo: `/home/zeokat/vozidea/file.txt.` Una ruta relativa, en cambio, solamente muestra parte de la ruta, que en el caso del ejemplo anterior sería `vozidea/file.txt`.

**4. ¿Qué función tiene la almohadilla en Markdown y en un programa de la shell? Razona tu respuesta.**

La almohadilla en Markdown sirve para hacer encabezamientos. Es decir, marcar títulos y subtítulos. En cambio, en la shell tiene una función totalmente distinta, indica que la línea que sigue a la almohadilla está comentada, por lo que toda la línea que la sigue se pasa por alto, el programa no la va a leer. 

**5. ¿Qué es una API? Pon algún ejemplo.**

API significa _Access Programming Interface_ o interfaz de programación de acceso y son los códigos que se utilizan para comunicarse con una web. HTTP es una de las APIs más conocidas y utilizadas que existen. 

**6. ¿Qué es Markdown?**

Markdown es un lenguaje para la edición de textos en aplicaciones informáticas. Se creó buscando la sintaxis más sencilla posible que permitiera hacer lo más legible posible el lenguaje informático. Además, Markdown es un conversor de su propia sintaxis a HTML, que por ejemplo en GitHub, a través de Jekyll, nos permite visualizar un documento en `markdown` como `HTML`. 

**7. ¿Que significa TSV?**

Significa _Tab Separated Values_ y es un tipo de archivo _*SV_ en el que el separador es el caracter del tabulador. 

## Pregunta de desarrollo

**3. ¿Qué formatos de datos hay?**

Durante el desarrollo de la asignatura hemos visto tres tipos de formatos de datos: 
- _*SV_ o valores separados por cualquier valor.
- _JSON_ o _JavaScript Object Notation_, notación de objetos JS.
- _XML_ o _eXtensible Markup Language_, lenguaje de marcas extensible.
El primero de ellos es el más sencillo de todos y el que más abunda en los diferentes portales de datos abiertos. Los valores, que pueden estar separados por distintos separadores (aunque el más habitual es la `,`), se visualizan como tablas dividadas por filas y por columnas. Por otro lado, tenemos los _JSON_ que son ficheros que utilizan la sintaxis de _JS_. Permiten más complejidad que los _*SV_, pero por esta misma razón también son más complicados de leer. Es el formato de dato que mejor funciona en aplicacinoes web. Por último está _XML_, que son el tipo de fichero que, por ejemplo, genera el programa excel. Se utiliza mucho en la adminsitración pública porque permite crear elementos HTML propios. Sin embargo nosotras no hemos trabajado con este tipo de datos por su complejidad.
