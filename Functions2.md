# Práctica 08. Funciones. Paso de parámetros. Parámetros en línea de comandos.

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Desarrolle programas sencillos en C++ que utilicen funciones y todos los tipos de sentencias estudiadas
* Sea capaz de organizar el código fuente de sus programas en C++ en diferentes ficheros siguiendo la
  organización habitual para este tipo de proyectos
* Sepa automatizar la compilación de sus programas en C++ utilizando la herramienta `make`
* Conozca el funcionamiento básico de las herramientas `git` y GitHub

### Rúbrica de evaluacion de esta práctica
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* El alumnado ha de acreditar conocer los conceptos expuestos en el material de referencia de esta práctica.
* El alumnado ha de acreditar que ha realizado todos los ejercicios propuestos, así como ser capaz de desarrollar otros similares.
* Ha de acreditar que es capaz de escribir un fichero Makefile para automatizar el proceso de compilación de sus programas.
* El código que escriba ha de estar escrito de acuerdo a los estándares definidos en la Guía de Estilo de Google para C++.
* Todos los identificadores que utilice en su programa (constantes, variables, etc.) deberán ser
  siempre significativos. No utilice nunca identificadores de una única letra, tal vez con la excepción de las
  variables que utilice para iterar en un bucle.
* Antes de su ejecución, todos los programas que desarrolle, deben imprimir en pantalla un
  mensaje indicando la finalidad del programa así como la información que precisará del usuario para su correcta ejecución.
* Todo el código que el alumnado presente para su evaluación ha de estar alojado en un repositorio privado de
  GitHub

### Trabajo previo: introducción a Git y GitHub
GitHub es un un servicio en la nube con una interfaz web que ayuda a los desarrolladores a almacenar y administrar el código
fuente de sus programas así como a llevar un registro y control de cualquier cambio que se realice sobre ese código. 
Git es un sistema distribuido de control de versiones.
En Git todo el código y su historial de cambios se encuentran disponibles en el ordenador del desarrollador.
En la web se puede encontrar multitud de tutoriales sobre el uso de GitHub y git y
[este](https://www.diegocmartin.com/tutorial-git/), por ejemplo puede ser un buen punto de comienzo para estudiar
ambas herramientas.
Esta [guía simple](https://rogerdudler.github.io/git-guide/) también puede servir para un uso inicial de ellas.

A la hora de estudiar estas herramientas ha de tener en cuenta que el uso que en esta asignatura se va a
realizar de las mismas es básico: inicialmente cada estudiante va a utilizar git/GitHub exclusivamente para almacenar el
código fuente de cada una de las prácticas que desarrolla. 
No se pretende que compartan código a través de git ni que colaboren en el desarrollo de código usando estas
herramientas.
También ha de tener en cuenta que un entorno de desarrollo colaborativo de programas es el escenario más
habitual y en el que estas herramientas muestran su relevancia.

Para crear un repositorio de código hay básicamente dos opciones: crear uno partiendo de cero o bien clonar
(copiar) un repositorio (que ha de ser público) del que se conozca su dirección.
En esta práctica se va a optar por la primera aproximación: crear un repositorio propio para alojar los
programas de esta práctica.

Comience su trabajo con GitHub utilizando la cuenta que creó en la primera práctica de la asignatura.
Acceda a su cuenta y siga 
[estas instrucciones](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/create-a-repo)
para crear un repositorio en su cuenta de GitHub.
Elija `IB-2020-2021-Practica8-Funciones` como nombre para su repositorio (en lugar de `hello-world`).
Haga que su repositorio sea privado.
El repositorio que ha creado no contiene programas y apenas contendrá un fichero `README.md`.
GitHub utiliza profusamente ficheros de texto con formato Markdown.
El fichero `README.md` (así lo indica su extensión) es un fichero de texto en formato Markdown.
Markdown es un lenguaje de marcas que permite aplicar formato (negrita, itálicas, imágenes, listas, etc.) a un
fichero de texto.
Este texto que está Ud. leyendo está escrito en un fichero con formato Markdown.
El formato fue ideado para elaborar textos cuyo destino iba a ser la web con más rapidez y sencillez que si se
empleara HTML.

No es neceario que aprenda Markdown en esta asignatura, pero si tiene interés por ello, la referencia 
[Qué es Markdown, para qué sirve y cómo usarlo](https://www.genbeta.com/guia-de-inicio/que-es-markdown-para-que-sirve-y-como-usarlo)
puede servirle de introducción.
[Este tutorial](https://guides.github.com/features/mastering-markdown/) es útil para un
conocimiento más profundo y por último 
[StackEdit](https://stackedit.io/) es un editor de Markdown con una interfaz web, que puede resultarle útil.

Antes de comenzar a trabajar ahora con Git, añada la clave ssh de su máquina virtual Linux a su cuenta GitHub.
Esta tarea es posible que la realizara en la primera práctica de la asignatura, pero en caso contrario ha de
hacerlo Ud. ahora siguiendo 
[estas instrucciones](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account).
En esa página siga el enlace 
[Generated a new SSH key and added it to the ssh-agent](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
para generar una clave ssh en su máquina virtual (también puede hacer lo mismo con otros sistemas Linux con
los que trabaje habitualmente, como su instalación de VirtualBox o WSL).
También la sección "Trabajando con Git en Remoto" del
[tutorial de Diego Martín](https://www.diegocmartin.com/tutorial-git/) puede serle de ayuda para
configurar la clave ssh.

Una vez configurada su clave ssh y creado su repositorio en GitHub, siga 
[estas otras instrucciones](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/cloning-a-repository)
para clonar el repositorio que ha creado en GitHub usando `git`.
Para ello, en su máquina virtual linux de la asignatura acceda al directorio en el que esté organizando sus
prácticas y ejecute los comandos:
```
$ mkdir practica08-Funciones
$ git clone git@github.com:username/IB-2020-2021-Practica8-Funciones.git practica08-Funciones
```
La dirección de su repositorio en GitHub (en el comando anterior es
`git@github.com:username/IB-2020-2021-Practica8-Funciones.git`) ha de obtenerla (cópiela de allí) en su cuenta de GitHub tal como
se indica en las instrucciones anteriores.
De las tres opciones disponibles (HTTPS, ssh, GitHub Cli) utilice la opción ssh.

A continuación ya está todo listo para que acceda al directorio de trabajo de esta práctica (el directorio que
en este documento se ha llamado `practica08-Funciones`) y desarrolle en él todos los ejercicios de esta
práctica.
Resulta recomendable que dentro de ese directorio cree subdirectorios para cada uno de los ejercicios.
Ahora todo el trabajo ha de realizarlo de la forma habitual, editando sus programas con VSC dentro de ese
directorio y realizando todas las pruebas que considere oportunas.
Después de cada sesión de trabajo recuerde "subir" sus cambios a la nube de GitHub.
Para ello, la secuencia habitual de comandos `git` a ejecutar suele ser la siguiente:
```
$ git pull
$ git add .
$ git commit -m "Texto alusivo a los cambios realizados"
$ git push
```
* El primero de los comandos anteriores, `git pull` es siempre conveniente porque de ese modo se asegura que se descarga al
ordenador la última versión del código que esté alojado en la nube de GitHub.
* `git add .` actualiza el índice de git con el contenido del directorio actual (nótese el punto -directorio
  actual, el de trabajo- en el comando).
* `git commit` registra el el repositorio los cambios que se hayan realizado. A esos cambios les asocia el
mensaje de texto que aparece en el comando. 
* `git push` Actualiza (sube los cambios a la nube) el repositorio en la nube.

Explicaciones más detalladas de este "workflow" las puede hallar en el primer
[tutorial](https://www.diegocmartin.com/tutorial-git/)
que se propone en este documento.


### Ejercicios 
Al realizar los siguientes ejercicios cree dentro del repositorio de esta práctica un directorio diferente
para cada uno de los ejercicios.
Ponga a cada uno de esos directorios nombres significativos.
Haga que cada uno de sus programas conste de 3 ficheros:
* Un fichero `mi_programa.cc` (programa principal) que contendrá la función `main` e incluirá el fichero de cabecera `funciones.h`
* El fichero `funciones.h` que contendrá las declaraciones de las diferentes funciones que se utilizan en el
  programa principal para resolver el ejercicio en cuestión.
* El fichero `funciones.cc` que contendrá el código (definiciones) de las funciones declaradas en el fichero
  de cabecera.

Modifique los nombres de los ficheros que aquí se proponen para adaptarlos al ejercicio en cuestión.

La compilación de los programas correspondientes a cada ejercicio se automatizará con un fichero Makefile para
cada ejercicio.

1. Escriba un programa `prime.cc` que tome por línea de comandos un número natural, N e imprima en pantalla
el n-ésimo número primo.
Si se ejecuta por ejemplo,

```
$ ./prime 5
11
```
El programa imprime 11, puesto que és es el quinto número en la secuencia de números primos.

2. Escriba un programa `difference_of_squares.cc` que tome como parámetro pasado por línea de comandos un
número natural N, e imprima en pantalla la diferencia entre el cuadrado de la suma de los primeros N números
naturales y la suma de los cuadrados de esos mismos números.

El cuadrado de la suma de los 10 primeros números naturales es (1 + 2 + ... + 10)<sup>2</sup> = 55<sup>2</sup> = 3025.

La suma de los cuadrados de los primeros diez números naturales es 1<sup>2</sup> + 2<sup>2</sup> + ... + 10<sup>2</sup> = 385.

Por tanto la diferencia entre el cuadrado de la suma y la suma de cuadrados es 3025 - 385 = 2640.

Se muestra a continuación un ejemplo de la ejecución del programa:
```
$ ./difference_of_squares 10
2640
```

Haga que si su programa se ejecuta sin pasar ningún parámetro por la línea de comandos, el programa finalice
su ejecución imprimiendo en pantalla un mensaje explicativo de su funcionamiento:
```
$ ./difference_of_squares 
difference_of_squares: falta un número natural como parámetro
Pruebe 'difference_of_squares --help' para más información.
```
si el usuario pasa como único parámetro la opción `--help`, el programa finalizará su ejecución e imprimirá
por pantalla un texto explicativo de su finalidad y comportamiento.

3.- Desarrolle un programa `vector_statistics.cc` que tome como parámetro por línea de comandos un tres
números naturales N, M, P, y cree un vector de N componentes de tipo `double` cuyos valores hayan sido generados
aleatoriamente en el rango `[M, P]`.
El programa dispondrá de funciones que calculen:
* La media
* La desviación estándar
* El máximo
* El mínimo
de los valores almacenados en el vector.

4.- Desarrolle un programa `string_statistics.cc` que inicialice un vector constante de 10 componentes de tipo
`std::string`, es decir, un vector con 10 cadenas de texto.
Elija Ud. mismo las cadenas que utiliza para inicializar el vector.
Haga que el programa imprima para cada una de las cadenas de texto del vector:
* La longitud de la cadena.
* El primer carácter de la cadena.
* El último carácter de la cadena.
* Sí/No la cadena en cuestión contiene el texto `abracadabra`.


### Referencias
* [Tutorial de Git. Manual básico con ejemplos](https://www.diegocmartin.com/tutorial-git/) 
* [Qué es Markdown, para qué sirve y cómo usarlo](https://www.genbeta.com/guia-de-inicio/que-es-markdown-para-que-sirve-y-como-usarlo)
* [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
* [StackEdit](https://stackedit.io/)
* [git - the simple guide](https://rogerdudler.github.io/git-guide/)
* [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
