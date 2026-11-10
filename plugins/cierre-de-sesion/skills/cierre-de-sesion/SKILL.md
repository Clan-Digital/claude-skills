---
name: cierre-de-sesion
description: Protocolo de cierre de sesión. Úsalo cuando el usuario pida cerrar la sesión o hacer el cierre («cierre», «cerramos», «protocolo de cierre»). Ofrécelo tú, sin lanzarlo, cuando el usuario dé señales de que termina («lo dejo por hoy», «ya está», «cierro», «hasta mañana»). También cuando pida configurar o cambiar su cierre de sesión.
---

# Cierre de sesión

Sirve para que el trabajo de la sesión no se quede solo en la conversación y para que no queden
restos: ficheros sueltos, procesos encendidos o datos sensibles donde no deben estar.

**Nunca lances el cierre por tu cuenta.** Ofrécelo cuando el usuario dé señales de que termina.
La decisión es suya, y se pregunta antes de cada paso que cambie algo.

## 0. La primera vez: configurarlo

Busca la configuración del cierre:

- **En Claude Code:** una sección `## Cierre de sesión` en el `CLAUDE.md` del proyecto (o en
  `~/.claude/CLAUDE.md`).
- **En claude.ai:** una sección `Cierre de sesión` en las instrucciones del proyecto o en lo que
  recuerdes del usuario.

Si no está, hazle estas preguntas antes del primer cierre, todas juntas y cortas:

1. Cómo quiere que le llames.
2. Dónde lleva sus tareas (Notion, Trello, Asana, una hoja, una libreta…) y si tienes conector
   con esa herramienta.
3. Si hay algún documento de seguimiento que quiera actualizar al cerrar. Puede no haberlo.
4. Solo en Claude Code:
   - Si guarda el trabajo en un repositorio (GitHub u otro) y cómo lo sube normalmente.
   - Si en sus sesiones se tocan servidores, y cuáles.

Con las respuestas, prepara este bloque:

```markdown
## Cierre de sesión

Cuando dé señales de que termina, ofréceme el cierre de sesión (skill `cierre-de-sesion`).
No lo lances sin mi sí.

- Nombre: …
- Tareas: … (conector: sí/no)
- Seguimiento: … (o «ninguno»)
- Repositorio: … y cómo se sube (o «ninguno»)        ← solo Claude Code
- Servidores: … (o «ninguno»)                        ← solo Claude Code
```

- **En Claude Code:** enséñaselo y, con su sí, añádelo al `CLAUDE.md` del proyecto (o al
  general si quiere el cierre en todos sus proyectos).
- **En claude.ai:** no puedes escribir en las instrucciones del proyecto. Dale el bloque para
  que lo pegue él en las instrucciones del proyecto.

Si quiere cambiar algo más adelante, se edita ese bloque.

## 1. Lo que se le pregunta

1. **Si hay que actualizar su documento de seguimiento** con lo hecho en la sesión. Si no
   tiene, sáltalo.
2. **Si hay que tocar su herramienta de tareas.** Con conector, se actualiza directamente. Sin
   conector, prepara el texto de cada tarea para que lo copie.
3. **Si algo de lo pendiente pasa a una fecha concreta** o se queda sin fecha.

## 2. Lo que revisas tú

- **Revisar lo aparcado.** Durante la sesión, aparca en la conversación lo que no bloquea la
  tarea: mejoras, retoques, cosas que salen de paso. En el cierre enséñaselo en una lista,
  marca lo que recomiendas conservar y pregunta qué pasa a su herramienta de tareas. Lo que no
  elija se descarta, y lo dices en una línea. **Su herramienta de tareas es la única lista de
  tareas**: no las escribas en ningún fichero, porque una segunda lista acaba contradiciendo a
  la primera.
- **Lecciones.** Si la sesión ha dejado algo que convenga recordar en futuras sesiones,
  propónlo: en Claude Code, como memoria o en el `CLAUDE.md`; en claude.ai, como texto para las
  instrucciones o el conocimiento del proyecto. Comprueba antes que no esté ya.
- **Datos sensibles.** Si se han pegado contraseñas, claves o datos personales, recuérdale que
  no los deje en documentos, artefactos ni ficheros compartidos.

### Solo en Claude Code

Si tienes acceso a terminal y a ficheros, revisa también:

- **Ficheros temporales de la sesión**: scripts de un solo uso, copias de trabajo, capturas,
  versiones descartadas. Se borran con su sí.
- **Que no se haya escapado nada** a `/tmp`, a la carpeta del proyecto o al directorio de
  trabajo. Se conserva solo el entregable y su documentación.
- **Que no quede ningún servidor ni proceso en marcha** lanzado en la sesión:
  `lsof -nP -iTCP -sTCP:LISTEN` y `ps` para servidores web locales (`http.server`, `serve`,
  `php -S`…), transcripciones o `caffeinate`. Lo que arrancó la sesión, se para. Un servidor
  local solo se lanza con permiso, en `127.0.0.1` y sirviendo una carpeta sin credenciales: uno
  abierto a toda la red puede dejar a la vista un `.env` sin que nadie se dé cuenta.
- **Credenciales**: que los `.env` sigan en permisos `600` y que el `.gitignore` cubra secretos
  y copias de seguridad.
- **Servidores**, si en la sesión se tocó alguno: el `/tmp` y el home del usuario SSH, por si
  quedaron scripts o ficheros de prueba. **Nunca borres nada en producción sin preguntar**: se
  informa, se explica por qué sobra y se espera confirmación.
- **Guardar el trabajo**, si usa repositorio:
  - Cada sesión guarda solo lo suyo. Nunca `git add -A`: se añaden rutas explícitas de los
    ficheros que ha tocado esta sesión. Lo que aparezca cambiado por otras sesiones se deja
    como está.
  - Enséñale la lista de ficheros en lenguaje llano y, con su visto bueno, súbelo como suele
    hacerlo, con un mensaje que explique qué se hizo y por qué.
  - Comprueba que ha llegado: que el remoto tiene lo mismo que la carpeta local.

## 3. Para terminar

Cierra con un resumen corto: qué se hizo, qué queda abierto, qué depende de una decisión suya
y qué se encontró de paso. Lo que haya que recordar va a su herramienta de tareas, no a un
fichero.

Un aviso que ya se ha dado y sobre el que ha decidido no actuar no se repite en cada cierre: se
anota la decisión y se calla, salvo que cambien las circunstancias.
