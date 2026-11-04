# Integrathon · Skill para Claude

La **Integrathon** es un evento de startups de salud en el marco de la Chile Tech Week 2026. Las startups se conocen y, el mismo día, dejan funcionando la integración técnica de su solución con la de otra (por ejemplo, una ficha clínica con un sistema de agendamiento). El día termina con una demo en vivo.

Este repo es un skill de Claude con el kit para las startups que participan.

- **Cuándo:** miércoles 18 de noviembre de 2026, de 9:30 a 13:30 hrs.
- **Dónde:** Startup Chile, San Isidro 85, piso 9, Santiago.
- **Página del evento:** [luma.com/spapvhk4](https://luma.com/spapvhk4)
- **Cierre de inscripciones:** viernes 13 de noviembre de 2026.

## Startups inscritas

- **Directorio de startups inscritas y aprobadas:** [abrir en el navegador](https://docs.google.com/spreadsheets/d/10Gnf3Vt1tMLQ-0raOMtWFwItFTZDDwK-Y5XHMFjPCo0/edit?usp=sharing) · [CSV](https://docs.google.com/spreadsheets/d/10Gnf3Vt1tMLQ-0raOMtWFwItFTZDDwK-Y5XHMFjPCo0/export?format=csv&gid=0)
- **Inscribe tu startup:** [formulario de inscripción](https://docs.google.com/forms/d/e/1FAIpQLSc14E44nPX4RdupclVU_0ppyNx42DU5UnlTSEMzeBS5nsIrwQ/viewform)

El directorio se actualiza solo. Cada ficha aparece después de una revisión manual de la organización. La revisión no decide quién participa: sirve para que ningún dato de contacto quede público y para evitar contenido malicioso. El directorio no trae datos de contacto. Cuando cierren las inscripciones, 5 días antes del evento, la organización enviará por correo a cada startup inscrita el nombre, correo y teléfono del contacto técnico de las demás. Esos datos no se publican en internet.

Cualquier duda, escribe a integrathon2026@speaknosis.com.

## Qué trae

| Archivo | Para qué sirve |
|---|---|
| `SKILL.md` | Qué es la Integrathon y qué archivo leer para cada cosa |
| `references/presentacion-startup.md` | El pitch de 1 minuto |
| `references/pitch-1-minuto.md` | Buenas prácticas para contar el pitch y armar su slide en HTML |
| `references/que-tener-preparado.md` | Checklist antes del evento |
| `references/documentacion-integracion.md` | Buenas prácticas para documentar tu API o servidor MCP |
| `references/ambiente-sandbox.md` | Buenas prácticas para el ambiente sandbox |
| `references/objetivo-del-dia.md` | Qué cuenta como "integración hecha" |
| `templates/nda-bilateral.md` | Plantilla de NDA bilateral entre las dos startups |

Con el skill instalado, Claude también lee el directorio de startups inscritas para responder quiénes participan y con quién conviene integrarse.

El NDA es una plantilla: cada startup debe revisarlo con su abogado antes de firmarlo.

## Cómo instalarlo

**Claude.ai o la app de escritorio:** descarga el repo como ZIP (Code → Download ZIP) y súbelo en *Settings → Capabilities → Skills*.

**Claude Code:** clona el repo en tu carpeta de skills.

```bash
git clone https://github.com/Speaknosis/integrathon-skill.git ~/.claude/skills/integrathon
```

Después pídele a Claude cosas como "ayúdame a preparar el pitch para la Integrathon" o "revisa la documentación de mi API para la Integrathon".

## Usarlo con ChatGPT o Gemini

El skill está en el formato de Claude, pero todo el contenido es Markdown, así que otras IA lo pueden usar.

**Rápido: pásale el link del repo.** En un chat nuevo, con la navegación web activada, pega `https://github.com/Speaknosis/integrathon-skill` y pregunta, por ejemplo, "¿qué startups se han inscrito en la Integrathon?".

**Completo: crea un GPT personalizado o un Gem.** Así la IA sigue todas las reglas del kit en cada conversación.

1. Descarga el repo como ZIP (Code → Download ZIP) y descomprímelo.
2. Crea un GPT personalizado en ChatGPT (*Explorar GPTs → Crear*) o un Gem en Gemini (*Gems → Nuevo Gem*).
3. En las instrucciones, pega el contenido de `SKILL.md` desde la línea `# Integrathon · Kit para startups` en adelante.
4. Sube como archivos de conocimiento los de `references/` y `templates/`.
5. En un GPT, activa la navegación web para que pueda leer el directorio de inscritas.

Las reglas del kit, como no entregar datos de contacto, son instrucciones para la IA. Los datos de contacto igual nunca están en el directorio, así que ninguna IA los puede sacar de ahí.

## Contacto

Dudas sobre el evento, la inscripción o el contacto con otra startup: integrathon2026@speaknosis.com

## Licencia

[MIT](LICENSE). Úsalo y adáptalo para tu propio evento.

## Aviso legal

El contenido de este repo, incluida la plantilla de NDA, es solo referencial y no constituye asesoría legal. Se entrega tal cual, sin garantías. Speaknosis no se hace responsable por su uso: cada startup debe revisarlo con su propio abogado antes de firmar cualquier acuerdo.
