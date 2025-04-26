# Guía de Flujo de Trabajo con Git: Ejemplo Práctico

En este archivo habran ejemplos que puedes usar y poner en practica para mejorar tu habilidad en el mundo de GIT

## Iniciar y Configurar un Repositorio

### Configuración inicial

git config --global user.name "Chef Programador" - *Establecemos nuestro nombre de usuario*

git config --global user.email "chef@programador.com" - *Configuramos nuestro email*

mkdir recetas-cocina - *Creamos una carpeta para nuestro proyecto*

cd recetas-cocina - *Nos movemos a la carpeta creada*

git init - *Inicializamos un repositorio Git vacío en la carpeta actual*

### Creación de archivos iniciales

touch archivo1.txt - *Creamos nuestro primer archivo*

cat > archivo1.txt - *Añadimos contenido al archivo*
Receta: Tortilla Española
Ingredientes:
- 4 patatas medianas
- 6 huevos
- 1 cebolla (opcional)
- Aceite de oliva
- Sal al gusto

Preparación:
1. Pelar y cortar las patatas en rodajas finas
2. Freír a fuego lento hasta que estén tiernas
3. Batir los huevos y mezclar con las patatas
4. Cuajar la tortilla por ambos lados

git status - *Verificamos el estado del repositorio: nos muestra archivo1.txt como sin seguimiento*

git add archivo1.txt - *Añadimos el archivo al área de preparación*

git commit -m "Añadida receta de tortilla española" - *Creamos nuestro primer commit*

## Gestión de Ramas y Cambios

git checkout -b "postres" - *Creamos y cambiamos a una nueva rama para postres*

touch archivo2.txt - *Creamos un archivo para una receta de postre*

cat > archivo2.txt - *Añadimos contenido al archivo*
Receta: Flan de Huevo
Ingredientes:
- 5 huevos
- 500ml de leche
- 150g de azúcar
- Esencia de vainilla

Preparación:
1. Caramelizar 100g de azúcar en un molde
2. Batir los huevos con la leche y el resto de azúcar
3. Verter en el molde y hornear al baño maría
4. Refrigerar antes de servir

git add archivo2.txt - *Añadimos el archivo al área de preparación*

git commit -m "Añadida receta de flan de huevo" - *Creamos un commit en la rama postres*

git switch main - *Volvemos a la rama principal*

touch archivo3.txt - *Creamos un nuevo archivo en la rama main*

cat > archivo3.txt - *Añadimos contenido al archivo*
Receta: Paella Valenciana
Ingredientes:
- 400g de arroz bomba
- 1 conejo troceado
- 200g de judías verdes
- 200g de garrofón
- Azafrán y pimentón
- Caldo de pollo
- Aceite de oliva y sal

Preparación:
1. Sofreír la carne en la paellera
2. Añadir las verduras y rehogar
3. Incorporar el arroz y el caldo caliente
4. Cocinar a fuego medio-alto 10 minutos
5. Bajar el fuego y cocinar 8 minutos más
6. Dejar reposar tapada con un paño

git add archivo3.txt - *Añadimos el archivo al área de preparación*

git commit -m "Añadida receta de paella valenciana" - *Creamos otro commit en main*

## Fusión de Ramas

git merge postres - *Fusionamos la rama postres a la rama main*

## Modificar Archivos y Gestionar Cambios

cat > archivo1.txt - *Modificamos el contenido del archivo*
Receta: Tortilla Española
Ingredientes:
- 4 patatas medianas
- 6 huevos
- 1 cebolla grande
- Aceite de oliva
- Sal al gusto
- Pimienta negra

Preparación:
1. Pelar y cortar las patatas en rodajas finas
2. Picar la cebolla en juliana
3. Freír todo a fuego lento hasta que estén tiernas
4. Batir los huevos y mezclar con las patatas y cebolla
5. Cuajar la tortilla por ambos lados
6. Servir caliente o a temperatura ambiente

git status - *Verificamos que el archivo está modificado*

git diff archivo1.txt - *Vemos las diferencias entre la versión actual y la última confirmada*

git add archivo1.txt - *Añadimos los cambios al área de preparación*

git commit -m "Actualizada receta de tortilla con más detalles" - *Confirmamos los cambios*

## Deshacer Cambios

cat > archivo2.txt - *Modificamos incorrectamente el archivo*
Receta: Flan de Chocolate (ERROR)

git status - *Verificamos que el archivo está modificado*

git restore archivo2.txt - *Descartamos los cambios volviendo a la versión del último commit*

## Repositorios Remotos

git remote add origin https://github.com/usuario/recetas-cocina.git - *Añadimos un repositorio remoto*

git push -u origin main - *Subimos nuestros cambios al remoto y establecemos seguimiento*

## Trabajo Colaborativo

git checkout -b "bebidas" - *Creamos una nueva rama para bebidas*

touch archivo4.txt - *Creamos un archivo para una receta de bebida*

cat > archivo4.txt - *Añadimos contenido al archivo*
Receta: Sangría Española
Ingredientes:
- 1 botella de vino tinto
- 2 naranjas
- 1 limón
- 1 manzana
- 50g de azúcar
- 1 ramita de canela
- Hielo al gusto

Preparación:
1. Cortar la fruta en trozos pequeños
2. Mezclar con el vino y el azúcar
3. Añadir la canela y refrigerar por 2 horas
4. Servir con hielo

git add archivo4.txt - *Añadimos el archivo al área de preparación*

git commit -m "Añadida receta de sangría española" - *Creamos un commit en la rama bebidas*

git push origin bebidas - *Subimos la rama bebidas al repositorio remoto*

## Etiquetas (Versiones)

git tag -a v1.0 -m "Primera versión del recetario" - *Creamos una etiqueta anotada*

git push origin v1.0 - *Subimos la etiqueta al repositorio remoto*

## Simulación de Trabajo en Equipo

git pull origin main - *Descargamos cambios que podrían haber hecho otros colaboradores*

## Conflictos y Resolución

git checkout main - *Volvemos a la rama principal*

cat > archivo1.txt - *Modificamos el archivo1.txt en main*
Receta: Tortilla Española Tradicional
Ingredientes:
- 4 patatas medianas
- 6 huevos
- Aceite de oliva
- Sal al gusto

Preparación:
1. Pelar y cortar las patatas en rodajas finas
2. Freír a fuego lento hasta que estén tiernas
3. Batir los huevos y mezclar con las patatas
4. Cuajar la tortilla por ambos lados
5. La tortilla auténtica no lleva cebolla

git add archivo1.txt - *Añadimos los cambios*

git commit -m "Actualizada receta de tortilla a versión tradicional" - *Confirmamos*

git checkout -b "variantes" - *Creamos otra rama*

cat > archivo1.txt - *Modificamos el mismo archivo en esta rama*
Receta: Tortilla Española con Variantes
Ingredientes:
- 4 patatas medianas
- 6 huevos
- 1 cebolla grande (opcional)
- 100g de pimientos (opcional)
- Aceite de oliva
- Sal al gusto

Preparación:
1. Pelar y cortar las patatas en rodajas finas
2. Añadir verduras si se desea
3. Freír todo a fuego lento hasta que esté tierno
4. Batir los huevos y mezclar
5. Cuajar la tortilla por ambos lados
git add archivo1.txt - *Añadimos los cambios*

git commit -m "Añadidas variantes a la receta de tortilla" - *Confirmamos*

git checkout main - *Volvemos a la rama principal*

git merge variantes - *Intentamos fusionar, lo que causará un conflicto*

// Resolvemos el conflicto manualmente editando archivo1.txt

cat > archivo1.txt - *Resolución del conflicto*
Receta: Tortilla Española (Con opciones)
Ingredientes:
- 4 patatas medianas
- 6 huevos
- 1 cebolla grande (opcional para versión con cebolla)
- 100g de pimientos (opcional para versión con verduras)
- Aceite de oliva
- Sal al gusto

Preparación:
1. Pelar y cortar las patatas en rodajas finas
2. Añadir verduras si se prefiere la versión con cebolla
3. Freír todo a fuego lento hasta que esté tierno
4. Batir los huevos y mezclar
5. Cuajar la tortilla por ambos lados
6. La versión tradicional no lleva cebolla, pero ambas son deliciosas

git add archivo1.txt - *Marcamos el conflicto como resuelto*

git commit -m "Fusionadas versiones de tortilla con y sin cebolla" - *Confirmamos la resolución*

## Historial y Seguimiento

git log --oneline - *Vemos el historial resumido de commits*

git blame archivo1.txt - *Vemos quién modificó cada línea del archivo*

git show HEAD~1 - *Vemos los detalles del penúltimo commit*

## Limpieza y Gestión Final

git branch -d variantes - *Eliminamos la rama una vez fusionada*

git branch -d postres - *Eliminamos otra rama ya fusionada*

git push origin --delete bebidas - *Eliminamos una rama remota que ya no necesitamos*

git tag -a v1.1 -m "Versión con todas las recetas básicas" - *Creamos una nueva etiqueta*

git push origin v1.1 - *Subimos la nueva etiqueta al repositorio remoto*
