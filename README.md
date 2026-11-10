# Skills de Clan Digital para Claude

Skills de [Clan Digital](https://clandigital.es) para usar en Claude (claude.ai y Claude Code).

## Cierre de sesión

Hace que Claude te ofrezca un cierre ordenado al terminar cada sesión:

- te pregunta qué tareas quedan abiertas y las lleva a tu herramienta de tareas (Notion,
  Trello, Asana…);
- propone qué conviene recordar para las próximas sesiones;
- te avisa si han quedado contraseñas o datos personales donde no deben;
- en Claude Code, además, borra los ficheros temporales, para los procesos que quedaron
  encendidos y te ayuda a guardar el trabajo.

La primera vez te hace unas preguntas cortas para adaptarse a ti. Después no vuelve a
preguntarlas.

### Instalarla en claude.ai

Funciona con los planes Pro y Max.

1. Activa la ejecución de código en **Settings → Capabilities**. Las skills la necesitan.
2. Entra en **Customize → Plugins**, pulsa **Add → Add marketplace** y escribe:

   ```
   Clan-Digital/claude-skills
   ```

3. Instala el plugin **cierre-de-sesion**.

Si no te aparece la opción de añadir un marketplace, descarga
[cierre-de-sesion.zip](https://github.com/Clan-Digital/claude-skills/raw/main/descargas/cierre-de-sesion.zip)
y súbelo en **Customize → Skills → «+» → Create skill → Upload a skill**. El resultado es el
mismo.

### Instalarla en Claude Code

En la terminal:

```bash
claude plugin marketplace add Clan-Digital/claude-skills
claude plugin install cierre-de-sesion@clan-digital
```

O, dentro de una sesión de Claude Code:

```
/plugin marketplace add Clan-Digital/claude-skills
/plugin install cierre-de-sesion@clan-digital
```

Después abre una sesión nueva: las que ya estaban abiertas no la ven.

### Usarla

Al terminar de trabajar, escribe **«cerramos»**.

- **La primera vez** te hará unas preguntas y te preparará un bloque de texto con tus respuestas:
  - En **Claude Code** te propondrá añadirlo a tu `CLAUDE.md`.
  - En **claude.ai** pégalo tú en las **instrucciones del proyecto**.

  Así Claude se acordará de ofrecerte el cierre cada vez que termines.
- **Para cambiar algo**, edita ese bloque o pídele a Claude «cambia mi cierre de sesión».

### Actualizarla

Cuando haya una versión nueva:

- **Claude Code:** `claude plugin update cierre-de-sesion@clan-digital`.
- **claude.ai:** actualiza el marketplace desde **Customize → Plugins**.

## Licencia

© 2026 Clan Digital. Publicado con licencia
[Creative Commons Atribución-NoComercial 4.0 Internacional (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/deed.es).
El texto completo está en [LICENSE](LICENSE).

- **Puedes** instalar, usar y adaptar estas skills en tu propio trabajo, también en tu negocio.
  Clan Digital te da permiso expreso para ese uso, aunque tu actividad sea comercial.
- **No puedes** venderlas, redistribuirlas a cambio de dinero ni incluirlas en un producto o
  servicio que ofrezcas a terceros sin permiso de Clan Digital.
- Si compartes una versión adaptada, cita a Clan Digital como autor del original.
