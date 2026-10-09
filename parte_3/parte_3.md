# Parte 3. Interpretación de comandos

## 1. Análisis de `git status`, `git add`, `git commit` y `git push`

### Planteamiento
Analiza este conjunto de instrucciones:

```bash
git status
git add README.md
git commit -m "Actualiza documentación"
git push
```

### Respuesta
`git status` muestra el estado del repositorio: qué archivos están modificados, sin seguimiento o ya preparados para el commit.

`git add README.md` agrega el archivo README al área de preparación (`staging area`). Esto significa que los cambios del archivo están listos para ser guardados en el siguiente commit.

`git commit -m "Actualiza documentación"` crea un nuevo commit con los cambios preparados, acompañado de un mensaje descriptivo. En este punto se guarda una instantánea del proyecto.

`git push` envía los commits locales al repositorio remoto configurado, por ejemplo GitHub.

### Explicación
Estos comandos forman el flujo básico de trabajo en Git: revisar cambios, prepararlos, guardar una versión y publicar la actualización. Es la base para colaborar con otros desarrolladores.

## 2. Caso A: falta una operación

### Planteamiento
```bash
Modificar archivo
git add .
¿?
git push
```

### Respuesta
Falta realizar un `git commit`.

### Explicación
Después de ejecutar `git add .`, los cambios quedan preparados en el área de staging. Sin embargo, aún no forman parte del historial de Git. `git commit` crea el punto de guardado y es necesario para poder enviar el trabajo con `git push`.

## 3. Caso B: repositorio GitHub y repositorio local

### Planteamiento
```text
Repositorio GitHub
    ↓
    ?
    ↓
Repositorio local
```

### Respuesta
La operación que se utiliza es `git clone`.

### Explicación
`git clone` copia un repositorio remoto a la máquina local para comenzar a trabajar en él. Es la operación conveniente cuando quieres obtener una copia del proyecto que ya existe en GitHub.

## 4. Caso C: repositorio remoto actualizado y repositorio local actualizado

### Planteamiento
```text
Repositorio remoto actualizado
    ↓
    ?
    ↓
Repositorio local actualizado
```

### Respuesta
La operación adecuada es `git pull`.

### Explicación
`git pull` trae los cambios del repositorio remoto al repositorio local y los integra con la rama actual. Se usa cuando el equipo ya publicó cambios en GitHub y tú quieres mantener tu copia local sincronizada.
