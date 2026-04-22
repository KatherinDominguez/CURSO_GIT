# CURSO DE GIT - 001
## ¿Qué es Git?
Es un Sistema de Control de Versiones, que nos permite llevar un control de los cambios realizados en nuestros proyectos, facilitando la colaboración entre varios desarrolladores.
Permitiendo a los desarrolladores trabajar de manera conjunta en un proyecto, sin preocuparse por los conflictos de código o la pérdida de información. Git registra cada cambio realizado en el proyecto, lo que permite revertir a versiones anteriores si es necesario y facilita la colaboración entre equipos de desarrollo.
## ¿Cómo nació Git?
Git nació en abril de 2005, creado por Linus Torvalds (creador de Linux), tras la necesidad de un sistema de control de versiones rápido y distribuido para el kernel de Linux.
Surgió tras la polémica cancelación de la licencia gratuita de BitKeeper, el sistema que usaban anteriormente, lo que obligó a Torvalds a diseñar uno nuevo en poco más de una semana.
## Cómo instalar Git?
### En Windows:
1. Descarga el instalador desde la página oficial: https://git-scm.com/downloads
2. Ejecuta el instalador y sigue las instrucciones. Puedes dejar las opciones por defecto, pero asegúrate de seleccionar "Git from the command line and also from 3rd-party software" para usar Git desde la terminal.
3. Una vez instalado, abre la terminal (Git Bash) y verifica la instalación con el comando:
   ```
   git --version
   ```      
### En macOS:
1. Abre la terminal y ejecuta el siguiente comando para instalar Git usando Homebrew:
   ```
   brew install git
   ```      
2. Verifica la instalación con el comando:
   ```
    git --version
    ```
### En Linux:
1. Abre la terminal y ejecuta el siguiente comando para instalar Git:   
    - En Debian/Ubuntu:
      ```
      sudo apt-get update
      sudo apt-get install git
      ```
    - En Fedora:
      ```
      sudo dnf install git
      ```
    - En Arch Linux:
      ```
      sudo pacman -S git
      ```
2. Verifica la instalación con el comando:
    ```
    git --version
    ```
## Configuración inicial de Git
Después de instalar Git, es importante configurar tu nombre de usuario y correo electrónico, ya que esta información se asociará con tus commits. Para configurar Git, abre la terminal y ejecuta los siguientes comandos:
```
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"
```
        
### Archivos en todo repositorio deberia tener
- README.md: Un archivo que proporciona información sobre el proyecto, cómo usarlo, cómo contribuir, etc.
- .gitignore: Un archivo que especifica qué archivos o directorios deben ser ignorados  por Git, como archivos temporales, dependencias, etc.
- LICENSE: Un archivo que especifica la licencia bajo la cual se distribuye el proyecto, indicando los términos de uso y distribución.
