# Parte 4. Conceptos

## 1. Diferencia entre Git y GitHub

### Respuesta
Git es un sistema de control de versiones distribuido que permite registrar cambios en un proyecto de forma local. GitHub es una plataforma en línea que aloja repositorios Git y facilita la colaboración, revisión y publicación de proyectos.

### Explicación
Git se usa principalmente en la máquina del desarrollador para gestionar versiones del código. GitHub agrega herramientas para compartir ese trabajo con otros, crear Pull Requests, revisar cambios y mantener un historial accesible desde internet.

## 2. ¿Para qué sirve `.gitignore`?

### Respuesta
`.gitignore` sirve para indicar a Git qué archivos o carpetas no deben incluirse en el seguimiento del repositorio.

### Explicación
Esto permite evitar que archivos temporales, configuraciones locales, dependencias instaladas o datos sensibles se guarden en el historial. En este proyecto se excluye `.venv/`, archivos `__pycache__/`, archivos `.pyc`, `.env` y archivos macOS como `.DS_Store`.

## 3. ¿Por qué `.venv` no debe almacenarse normalmente en GitHub?

### Respuesta
Porque `.venv` contiene un entorno virtual local con dependencias y configuraciones específicas del equipo o la computadora.

### Explicación
Cada entorno virtual puede variar según la versión de Python, paquetes instalados y configuración del sistema. Mantenerlo en GitHub no es recomendable porque aumenta el tamaño del repositorio y puede causar inconsistencias entre desarrolladores.

## 4. ¿Para qué sirve `requirements.txt`?

### Respuesta
`requirements.txt` sirve para listar las dependencias del proyecto y permitir que otros usuarios o entornos puedan instalarlas con el mismo conjunto de bibliotecas.

### Explicación
Cuando alguien desea reproducir el proyecto, puede ejecutar `pip install -r requirements.txt` para instalar exactamente las librerías necesarias. Esto facilita la colaboración y la ejecución del proyecto en otros equipos.

## 5. Diferencia entre Stage, Commit y Push

### Respuesta
- `Stage` (`git add`): prepara los cambios para el siguiente commit.
- `Commit`: guarda una instantánea del estado actual del repositorio con un mensaje descriptivo.
- `Push`: envía esos commits al repositorio remoto, por ejemplo GitHub.

### Explicación
El flujo lógico es: modificar archivos → `git add` → `git commit` → `git push`. Cada paso cumple una función diferente, y la combinación ayuda a mantener un historial ordenado y reproducible.

## 6. ¿Por qué un repositorio puede tener varios commits antes de realizar un push?

### Respuesta
Porque un desarrollador puede hacer varios cambios y guardarlos localmente en distintos momentos antes de publicar el trabajo en GitHub.

### Explicación
Cada commit representa un punto de guardado del proyecto. Esto permite documentar el progreso, separar cambios por tareas y corregir errores de forma ordenada antes de compartir la versión final con el repositorio remoto.
