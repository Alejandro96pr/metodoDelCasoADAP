# Método del Caso ADAP

Repositorio de trabajo del equipo para el proyecto **Turbine**. Por ahora contiene la documentación y la organización inicial. Las tecnologías, sus versiones y los comandos para ejecutar la aplicación se añadirán aquí cuando estén decididos.

## Antes de empezar

1. Instala **Git** en tu portátil y comprueba que funciona:

   ```bash
   git --version
   ```

2. Configura tu identidad de Git **una sola vez en cada portátil**. Sustituye el nombre y el correo por los tuyos:

   ```bash
   git config --global user.name "Tu Nombre Apellido"
   git config --global user.email "tu-correo@example.com"
   ```

3. Para subir cambios, necesitas acceso de escritura al repositorio en GitHub y autenticarte cuando Git te lo solicite. Si el repositorio es privado, también necesitas acceso para clonarlo.

Puedes usar la Terminal de macOS o Linux, o **Git Bash** en Windows. Ejecuta los comandos siguientes desde la carpeta de tu portátil en la que quieras guardar el proyecto.

## Descargar el repositorio por primera vez

```bash
git clone https://github.com/Alejandro96pr/metodoDelCasoADAP.git
cd metodoDelCasoADAP
git status
```

`git clone` crea la carpeta `metodoDelCasoADAP` con el proyecto y su historial. Este paso se hace **una sola vez por portátil**. Si ya tienes esa carpeta clonada, entra en ella con `cd` y sigue con la sección siguiente; no vuelvas a clonarla encima.

## Empezar una tarea

Desde la carpeta del repositorio, actualiza `main` y crea una rama para tu tarea:

```bash
git switch main
git pull --ff-only origin main
git switch -c tu-nombre/descripcion-tarea
```

Sustituye `tu-nombre/descripcion-tarea` por un nombre propio y descriptivo, por ejemplo `ana/diagrama-casos-uso`. Usa una rama nueva para cada tarea y evita editar directamente en `main`.

Antes de trabajar en una rama que ya habías creado, comprueba dónde estás y trae los cambios de tus compañeros. Si `git status` muestra cambios tuyos sin guardar, haz un commit antes de combinar las ramas:

```bash
git status
git fetch origin
git merge origin/main
```

Si Git indica un conflicto, abre los archivos señalados, decide qué contenido conservar, guarda los cambios y termina la combinación con `git add` y `git commit`. Si no sabes cómo resolverlo, consulta al equipo antes de descartar cambios.

## Guardar y subir tus cambios

Al terminar una parte de la tarea, revisa lo modificado y añade **solo los archivos de esa tarea**. En el ejemplo se usa `ScrumDistribution.md`: cámbialo por el archivo que hayas editado. Repite `git add` para cada archivo que quieras incluir.

```bash
git status
git diff
git add ScrumDistribution.md
git diff --cached
git commit -m "Actualiza la distribución de tareas"
git push -u origin HEAD
```

`git diff --cached` muestra exactamente lo que entrará en el commit. `git push -u origin HEAD` sube la rama actual y la vincula con GitHub; las siguientes veces, en esa misma rama, basta con `git push`.

Después, abre [el repositorio en GitHub](https://github.com/Alejandro96pr/metodoDelCasoADAP) y crea una **Pull Request** desde tu rama hacia `main` para que el equipo revise e integre los cambios. Subir una rama no modifica `main` automáticamente.

## Continuar después de integrar una tarea

Una vez aceptada la Pull Request, actualiza tu copia local antes de iniciar otra tarea:

```bash
git switch main
git pull --ff-only origin main
git switch -c tu-nombre/siguiente-tarea
```

Si aún tienes cambios sin guardar al cambiar de rama, haz primero un commit en la rama correspondiente. No uses `git reset --hard` ni fuerces un `push` para resolver errores: esos comandos pueden eliminar trabajo.

## Documentos actuales

- [Distribución de tareas Scrum](ScrumDistribution.md)
- [Resumen del caso Turbine](Turbine_resumen_para_el_equipo.md)

