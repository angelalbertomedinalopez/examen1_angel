# Parte 2. Comprensión del flujo colaborativo

## 1. Flujo colaborativo

### Planteamiento
Supón que quieres colaborar con el repositorio de otro desarrollador. Ordena y explica los siguientes elementos: Push, Fork, Pull Request, Clone, Merge, Commit, Review, Branch y Modificar archivos. Agrega cualquier operación que consideres necesaria.

### Respuesta
El flujo típico es el siguiente:

1. Crear un Fork del repositorio original para obtener tu propia copia en GitHub.
2. Clonar ese Fork en tu máquina local con `git clone`.
3. Crear una rama con `git checkout -b <nombre-rama>` o `git switch -c <nombre-rama>`.
4. Modificar archivos en la rama de trabajo.
5. Guardar los cambios con `git add` y `git commit`.
6. Publicar la rama con `git push`.
7. Abrir un Pull Request desde tu rama hacia la rama principal del repositorio original.
8. El propietario del repositorio revisa el Pull Request (`Review`).
9. Si acepta los cambios, se realiza el `Merge` en el repositorio original.
10. Si el repositorio original tiene cambios nuevos, puedes sincronizar tu Fork con `Sync Fork` o `git fetch`/`git pull`.

### Explicación
Este procedimiento permite colaborar sin modificar directamente el proyecto original. Las ramas ayudan a separar las modificaciones del trabajo principal, mientras que los commits registran los avances. Finalmente, el Pull Request permite evaluar las contribuciones antes de incorporarlas al repositorio original.

## 2. Fork y Clone

### Planteamiento
Analiza la afirmación: “Clone crea una copia del proyecto dentro de mi cuenta de GitHub”. Indica si es correcta y explica la diferencia entre Fork y Clone.

### Respuesta
La afirmación no es correcta. `git clone` no crea una copia dentro de GitHub; en realidad descarga una copia del repositorio a tu equipo local.

La diferencia es:

- `Fork`: crea una copia del repositorio en tu cuenta de GitHub.
- `Clone`: descarga esa copia (o un repositorio ajeno) a tu computadora para trabajar localmente.

### Explicación
Un `Fork` se hace en GitHub y te da un repositorio independiente asociado a tu cuenta. Un `Clone` es la acción local que copia ese repositorio a tu máquina para editarlo. Ambos conceptos son complementarios, pero no equivalentes.

## 3. Pull Request

### Planteamiento
Supón que realizaste Fork, Clone, Branch, Modificar, Commit y Push. Responde: ¿los cambios ya forman parte del repositorio original? ¿Qué debe ocurrir para incorporarlos?

### Respuesta
No, los cambios todavía no están incorporados al repositorio original. Es necesario enviar un Pull Request y esperar a que los cambios sean aceptados e integrados.

Para incorporarlos, el propietario del repositorio original debe revisar el Pull Request y luego aceptar el `Merge`.

### Explicación
El `Push` publica tus commits en tu propio Fork, no en el repositorio del otro desarrollador. El Pull Request propone esos cambios al repositorio original y el `Merge` los incorpora si el propietario los aprueba.

## 4. Request Changes

### Planteamiento
El propietario revisa tu Pull Request y selecciona Request Changes. Explica qué debes hacer, si necesitas crear otro Pull Request y qué ocurre cuando realizas nuevamente push.

### Respuesta
Debo atender las observaciones del propietario, corregir los archivos y subir las modificaciones a la misma rama. No es necesario abrir otro Pull Request.

### Explicación
Cuando el propietario selecciona Request Changes, significa que necesita que realice ajustes antes de aceptar la propuesta. Después de corregir los archivos, debo crear otro commit y ejecutar git push. Como los cambios se envían a la misma rama vinculada al Pull Request, este se actualiza automáticamente y puede revisarse de nuevo.

## 5. Merge y repositorio local

### Planteamiento
Un Pull Request fue aceptado y se realizó Merge en GitHub. Sin embargo, el repositorio local del propietario no contiene los cambios. Explica por qué sucede y qué operación debe realizarse.

### Respuesta
Esto ocurre porque el `Merge` se hizo en GitHub, no en la máquina local del propietario. El repositorio local sigue apuntando a una versión anterior del historial.

Para actualizarlo, se debe hacer `git pull` o `git fetch` seguido de `git merge` (o simplemente `git pull` si el repositorio está configurado correctamente).

### Explicación
El Merge modifica el repositorio remoto, pero no actualiza automáticamente los archivos que están guardados en la computadora del propietario. Por eso, debe descargar las actualizaciones del remoto mediante git pull, estando en la rama correspondiente, para incorporar esos cambios a su copia local.

## 6. Sync Fork

### Planteamiento
Tu Fork fue creado varios días atrás y el repositorio original recibió nuevos commits. Explica qué herramienta utilizarías, qué repositorio se actualiza y qué diferencia existe entre Sync Fork y git pull.

### Respuesta
Para actualizar tu fork usaría `Sync Fork` desde GitHub, que compara tu bifurcación con el repositorio original y aplica los cambios relevantes. En este caso, se actualiza tu Fork, no el repositorio original.

La diferencia con `git pull` es que:

- `git pull` sincroniza la rama local con un remoto configurado.
- `Sync Fork` es una acción de GitHub para actualizar una bifurcación con los cambios del proyecto original.

### Explicación
`Sync Fork` actualiza tu copia del repositorio en GitHub con los cambios del repositorio original. `git pull`, en cambio, descarga e integra en tu copia local los cambios del remoto configurado. Si ya sincronizaste el Fork, puedes después usar `git pull` para actualizar también tu repositorio local.