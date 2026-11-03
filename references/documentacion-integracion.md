# Buenas prácticas: documentación de la integración

La documentación es buena si un dev de la otra startup hace su primera llamada exitosa en menos de 15 minutos, sin preguntarte nada.

- **Quickstart:** los pasos de cero a la primera llamada, con un ejemplo que se pueda copiar y pegar (curl o colección de Postman).
- **Autenticación:** cómo se pide el token, cuánto dura y cómo se renueva.
- **Especificación:** OpenAPI/Swagger si es API, o la lista de tools con sus parámetros si es un servidor MCP.
- **Ejemplos reales:** request y response de cada paso del flujo acordado, incluidos los casos de error.
- **Errores y límites:** qué significa cada código de error, qué hacer con él, y los límites de uso (rate limits).
- **Modelo de datos:** campos obligatorios y formatos (fechas en ISO 8601, RUT con o sin puntos, zona horaria), y su equivalente FHIR si aplica.
- **Webhooks:** qué eventos existen, cómo es el payload, la política de reintentos y cómo verificar la firma.
- **Versión y contacto:** la versión de la API y quién responde dudas técnicas durante el evento, con su canal.
