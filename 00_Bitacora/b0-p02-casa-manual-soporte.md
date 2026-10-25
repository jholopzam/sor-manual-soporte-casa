# b0-p02-casa-manual-soporte

- **Alumno:** Jhoseen Lopez zambano
- **Bloque:** B0 — Fase 0.8
- **Fase / ejercicio:** Fase 0.8 · Práctica 02 (Casa)
- **Fecha de inicio:** 23/10/2026
- **Fecha de entrega:** 25/10/2026

---

## 🎯 Qué se pedía

Crear un manual de soporte técnico desde cero en la bóveda "Boveda_Manual_Casa" dentro de la carpeta "01_Proyecto". El objetivo era practicar el ciclo completo de Git : registrar tres versiones progresivas, configurar `.gitignore` para excluir archivos multimedia/auxiliares, consultar el historial y el commit inicial con `git switch --detach` sin alterar el trabajo, volver a la rama `main` y subir todo el progreso a GitHub.

## ⌨️ Comandos y pasos importantes

- `git init`: Inicializa el repositorio Git en la carpeta actual (`01_Proyecto`).
- `git branch -M main`: Renombra la rama por defecto a `main`.
- `git remote add origin git@github.com:jholopzam/sor-manual-soporte-casa.git`: Asocia el repositorio remoto de GitHub por SSH.
- `git add <archivo>`: Añade archivos específicos al área de preparación (staging/index).
- `git status --short --untracked-files=all`: Muestra el estado de los archivos y los no seguidos de forma resumida.
- `git diff --cached`: Compara los cambios preparados en el índice contra el último commit antes de guardar.
- `git commit -m "<mensaje>"`: Crea una versión local con un mensaje descriptivo.
- `git push -u origin main` / `git push`: Sube las versiones locales al repositorio remoto en GitHub.
- `git check-ignore -v <archivo>`: Comprueba qué regla del `.gitignore` está ignorando un archivo en concreto.
- `git log --oneline`: Muestra un resumen del historial de commits en una sola línea por commit.
- `git switch --detach <hash>`: Cambia el espacio de trabajo al estado exacto de un commit antiguo para consultarlo.
- `git switch main`: Regresa a la rama principal con todo el trabajo más reciente e intacto.

## 🛠️ Qué he hecho

1. **Comprobación inicial:** Verifiqué la versión de Git, la identidad global (`user.name` y `user.email`) y la conexión SSH a GitHub mediante "ssh -T git@github.com".
2. **Estructura e inicialización:** Creé la bóveda en una ruta local independiente y construí el árbol de carpetas. En `01_Proyecto` creé la bitácora, el `.gitignore` y los archivos iniciales (`README.md` y `sin-conexion.md`).
3. **Primer commit y remoto:** Inicialicé Git en `01_Proyecto`, vinculé el remoto SSH en GitHub (`sor-manual-soporte-casa`), preparé de manera individual los archivos iniciales, revisé con `git diff --cached`, hice el primer commit (`Crear manual inicial de soporte`) y lo subí con `git push -u origin main`.
4. **Segunda versión:** Modifiqué `sin-conexion.md` para intercambiar las instrucciones comprobando primero el cable de red. Comprobé las diferencias con `git diff`, preparé el archivo, hice el commit (`Corregir comprobacion de conexion del manual`) y subí los cambios.
5. **Ampliación y reglas de exclusión:** Creé las carpetas `imagenes/` y `videos/`. Redacté los procedimientos `impresora.md` y `sin-sonido.md`, actualicé el `README.md` con enlaces y la imagen `diagnostico.png`, y añadí dos vídeos de prueba `.mp4` en `manual/videos/`.
6. **Verificación de ignorados y preparación individual:** Usé `git check-ignore -v` para confirmar que los vídeos quedaban excluidos por `.gitignore`. Preparé uno por uno los 4 archivos válidos, revisé con `git diff --cached
7. , guardé el commit (`Anadir impresora sonido e imagen al manual`) y subí a GitHud.
8. **Consulta de versión anterior:** Revisé el historial con `git log --oneline`, cambié al primer commit con `git switch --detach`para comprobar el estado antiguo del procedimiento sin modificar nada, y volví a `main` mediante `git switch main` dejando el árbol limpio.
9. **Cierre:** Grabé las comprobaciones finales, subí el vídeo y completé este documento con los enlaces requeridos.

## 🚩 Qué me ha fallado y cómo lo he resuelto

ningún fallo el único es que todavía no lo hago como de memoria pero eso poco a poco me acostumbro 
## 🤔 Respuestas a las preguntas

1. **¿Por qué Git se inicializa solo en 01_Proyecto y la grabación queda fuera?**  
   Porque `01_Proyecto` contiene el código fuente y la documentación versionable del producto. La raíz de la bóveda contiene la grabación del vídeo y la configuración de Obsidian (`.obsidian/`), los cuales son recursos locales o pesados que no deben formar parte del historial de control de versiones ni subirse al remoto.

2. **¿Qué muestran status y diff antes de preparar la corrección del procedimiento? Cita la instrucción anterior y la nueva.**  
   `git status` muestra `manual/procedimientos/sin-conexion.md` como modificado sin preparar (` M`). `git diff` muestra las líneas eliminadas (`-`) e insertadas (`+`).  
   - *Anterior:* `1. Abre el navegador y prueba la página interna.` / `2. Comprueba visualmente que el cable de red está conectado.`
   - *Nueva:* `1. Comprueba visualmente que el cable de red está conectado.` / `2. Abre el navegador y prueba la página interna.`

3. **¿Por qué un archivo nuevo aparece en status pero no en el diff de README.md?**  
   Porque los archivos totalmente nuevos son "untracked" (sin seguimiento) y Git aún no conoce su historial previo para hacer una comparación de diferencias de contenido línea a línea. `git diff` solo compara modificaciones sobre archivos que ya están en el índice o bajo seguimiento.

4. **¿Qué preparas con cada add y qué compruebas con diff --cached antes del commit?**  
   Con cada `git add` se añade al índice (staging area) la foto/estado exacto del archivo en ese momento. Con `git diff --cached` se revisan las diferencias exactas entre lo preparado en el índice y el último commit para asegurar que no se incluyan archivos indeseados, errores de formato o archivos ignorados antes de consolidar la versión.

5. **¿Qué demuestra check-ignore y qué comprobaste además para saber que los clips existen?**  
   `check-ignore` demuestra exactamente qué patrón del `.gitignore` (y en qué línea) bloquea la inclusión del archivo en Git. Además, se comprobó la existencia física de los clips en el explorador de archivos y su correcta reproducción local en el reproductor multimedia.

6. **¿Qué diferencias concretas observaste en el manual del primer commit y qué recuperaste al volver a main?**  
   En el primer commit, el procedimiento de conexión tenía el orden antiguo (navegador primero, cable después) y no existían los procedimientos de impresora, sonido, la imagen ni sus enlaces en el `README.md`. Al regresar a `main`, se recuperó toda la estructura ampliada, los archivos nuevos y la versión corregida del procedimiento de red.

7. **¿Qué aporta un historial cuando dos técnicos necesitan conocer el procedimiento vigente?**  
   Permite auditar en qué fecha y commit se modificó una instrucción, entender por qué se cambió, comparar versiones pasadas ante incidencias y garantizar que todos sigan la única versión oficial aprobada publicada en la rama `main`.

8. **¿Por qué commit y push son acciones diferentes y qué miraste en GitHub?**  
   `git commit` es una operación local que guarda una instantánea en el repositorio de la máquina. `git push` transfiere esos commits locales al servidor remoto en GitHub. En GitHub se comprobó visualmente que la rama `main` mostraba los 3 commits del producto, el renderizado del `README.md` con su imagen y la ausencia total de los archivos multimedia ignorados.

9. **¿Qué pasos repetirías para corregir otra instrucción y cuáles se hicieron una sola vez?**  
   - *Se repiten:* Editar los archivos, revisar con `git diff`, preparar con `git add`, comprobar con `git diff --cached`, hacer `git commit` y subir con `git push`.  
   - *Se hacen una sola vez:* `git init`, `git branch -M main`, la creación y vinculación del remoto `git remote add origin`, y la configuración inicial de `.gitignore`.

## 🔗 Enlaces

- **Repositorio en GitHub:** [https://github.com/jholopzam/sor-manual-soporte-casa](https://github.com/jholopzam/sor-manual-soporte-casa.git)
- **Vídeo de esta fase:** [https://youtu.be/XXXXXXXXXXX](https://youtu.be/WDRoXy1NXV8)
- **Playlist:** https://youtube.com/playlist?list=PLGtQOzJQwin0&si=O75addHyfQNmuUzr

## 💭 Dudas / a repasar

- Ninguna duda pendiente tras completar la práctica y verificar las versiones en GitHub.