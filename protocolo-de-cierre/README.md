# Protocolo de cierre de sesión

Hace que Claude te ofrezca un cierre ordenado al terminar cada sesión:

- te pregunta qué tareas quedan abiertas y las lleva a tu herramienta de tareas (Notion,
  Trello, Asana…);
- propone qué conviene recordar para las próximas sesiones;
- te avisa si han quedado contraseñas o datos personales donde no deben;
- en Claude Code, además, borra los ficheros temporales, para los procesos que quedaron
  encendidos y te ayuda a guardar el trabajo.

La primera vez te hace unas preguntas cortas para adaptarse a ti. Después no vuelve a
preguntarlas.

## Instalarla en claude.ai

Funciona con los planes Pro y Max.

1. Activa la ejecución de código en **Settings → Capabilities**. Las skills la necesitan.
2. Entra en **Customize → Plugins**, pulsa **Add → Add marketplace** y escribe:

   ```
   Clan-Digital/claude-skills
   ```

3. Instala el plugin **protocolo-de-cierre**.

Si no te aparece la opción de añadir un marketplace, descarga
[protocolo-de-cierre.zip](https://github.com/Clan-Digital/claude-skills/raw/main/protocolo-de-cierre/protocolo-de-cierre.zip)
y súbelo en **Customize → Skills → «+» → Create skill → Upload a skill**. El resultado es el
mismo.

## Instalarla en Claude Code

Lo más fácil es pedírselo a Claude Code. Abre una sesión y pega:

```
Instala el plugin protocolo-de-cierre del marketplace Clan-Digital/claude-skills
(claude plugin marketplace add Clan-Digital/claude-skills y después
claude plugin install protocolo-de-cierre@clan-digital) y dime cuándo está.
```

Si prefieres hacerlo tú, en la terminal:

```bash
claude plugin marketplace add Clan-Digital/claude-skills
claude plugin install protocolo-de-cierre@clan-digital
```

O, dentro de una sesión de Claude Code:

```
/plugin marketplace add Clan-Digital/claude-skills
/plugin install protocolo-de-cierre@clan-digital
```

Después abre una sesión nueva: las que ya estaban abiertas no la ven.

## Usarla

Al terminar de trabajar, escribe **«cerramos»**.

- **La primera vez** te hará unas preguntas y te preparará un bloque de texto con tus respuestas:
  - En **Claude Code** te propondrá añadirlo a tu `CLAUDE.md`.
  - En **claude.ai** pégalo tú en las **instrucciones del proyecto**.

  Así Claude se acordará de ofrecerte el cierre cada vez que termines.
- **Para cambiar algo**, edita ese bloque o pídele a Claude «cambia mi cierre de sesión».

## Actualizarla

Cuando haya una versión nueva:

- **Claude Code:** `claude plugin update protocolo-de-cierre@clan-digital`.
- **claude.ai:** actualiza el marketplace desde **Customize → Plugins**.

## Licencia

CC BY-NC 4.0 con permiso expreso para usarla en tu propio negocio. Detalles en el [README principal](../README.md#licencia).
