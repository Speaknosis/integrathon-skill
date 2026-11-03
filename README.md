# Integrathon · Skill para Claude

La **Integrathon** es un evento de startups de salud en el marco de la Chile Tech Week 2026. Las startups se conocen y, el mismo día, dejan funcionando la integración técnica de su solución con la de otra (por ejemplo, una ficha clínica con un sistema de agendamiento). El día termina con una demo en vivo.

Este repo es un skill de Claude con el kit para las startups que participan.

## Qué trae

| Archivo | Para qué sirve |
|---|---|
| `SKILL.md` | Qué es la Integrathon y qué archivo leer para cada cosa |
| `references/presentacion-startup.md` | El pitch de 1 minuto |
| `references/que-tener-preparado.md` | Checklist antes del evento |
| `references/documentacion-integracion.md` | Buenas prácticas para documentar tu API o servidor MCP |
| `references/ambiente-sandbox.md` | Buenas prácticas para el ambiente sandbox |
| `references/objetivo-del-dia.md` | Qué cuenta como "integración hecha" |
| `templates/nda-bilateral.md` | Plantilla de NDA bilateral entre las dos startups |

El NDA es una plantilla: cada startup debe revisarlo con su abogado antes de firmarlo.

## Cómo instalarlo

**Claude.ai o la app de escritorio:** descarga el repo como ZIP (Code → Download ZIP) y súbelo en *Settings → Capabilities → Skills*.

**Claude Code:** clona el repo en tu carpeta de skills.

```bash
git clone https://github.com/Speaknosis/integrathon-skill.git ~/.claude/skills/integrathon
```

Después pídele a Claude cosas como "ayúdame a preparar el pitch para la Integrathon" o "revisa la documentación de mi API para la Integrathon".

## Licencia

[MIT](LICENSE). Úsalo y adáptalo para tu propio evento.

## Aviso legal

El contenido de este repo, incluida la plantilla de NDA, es solo referencial y no constituye asesoría legal. Se entrega tal cual, sin garantías. Speaknosis no se hace responsable por su uso: cada startup debe revisarlo con su propio abogado antes de firmar cualquier acuerdo.
