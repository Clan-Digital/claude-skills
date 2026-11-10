# Skills de Clan Digital para Claude

Skills de [Clan Digital](https://clandigital.es) para usar en Claude (claude.ai y Claude Code).
Cada skill vive en su propia carpeta, con sus instrucciones.

| Skill | Qué hace |
|---|---|
| [protocolo-de-cierre](protocolo-de-cierre/) | Cierre de sesión ordenado: tareas abiertas a tu herramienta de tareas, lecciones que recordar, datos sensibles y limpieza de restos de la sesión. Se configura sola la primera vez. |

## Cómo se instalan

Este repositorio es un marketplace de plugins para Claude. Se añade una vez y desde ahí se
instala cada skill.

- **claude.ai (Pro o Max):** activa la ejecución de código en **Settings → Capabilities**. Luego
  ve a **Customize → Plugins → Add → Add marketplace**, escribe `Clan-Digital/claude-skills` e
  instala la skill que quieras.
- **Claude Code:** `claude plugin marketplace add Clan-Digital/claude-skills` y después
  `claude plugin install <skill>@clan-digital`.

Cada carpeta tiene además un zip para subirlo a mano en claude.ai si no aparece la opción de
añadir marketplaces. Los detalles están en el README de cada skill.

## Licencia

© 2026 Clan Digital. Publicado con licencia
[Creative Commons Atribución-NoComercial 4.0 Internacional (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/deed.es).
El texto completo está en [LICENSE](LICENSE).

- **Puedes** instalar, usar y adaptar estas skills en tu propio trabajo, también en tu negocio.
  Clan Digital te da permiso expreso para ese uso, aunque tu actividad sea comercial.
- **No puedes** venderlas, redistribuirlas a cambio de dinero ni incluirlas en un producto o
  servicio que ofrezcas a terceros sin permiso de Clan Digital.
- Si compartes una versión adaptada, cita a Clan Digital como autor del original.
