# Python Challenges

Este repositorio contiene los proyectos realizados por los colaboradores autorizados que hacen parte de la iniciativa **Python Challenges**, que tiene por objetivo ofrecer un espacio en el cual estudiantes, profesionales e interesados en programación científica y ciencia de datos puedan aprender y recibir realimentación de manera colaborativa.

Se recomienda que cualquier persona interesada en colaborar tenga conocimientos básicos los siguientes aspectos. No obstante, esto se considera una limitante; adicionalmente, se adjunta documentación de interés para quien desee conocer aspectos generales de las herramientas y tecnologías mencionadas a continuación:

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

Git es una herramienta para facilitar el desarrollo de software a través de control de versiones, permitendo a grupos o células de trabajo trabajar de manera colaborativa.  No se debe confundir Git con GitHub, Github es una plataforma que permite mantener repositorios en la nube utilizando las características ofrecidas por git.

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

Una vez instalado git, ejecutar los siguientes comandos por terminal para activar características útiles. El primer comando evita errores presentes por formato que puede ocurrir en algunos editores; El segundo comando permite descargar cambios específicos de la rama **main**:

```bash
$ git config core.autocrlf true
$ git config core.sparseCheckout true
```

Si es la primera vez que se utiliza git, es necesario configurar el usuario para el acceso al repositorio. Para ello, se deben ejecutar los siguientes comandos:
```bash
$ git --global user.name = "mi_usuario"
$ git --global user.email = "mi_correo@host.xxx.xx"
```
La cuenta se puede verificar aplicando el siguiente comando:
```bash
$ git config --global -e
```
Adicionalmente, se recomienda agregar los siguientes alias para facilitar acciones que se realizan con frecuencia. Los alias descritos a continuación permiten resumir las acciones para consultar historico de commits y la revisión de status:

```bash
$ git config --global alias.lg "log --oneline --decorate --all --graph"
$ git config --global alias.s "status -sb"
```

# 2. Guía de instalación/Acciones básicas


A continuación se presentan los pasos para clonar el proyecto:

1. **Crear un fork del proyecto principal:**  Dar click en la opción fork como se muestra a continuación

![](/img/CREATE_FORK.png)


