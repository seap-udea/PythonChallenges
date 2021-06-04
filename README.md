# Python Challenges

Este repositorio contiene los proyectos realizados por los colaboradores autorizados que hacen parte de la iniciativa **Python Challenges**, que tiene por objetivo ofrecer un espacio en el cual estudiantes, profesionales e interesados en programación científica y ciencia de datos puedan aprender y recibir realimentación de manera colaborativa.

Se recomienda que cualquier persona interesada en colaborar tenga conocimientos básicos en las siguientes herramientas y tecnologías. No obstante, esto no se considera una limitante.

- Python v3.7 o superior
	- [Guía para principiantes](https://wiki.python.org/moin/BeginnersGuide)
	- [Guía para desarrolladores](https://devguide.python.org/)
- Comandos básicos de la terminal.
	- [UNIX/Linux terminal tutorial](http://www.ee.surrey.ac.uk/Teaching/Unix/)
- Conocimientos básicos de control de versiones usando git.
	- [Guía básica para utilizar git](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
	- [Git y Github | Curso Práctico de Git y Github Desde Cero](https://www.youtube.com/watch?v=HiXLkL42tMU)

A continuación, se presentan los elementos básicos a tener en cuenta para colaborar en el proyecto:

# 1. Instalación de git

Git es una herramienta para facilitar el desarrollo de software a través de control de versiones, permitendo a grupos o células de trabajo trabajar de manera colaborativa.  No se debe confundir git con GitHub, Github es una plataforma que permite mantener repositorios en la nube utilizando las características ofrecidas por git.

## Windows
Instalar y ejecutar el archivo disponible en el siguiente enlace: [git for Windows](https://git-scm.com/download/win "git for Windows")

## Linux/Unix
En sistemas operativos basados en Fedora ejecutar el siguiente comando en el terminal:

```bash
$ sudo dnf install git-all
```

En sistemas basados en Debian ejecutar el siguiente comando en el terminal:

```bash
$ sudo apt install git-all
```
## MAC OS X

Se recomienda instalar HomeBrew para la gestión de paquetes, para ello ejecutar el siguiente comando por terminal y refrescar la sesión:

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Después de instalar brew, ejecutar el siguiente comando:
```bash
$ brew install git
```

# 2. Antes de comenzar con el proyecto

Una vez instalado git, ejecutar el siguiente comando para evitar que ocurran errores y advertencias relacionadas a formato.

```bash
$ git config core.autocrlf true
```

En caso de usar git por primera vez, se debe configurar el usuario para acceder a los repositorios de interés. Para ello, se deben ejecutar los siguientes comandos:

```bash
$ git --global user.name = "mi_usuario"
$ git --global user.email = "mi_correo@host.xxx.xx"
```

La cuenta se puede verificar aplicando el siguiente comando:

```bash
$ git config --global -e
```

Adicionalmente, se recomienda agregar los siguientes alias para facilitar acciones que se realizan con frecuencia. Los alias descritos a continuación permiten resumir la visualización de logs y el estado de los cambios en el repositorio local.

```bash
$ git config --global alias.lg "log --oneline --decorate --all --graph"
$ git config --global alias.s "status -sb"
```

# 2. Guía de instalación del proyecto local

A continuación se presentan los pasos para clonar el proyecto:

-  **Crear un fork del proyecto principal:**  Dar click en la opción fork como se muestra a continuación

![](/img/CREATE_FORK.png)

Como resultado, se crea una copia del repositorio asociado a la cuenta de la persona que va participar. La URL tiene una estructura parecida a esto: 

https://github.com/mi_usuario/PythonChallenges

-  **Clonar proyecto:**  Ejecutar el siguiente comando apuntando al fork creado en el paso anterior:

```bash
$ git clone https://github.com/mi_usuario/PythonChallenges
```

- **Establecer el repositorio principal como upstream:**

```bash
$ git add upstream https://github.com/seap-udea/PythonChallenges
```

# 3. Estructura del proyecto

* **PC_X**: Directorio para cada challenge.
* **id_nombre_x**: Directorio en el cual cada participante realiza cambios **(Es mandatorio evitar modificar las carpetas de otros participantes)**

![](/img/ESTRUCTURA_PROYECTO.png)


# 3. Estrategia para el control de versiones

Para facilitar el trabajo colaborativo entre las personas que hacen parte de la iniciativa, se plantea el siguiente esquema de trabajo con el objetivo de evitar conflictos entre los participantes.

## Estrategia para descargar cambios en la rama principal

Cada cierto tiempo, los colaboradores crean un nuevo directorio llamado **PC_(N+1)/**  que corresponde con el nuevo challenge a realizar. 

Los participantes deben actualizar su fork a la ultima versión de la rama principal del proyecto. Para ello se realizan las siguientes acciones:

```bash
$ git fetch upstream
$ git merge upstream/main
```

Ejecutar los comandos anteriores sincronizará el fork del participante con los ultimos cambios presentes en la linea principal de desarrollo.  Una vez sincronizado, cada participante procederá a crear una carpeta siguiendo la estructura del proyecto. 

**Ejemplo**
		El colaborador A crea el challenge PC3/
		El participante 1 sincroniza su fork
		El participante 1 ingresa a la carpeta PC3/ y crea el directorio id_nombre_1/

## Estrategia para subir cambios

Cada participante tiene la capacidad de realizar cambios en su fork. Por limitaciones de accesos y permisos, se recomienda y solicita a cada participante hacer cambios **únicamente** en su propio directorio para evitar conflictos con el trabajo de otras personas.

Tomando en cuenta lo anterior, se presentan las siguientes acciones básicas que se deben tener en cuenta cuando se van a subir cambios al repositorio local, al fork, y posteriormente a la rama principal.

- #### Actualizar cambios:

**git add:** Permite agregar los cambios del usuario al estado de staged, lo cual significa que están listos para subirse al repositorio local. Ejemplos:

```bash
$ git add . (Agrega todos los cambios al stage)
$ git add archivo1 (Agrega el archivo seleccionado al stage)
$ git add archivo1 archivo2 archivoN (Agrega los archivos seleccionados al stage)
```

**git commit:** Guarda los cambios realizados en el repositorio local de cada participante. Ejemplo:

```bash
$ git commit -am "se agrega archivo" 
```

**git push:** Actualiza los cambios en el repositorio remoto (fork configurado):

```bash
$ git push 
```

- #### Subir cambios al proyecto principal.

Para evitar conflictos entre los participantes, cada cambio que se vaya a subir al repositorio central debe ser gestionado mediante un pull request que será evaluado por un colaborador para garantizar que no se hicieron cambios que puedan afectar a los demás.

Para realizar un pull request se deben realizar las siguientes acciones:

* Ir a la url del fork configurado
* Seleccionar la opción pull requests

![](/img/CREATE_PULL_REQUEST.png)

*  Seleccionar la opción **new pull request**

![](/img/PULL_REQUEST.png)

* Verificar que no existen conflictos con la rama principal
* Seleccionar la opción **create pull request**

Después de realizar esta acción, un colaborador revisará el pull request y realizará su aprobación o rechazo. En caso de aceptar el pull request, se hará merge con la rama principal, en caso contrario se debe revisar la causa del rechazo