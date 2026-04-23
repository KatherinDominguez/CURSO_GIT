# CURSO DE GIT 
## CLASE - 01 
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

## CLASE - 02
### Los estados de Git
En Git, los archivos pueden estar en diferentes estados que reflejan su situación en el proceso de desarrollo. Estos estados son fundamentales para entender cómo Git maneja los cambios y cómo se preparan los archivos para ser incluidos en los commits.
#### Directorio de trabajo (Working Directory)
Es el lugar donde se encuentran los archivos del proyecto en tu sistema de archivos. Aquí es donde realizas cambios en los archivos, como editarlos, agregar nuevos archivos o eliminar archivos existentes. El directorio de trabajo refleja el estado actual de tu proyecto.
* Untracked: El archivo no está siendo rastreado por Git. No forma parte del historial de versiones y no se incluirá en los commits a menos que se agregue explícitamente.
* Unmodified: El archivo está siendo rastreado por Git y no ha sufrido cambios desde el último commit. No se necesita hacer nada con este archivo, ya que no hay cambios que registrar.
* Modified: El archivo ha sido modificado desde el último commit, pero aún no se ha agregado al área de preparación (staging area). Para incluir estos cambios en el próximo commit, es necesario agregar el archivo al área de preparación.
Si necesitas que un archivo vuelva a su estado original, puedes usar el comando `git restore -- <archivo>`, lo que descartará los cambios realizados en ese archivo y lo devolverá a la última versión confirmada en el repositorio local.
##### ¿Qué pasa si quiero que el archivo que creé no quiero que lo vea Git?
En ese caso, puedes agregar el nombre del archivo o el patrón de archivos al archivo `.gitignore`. Esto le indicará a Git que ignore esos archivos y no los rastree ni los incluya en los commits.

#### Área de preparación (Staging Area)
Es un espacio intermedio donde puedes preparar los cambios que deseas incluir en el próximo commit. Cuando agregas un archivo al área de preparación, estás indicando que quieres que esos cambios se registren en el historial de versiones. Puedes agregar archivos al área de preparación utilizando el comando `git add <archivo>`. Y con el comando `git reset <archivo>` puedes eliminar un archivo del área de preparación, lo que significa que esos cambios no se incluirán en el próximo commit.
Al aplicar el comando `git add .`, todos los archivos modificados en el directorio de trabajo se agregarán al área de preparación, lo que significa que estarán listos para ser incluidos en el próximo commit.
#### Repositorio local (Local Repository)
Es donde Git almacena el historial de versiones de tu proyecto. Cuando realizas un commit, los cambios que has preparado en el área de preparación se registran en el repositorio local. El repositorio local es una copia completa del historial de versiones, lo que permite trabajar de manera independiente sin necesidad de una conexión a internet.
Los comandos básicos para manejar estos estados son:
- `git commit -m "Mensaje del commit"`: Crea un nuevo commit con los cambios que has preparado en el área de preparación.
- `git status`: Muestra el estado actual de los archivos en el directorio de trabajo, el área de preparación y el repositorio local, indicando qué archivos están modificados, cuáles están preparados para el commit y cuáles no están siendo rastreados por Git.
- `git log`: Muestra el historial de commits en el repositorio local, permitiéndote ver los cambios realizados a lo largo del tiempo y quién los realizó.
- `git reset --hard HEAD`: Restaura el estado del repositorio local al último commit, descartando cualquier cambio no confirmado en el directorio de trabajo y el área de preparación. Ten cuidado al usar este comando, ya que perderás cualquier cambio no confirmado.
- `git reset --soft HEAD~1`: Deshace el último commit, pero mantiene los cambios en el área de preparación. Esto te permite modificar el mensaje del commit o agregar más cambios antes de volver a confirmar.

### Buenas prácticas para el uso de Git
1. Usa verbos imperativos en los mensajes de commit: Los mensajes de commit deben ser claros y concisos, describiendo la acción realizada. Por ejemplo, "Agrega función de autenticación" en lugar de "Función de autenticación agregada".
* Add: Indica que se ha agregado una nueva función o característica al proyecto.
* Fix: Indica que se ha corregido un error o bug en el código.
* Update: Indica que se ha actualizado o mejorado una función existente.
* Remove: Indica que se ha eliminado una función o código innecesario del proyecto.

2. No uses punto final en los mensajes de commit: Los mensajes de commit no deben terminar con un punto, ya que esto puede dificultar la lectura y el seguimiento del historial de versiones. 

3. Usar como maximo 50 caracteres para el mensaje de commit: Los mensajes de commit deben ser breves y al punto, idealmente no más de 50 caracteres. Esto facilita la lectura y comprensión del historial de versiones, especialmente cuando se visualiza en herramientas como `git log` o plataformas de alojamiento de código como GitHub.

4. Usar un prefixo para el mensaje de commit: Es recomendable usar un prefijo en el mensaje de commit para indicar el tipo de cambio realizado. Esto ayuda a categorizar los commits y facilita la comprensión del historial de versiones. Algunos prefijos comunes incluyen:
* feat: Indica que se ha agregado una nueva función o característica al proyecto.
* fix: Indica que se ha corregido un error o bug en el código.
* docs: Indica que se han realizado cambios en la documentación del proyecto.
* style: Indica que se han realizado cambios en el formato o estilo del código, sin afectar la funcionalidad.
* refactor: Indica que se ha refactorizado el código, mejorando su estructura sin cambiar su comportamiento.
* test: Indica que se han agregado o modificado pruebas para el proyecto.
* chore: Indica que se han realizado tareas de mantenimiento o cambios menores que no afectan la funcionalidad del proyecto.
* perf: Indica que se han realizado cambios para mejorar el rendimiento del proyecto.
* ci: Indica que se han realizado cambios relacionados con la integración continua o el proceso de construcción del proyecto.
* build: Indica que se han realizado cambios relacionados con el proceso de construcción o compilación del proyecto.
5. Añade todo el contexto necesario en el mensaje de commit: Además de ser breve, el mensaje de commit debe proporcionar suficiente contexto para que otros desarrolladores (o tú mismo en el futuro) puedan entender claramente qué cambios se realizaron y por qué. Esto puede incluir detalles sobre la razón detrás del cambio, cómo se implementó o cualquier información relevante que ayude a comprender el propósito del commit.

> Razón por la cual no asistí a la clase 21/03/2026
> - ![Hora de inicio de Parcial 18:45 pero nos dió tiempo a resolver hasta las 20:30 y de ahí a casa me demoro aproximadamente una hora y media. Por lo cual no pude asistir.](images/Foto_de_WhatsApp.png )
> - Estaba en el parcial de la materia de Taller de Sistemas Operativos, que se llevó a cabo el mismo día y hora que la clase de Git. Lamentablemente, no pude asistir a la clase debido a este compromiso académico.