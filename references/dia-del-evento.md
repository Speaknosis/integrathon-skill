# El día del evento

Miércoles 18 de noviembre de 2026, de 9:30 a 13:30 hrs, en Startup Chile (San Isidro 85, piso 9, Santiago). Las parejas llegan armadas: el match ocurre antes del evento.

## Agenda

| Hora | Bloque |
|---|---|
| 9:30 – 10:00 | Pitch de 1 minuto de cada startup (`references/pitch-1-minuto.md`) |
| 10:00 – 13:00 | Codeo en pareja |
| 13:00 – 13:30 | Demos de las integraciones logradas (`references/objetivo-del-dia.md`) |

Cada demo dura 3 minutos. Si hay más de 9 parejas, baja a 2 minutos para que todas alcancen.

## Hitos del codeo

- **10:00 – 10:20 · Alcance y diagrama.** Una frase con lo que tiene que funcionar a las 13:00, y el diagrama del flujo.
- **11:00 · Primera llamada exitosa** entre los dos sistemas, en sandbox.
- **12:00 · Flujo de punta a punta.** Si a esta hora no funciona, recorten el alcance a lo que sí alcanza a funcionar.
- **12:30 · Se congela el código.** Ensayen la demo y graben un video corto del flujo funcionando, por si falla la conexión en vivo.

## Buenas prácticas

### 1. Nadie codea sin el NDA firmado

El NDA (`templates/nda-bilateral.md`) se firma antes del evento, porque se necesita para compartir documentación y sandbox. El día solo se confirma que está firmado.

### 2. Primero el diagrama

Antes de escribir código, dibujen juntos el flujo: quién llama a quién, en qué orden y qué dato pasa en cada punto de integración. Un solo flujo, el camino feliz, en máximo 20 minutos. Sirve una pizarra, una hoja o un diagrama en [Mermaid](https://mermaid.js.org/).

### 3. Acuerden el contrato con ejemplos reales

Por cada llamada del diagrama, escriban juntos:

- Un ejemplo de request y su response, copiables.
- Los campos obligatorios y sus formatos: fechas en ISO 8601 con zona `America/Santiago`, RUT con o sin puntos, identificadores de paciente y de profesional.
- Al menos un caso de error y cómo se responde. Por ejemplo: el paciente no existe.

Esto evita la mitad de los bugs del día.

### 4. Todo en sandbox, con datos sintéticos

Nunca datos reales de pacientes, ni siquiera anonimizados ni seudonimizados (`references/ambiente-sandbox.md`).

### 5. Autenticación: API Key, sabiendo que es provisoria

Para un día de codeo, una API Key basta. Déjenlo anotado como tarea pendiente: en una integración real se refuerza, por ejemplo con OAuth2 *client credentials* o mTLS.

Cómo manejar las credenciales:

- Una API Key por startup, solo para el sandbox, con los permisos mínimos para el flujo y revocable.
- Se comparte por un canal seguro, con un link que se abre una sola vez, como [Bitwarden Send](https://bitwarden.com/products/send/) o 1Password. Nunca por WhatsApp, Slack, correo ni en una foto de la pantalla.
- Va en un header (por ejemplo `Authorization` o `X-API-Key`), nunca en la URL, y siempre por HTTPS.
- En el código va en variables de entorno, con el `.env` en `.gitignore`. Nunca queda en el repo.
- No la pegues en asistentes de IA. Si codeas con IA, usa variables de entorno y deja que el código las lea.
- Al terminar el evento, cada startup revoca las credenciales que entregó.

### 6. Interoperabilidad: contratos simples, pensando en FHIR

No fuercen FHIR en 3 horas: partan con JSON simple. Pero nombren los datos pensando en FHIR (`Patient`, `Practitioner`, `Appointment`, `Encounter`) y, donde calce sin esfuerzo, usen sus campos. Así pasar a FHIR después es un cambio chico. Como referencia local está la [guía Core-CL de HL7 Chile](https://hl7chile.cl/fhir/ig/clcore/).

### 7. Logs que vean los dos

Cada request lleva un identificador (por ejemplo, el header `X-Request-Id`) que ambos sistemas registran. Cuando algo falla entre dos equipos, ese identificador dice en qué lado se cortó.

### 8. Webhooks: prueben el túnel antes

Si su flujo recibe webhooks, el sandbox tiene que ser accesible desde internet. Si corre en un notebook, levanten un túnel con [ngrok](https://ngrok.com) o [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) y pruébenlo antes del evento: es lo que más falla con el WiFi de un evento.

## Al terminar

- Demo en vivo y próximo paso acordado (`references/objetivo-del-dia.md`).
- Revoquen las credenciales del sandbox que entregaron.
