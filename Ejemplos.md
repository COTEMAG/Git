# Ejemplo Práctico de Flujo de Trabajo con Git

A continuación te presento un ejemplo paso a paso que muestra el uso de los comandos Git más importantes en un flujo de trabajo típico.

## 1. Configuración Inicial

```
mkdir proyecto-recetas
cd proyecto-recetas
```
*Creamos un directorio para nuestro proyecto y nos movemos a él*

```
git init
```
*Inicializa un repositorio Git vacío en el directorio actual. Crea una carpeta oculta .git que contendrá toda la información del repositorio*

```
git config --global user.name "Tu Nombre"
```
*Establece tu nombre de usuario para todos los repositorios de Git en tu máquina*

```
git config --global user.email "tucorreo@ejemplo.com"
```
*Configura tu correo electrónico para identificar tus commits*

## 2. Creación y Seguimiento de Archivos

```
touch archivo1.txt
"Receta de Gazpacho:
- 1kg de tomates maduros
- 1 pimiento verde
- 1 pepino
- 1 diente de ajo
- Aceite de oliva, vinagre y sal"
```
*Creamos un archivo de texto y añadimos contenido*

```
git status
```
*Muestra el estado actual del repositorio. Veremos que archivo1.txt aparece como "Untracked file" (archivo sin seguimiento)*

```
git add archivo1.txt
```
*Añade el archivo al área de preparación (staging area). El archivo ahora está listo para ser incluido en el próximo commit*

```
git status
```
*Ahora muestra archivo1.txt como "Changes to be committed" (cambios por confirmar)*

```
git commit -m "Añadida receta de gazpacho"
```
*Crea un nuevo commit con los cambios preparados y un mensaje descriptivo. Este commit contiene una instantánea del archivo en este momento*

## 3. Modificación de Archivos y Visualización de Cambios

```
"- 1 cebolla pequeña" >> archivo1.txt
```
*Modificamos el archivo añadiendo un ingrediente más*

```
git status
```
*Muestra que archivo1.txt ha sido modificado pero los cambios no están preparados*

```
git diff archivo1.txt
```
*Muestra las diferencias entre el archivo en el directorio de trabajo y la versión en el último commit. Veremos la línea añadida destacada*

```
git add archivo1.txt
```
*Añade los cambios al área de preparación*

```
git commit -m "Añadido ingrediente a la receta de gazpacho"
```
*Crea un nuevo commit con los cambios*

## 4. Creación y Gestión de Ramas

```
git branch
```
*Lista todas las ramas del repositorio. Veremos solo "main" o "master" con un asterisco indicando que es la rama actual*

```
git branch postres
```
*Crea una nueva rama llamada "postres" pero no cambia a ella*

```
git switch postres
```
*Cambia a la rama "postres". En versiones antiguas de Git, usaríamos "git checkout postres"*

```
touch archivo2.txt
"Receta de Flan:
- 4 huevos
- 500ml de leche
- 150g de azúcar
- Esencia de vainilla"
```
*Creamos un nuevo archivo en la rama postres*

```
git add archivo2.txt
```
*Añade el archivo al área de preparación*

```
git commit -m "Añadida receta de flan"
```
*Crea un commit en la rama postres*

## 5. Fusión de Ramas

```
git switch main
```
*Volvemos a la rama principal*

```
ls
```
*Lista los archivos en el directorio. Notaremos que archivo2.txt no aparece porque existe solo en la rama postres*

```
git merge postres
```
*Incorpora los cambios de la rama "postres" a la rama actual (main). Después de esto, archivo2.txt aparecerá en la rama main*

## 6. Visualización del Historial

```
git log
```
*Muestra el historial completo de commits con detalles como autor, fecha y mensaje*

```
git log --oneline
```
*Muestra el historial resumido, un commit por línea, identificando cada commit con un hash abreviado*

```
git show HEAD
```
*Muestra detalles del último commit (HEAD)*

## 7. Deshacer Cambios

```
"Este es un cambio que no quiero mantener" 
```
*Hacemos un cambio en archivo1.txt que luego queremos descartar*

```
git status
```
*Veremos que archivo1.txt ha sido modificado*

```
git restore archivo1.txt
```
*Descarta los cambios en archivo1.txt, volviendo a la versión del último commit*

```
touch archivo3.txt
"Archivo temporal que no quiero" > archivo3.txt
git add archivo3.txt
```
*Creamos un archivo y lo añadimos al área de preparación*

```
git status
```
*Muestra archivo3.txt como preparado para commit*

```
git restore --staged archivo3.txt
```
*Quita archivo3.txt del área de preparación pero mantiene el archivo y sus cambios*

```
git status
```
*Ahora archivo3.txt aparece como sin seguimiento*

## 8. Modificación de Commits

```
touch archivo4.txt
"Receta de Paella"
git add archivo4.txt
git commit -m "Receta incompleta"
```
*Creamos un archivo, lo añadimos y hacemos un commit*

```
"- 400g de arroz
- Azafrán
- Caldo de pescado
- Mariscos variados" >> archivo4.txt
```
*Completamos la receta*

```
git add archivo4.txt
git commit --amend -m "Añadida receta completa de paella"
```
*Modifica el último commit añadiendo los nuevos cambios y actualizando el mensaje*

## 9. Trabajo con Repositorios Remotos

```
git remote add origin https://github.com/usuario/proyecto-recetas.git
```
*Añade un repositorio remoto llamado "origin" con la URL especificada*

```
git remote -v
```
*Muestra los repositorios remotos configurados con sus URLs*

```
git push -u origin main
```
*Sube los commits locales de la rama main al repositorio remoto y establece la rama para seguimiento*

```
git fetch origin
```
*Descarga cambios del remoto sin fusionarlos, permitiendo ver qué ha cambiado antes de integrar los cambios*

```
git pull origin main
```
*Descarga y fusiona los cambios remotos en la rama actual*

## 10. Etiquetas (Tags)

```
git tag v1.0
```
*Crea una etiqueta ligera en el commit actual, útil para marcar versiones*

```
git tag -a v1.1 -m "Primera versión estable con múltiples recetas"
```
*Crea una etiqueta anotada con mensaje y metadatos adicionales*

```
git push origin v1.1
```
*Publica la etiqueta v1.1 en el repositorio remoto*

## 11. Deshacer Commits

```
touch archivo5.txt
"Este es un archivo que añadí por error"
git add archivo5.txt
git commit -m "Archivo añadido por error"
```
*Creamos un archivo y lo confirmamos por error*

```
git log --oneline
```
*Vemos el historial y copiamos el hash del commit anterior al erróneo*

```
git reset --soft HEAD~1
```
*Deshace el último commit pero mantiene los cambios en el área de preparación*

```
git status
```
*Veremos que archivo5.txt sigue en el área de preparación*

```
git reset HEAD archivo5.txt
```
*Quita el archivo del área de preparación*

```
rm archivo5.txt
```
*Eliminamos el archivo no deseado*

## 12. Revertir Cambios de Forma Segura

```
touch archivo6.txt
"Contenido inicial"
git add archivo6.txt
git commit -m "Añadido archivo6.txt"
```
*Creamos un archivo y lo confirmamos*

```
echo "Cambio que luego querré revertir" > archivo6.txt
git add archivo6.txt
git commit -m "Cambio problemático en archivo6.txt"
```
*Hacemos un cambio que luego queremos revertir*

```
git log --oneline
```
*Vemos el historial y copiamos el hash del commit problemático*

```
git revert [hash-del-commit]
```
*Crea un nuevo commit que deshace los cambios del commit especificado sin modificar el historial*

## 13. Limpieza y Gestión de Ramas

```
git branch -d postres
```
*Elimina la rama "postres" después de haberla fusionado con main*

```
git checkout -b nueva-funcionalidad
```
*Crea y cambia a una nueva rama en un solo paso*

```
git branch -a
```
*Lista todas las ramas (locales y remotas)*

## 14. Trabajo Colaborativo

```
git pull
```
*Actualiza tu repositorio local con los cambios del remoto (equivalente a git fetch seguido de git merge)*

```
git push
```
*Envía tus commits locales al repositorio remoto*

```
git fetch --prune
```
*Actualiza referencias remotas y elimina referencias a ramas que ya no existen en el remoto*
