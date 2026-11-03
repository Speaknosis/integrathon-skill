# Buenas prácticas: pitch de 1 minuto

El contenido del pitch está en `references/presentacion-startup.md`. Este archivo dice cómo contarlo y cómo armar la slide.

El pitch es bueno si, al terminar, otra startup sabe en qué se puede integrar contigo y te busca en el break.

## Cómo contarlo

- **Unas 130 palabras.** Es lo que cabe en un minuto hablando tranquilo. Escríbelo, léelo en voz alta con cronómetro y corta hasta que entre en 55 segundos.
- **Habla de integración, no de inversión.** No van inversionistas a escucharte: nada de mercado, ronda ni valorización. Lo que importa es qué expones y qué datos entran y salen.
- **Un ejemplo concreto vale más que una lista.** "Cuando una clínica agenda una hora, nosotros creamos la consulta en la ficha" se entiende mejor que "tenemos API REST, webhooks y FHIR".
- **Cierra con lo que buscas.** La última frase dice con qué tipo de solución te quieres integrar. Es lo que la gente recuerda.
- **Sin demo ni video.** No cabe en un minuto y es lo primero que falla con el proyector.
- **Habla una persona.** Cambiar de orador en un minuto se come tiempo.

## Cómo armar la slide en HTML

Cuando te pidan la slide, genera **un solo archivo `.html`** con la plantilla de abajo y complétala con los datos de la startup.

Reglas:

- **Una sola slide en 16:9.** Sin animaciones, transiciones ni scroll.
- **Archivo autocontenido.** Todo el CSS va dentro del archivo, sin CDN ni Google Fonts, para que funcione sin internet en el evento. Si hay logo, va como SVG en línea o como imagen en base64.
- **Máximo 40 palabras en la slide.** La slide acompaña, no se lee: el resto lo dice la persona que presenta.
- **Letra grande.** El texto más chico debe leerse desde el fondo de la sala, así que no uses menos de unos 24 px en una pantalla de 1920 × 1080.
- **Contraste alto y colores de la marca.** Si la startup tiene colores o tipografía propios, ponlos en las variables de `:root`. Si no, deja los de la plantilla.
- **Sin datos de contacto.** Ni correos, ni teléfonos, ni links, ni redes sociales, ni nombres de personas: la slide se proyecta y circula. El contacto entre startups lo coordina la organización.
- **Los cinco bloques del pitch.** Quiénes somos, para quién, qué exponemos, qué datos entran y salen, y con quién queremos integrarnos. Solo palabras clave, no frases completas.
- **Exportable a PDF.** La plantilla trae estilos de impresión: en el navegador, Imprimir → Guardar como PDF, en horizontal. Lleva el PDF de respaldo por si el HTML no abre en el computador del evento.

Antes de entregarla, ábrela en el navegador y revisa que nada se corte ni se salga de la slide, con la ventana grande y con la ventana chica.

### Plantilla

```html
<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>[Nombre startup] · Integrathon</title>
<style>
  :root {
    --fondo: #0f172a;
    --texto: #f8fafc;
    --suave: #94a3b8;
    --acento: #38bdf8;
    --tarjeta: #1e293b;
    --fuente: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  }
  * { box-sizing: border-box; margin: 0; }
  html, body { height: 100%; background: #000; }
  body { display: grid; place-items: center; font-family: var(--fuente); }

  /* La slide siempre ocupa el máximo posible en 16:9. Todo se mide en cqw
     (1 cqw = 1% del ancho de la slide) para que escale igual en cualquier pantalla. */
  .slide {
    width: min(100vw, 177.78vh);
    aspect-ratio: 16 / 9;
    container-type: inline-size;
    background: var(--fondo);
    color: var(--texto);
    padding: 4.5cqw 5cqw;
    display: grid;
    grid-template-rows: auto 1fr auto;
    gap: 3cqw;
    overflow: hidden;
  }

  header { display: flex; align-items: center; gap: 2cqw; }
  .logo { height: 5cqw; width: auto; }
  h1 { font-size: 4.4cqw; line-height: 1.05; }
  .problema { font-size: 2.2cqw; color: var(--suave); margin-top: 0.6cqw; }

  .bloques { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.6cqw; align-content: center; }
  .bloque { background: var(--tarjeta); border-radius: 1.2cqw; padding: 2cqw; }
  .bloque.ancho { grid-column: span 2; }
  .etiqueta { font-size: 1.3cqw; letter-spacing: 0.12em; text-transform: uppercase; color: var(--acento); font-weight: 700; }
  .valor { font-size: 2.3cqw; line-height: 1.25; margin-top: 0.8cqw; font-weight: 600; }

  footer { display: flex; justify-content: space-between; align-items: baseline; font-size: 1.6cqw; color: var(--suave); }
  .busco { font-size: 2.4cqw; color: var(--texto); font-weight: 700; }
  .busco strong { color: var(--acento); }

  @page { size: 1920px 1080px; margin: 0; }
  @media print {
    html, body { background: var(--fondo); }
    .slide { width: 1920px; height: 1080px; }
    * { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  }
</style>
</head>
<body>
  <main class="slide">
    <header>
      <!-- Logo opcional: <img class="logo" src="data:image/svg+xml;base64,..." alt="[Nombre startup]"> -->
      <div>
        <h1>[Nombre startup]</h1>
        <p class="problema">[Qué problema resolvemos, en una frase]</p>
      </div>
    </header>

    <section class="bloques">
      <div class="bloque">
        <p class="etiqueta">Para quién</p>
        <p class="valor">[Clínicas, profesionales o pacientes · N usuarios]</p>
      </div>
      <div class="bloque">
        <p class="etiqueta">Qué exponemos</p>
        <p class="valor">[API REST · Webhooks · FHIR · MCP]</p>
      </div>
      <div class="bloque">
        <p class="etiqueta">Entra</p>
        <p class="valor">[Ej: hora agendada]</p>
      </div>
      <div class="bloque ancho">
        <p class="etiqueta">Ejemplo de integración</p>
        <p class="valor">[Ej: la hora agendada crea la consulta en la ficha]</p>
      </div>
      <div class="bloque">
        <p class="etiqueta">Sale</p>
        <p class="valor">[Ej: informe clínico]</p>
      </div>
    </section>

    <footer>
      <p class="busco">Buscamos integrarnos con <strong>[tipo de solución]</strong></p>
      <p>Integrathon 2026</p>
    </footer>
  </main>
</body>
</html>
```
