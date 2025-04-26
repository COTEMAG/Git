# Guía Completa de Comandos Git
Esta guía servira de apoyo para aquellos que desean iniciar en el mundo de la programacion y en GIT, github, firebase studio, etc.

## Comandos mas importantes (Uso Diario)

### Iniciar y Configurar

git init - *Crea un nuevo repositorio Git en el directorio actual*

git clone url - *Descarga una copia completa de un repositorio remoto como lo puede ser github*

git status - *Muestra el estado actual: archivos modificados, preparados o sin seguimiento*

git config --global user.name "Tu Nombre" - *Establece tu nombre de usuario para todos los repositorios*

git config --global user.email "tucorreo@ejemplo.com" - *Configura tu correo electrónico para identificar tus commits*

### Gestionar Cambios

git add archivo - *Añade un archivo específico al área de preparación para el próximo commit*

git add . - *Añade todos los archivos nuevos y modificados al área de preparación*

git commit -m "Mensaje" - *Crea un nuevo commit con los cambios preparados y un mensaje descriptivo*

git commit -am "Mensaje" - *Hace el trabajo de "Git add" y "Git commit" a la vez*

### Ramas y Fusiones

git branch - *Lista todas las ramas de tu repositorio*

git switch nombredelarama - *Cambia a una rama existente*

git checkout nombredelarama - *Cambia a una rama existente (otra forma que usan los viejos)*

git checkout -b nombre - *Crea y cambia a una nueva rama*

git merge rama - *Incorpora los cambios de la rama especificada a la rama actual*

### Sincronización con Remotos

git pull remoto rama - *Descarga y fusiona cambios remotos en la rama actual*

git push remoto rama - *Sube los commits locales al repositorio remoto*

git fetch remoto - *Descarga cambios del remoto sin fusionarlos, viendo que cambios hay en el repositorio remoto antes de hacer un pull directo*

## Historial y Diferencias

git log - *Muestra el historial completo de commits con detalles*

git log --oneline - *Muestra el historial resumido, un commit por línea*

git diff - *Muestra diferencias entre directorio de trabajo y área de preparación*

git diff --staged - *Muestra diferencias entre área de preparación y último commit*

git show commit - *Muestra detalles de un commit específico*

## Deshacer Cambios

### Restaurar Archivos

git restore archivo - *Descarta cambios en un archivo antes de prepararlo*

git checkout -- archivo - *Descarta cambios en un archivo*

git restore --staged archivo - *Quita un archivo del área de preparación manteniendo los cambios*


### Modificar Commits

git commit --amend - *Modifica el último commit (mensaje o contenido)*

### Reset (Deshacer Commits)

git reset --soft HEAD~1 - *Deshace el último commit pero mantiene cambios en staging*

git reset HEAD~1 - *Deshace el último commit y desagrega cambios, manteniéndolos en el directorio*

git reset --hard HEAD~1 - *Elimina completamente el último commit y todos sus cambios (no recomendado)*

### Revert (Deshacer de Forma Segura)

git revert commit - *Crea un nuevo commit que deshace los cambios de otro sin modificar el historial*

## Gestión de Ramas Avanzada

git branch -a - *Lista todas las ramas (locales y remotas)*

git branch nombre - *Crea una nueva rama*

git branch -d rama - *Elimina una rama (después de fusionar)*

git rebase rama - *Reaplica los cambios de la rama actual sobre otra (historial más limpio)*

git rebase -i HEAD~n - *Rebase interactivo para reorganizar, editar o combinar los últimos n commits*

## Etiquetas (Tags)

git tag - *Lista todas las etiquetas existentes*

git tag nombre - *Crea una etiqueta ligera en el commit actual*

git tag -a nombre -m "mensaje" - *Crea una etiqueta anotada con mensaje y metadatos adicionales*

git tag -a nombre commit -m "mensaje" - *Etiqueta un commit específico (útil para marcar versiones)*

git push origin tag - *Publica una etiqueta específica en el repositorio remoto*

git push origin --tags - *Publica todas las etiquetas en el repositorio remoto*

## Gestión de Remotos

git remote -v - *Muestra los repositorios remotos configurados con sus URLs*

git remote add nombre url - *Añade un nuevo repositorio remoto*

git remote remove nombre - *Elimina un repositorio remoto*

git pull remoto rama - *Descarga cambios y aplica commits locales encima (evita commits de merge)*

git push remoto rama - *Envía y establece la rama para seguimiento (futuro git pull sin argumentos)*

## Configuración Avanzada

git config --global core.editor "code --wait" - *Define el editor de texto para mensajes de commit y otras operaciones*

git config --global core.autocrlf true - *Gestiona la conversión de saltos de línea en Windows*

git config --global core.autocrlf input - *Gestiona la conversión de saltos de línea en Linux/Mac*

git config --global init.defaultBranch main - *Cambia el nombre de la rama principal por defecto a "main"*

git config --global -e - *Abre el archivo de configuración global para edición manual*

## Comandos del Sistema Útiles

mkdir carpeta - *Crea una nueva carpeta o directorio*

cd ruta - *Cambia al directorio especificado*

pwd - *Muestra la ruta completa del directorio actual*

touch archivo - *Crea un archivo vacío*

cat archivo - *Muestra el contenido de un archivo*

ls -la - *Lista todos los archivos (incluyendo ocultos) con detalles*

rm archivo - *Elimina un archivo*

code . - *Abre la carpeta actual en Visual Studio Code*