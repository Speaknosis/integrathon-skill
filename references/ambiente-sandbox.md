# Buenas prácticas: ambiente sandbox

En el sandbox solo hay datos sintéticos, creados desde cero para las pruebas. No se copia producción, ni siquiera anonimizada o seudonimizada: anonimizar datos de salud es difícil, y un error expone a pacientes reales.

- **Datos inventados y evidentes:** nombres como "Paciente Prueba 001". Para datos clínicos realistas sirve un generador como [Synthea](https://synthetichealth.github.io/synthea/), que exporta en FHIR.
- **Datos precargados para el flujo:** por ejemplo, 20 pacientes, 5 profesionales y la agenda de una semana, para no partir con el sistema vacío.
- **Separado de producción:** otra URL, otra base de datos y otras credenciales. Nada del sandbox llega a producción.
- **Sin efectos reales:** no envía SMS, correos ni cobros de verdad. Si hay notificaciones, se registran en un log en vez de enviarse.
- **Credenciales por startup:** con los permisos mínimos para el flujo, revocables, y se rotan al terminar el evento.
- **Reseteable:** se puede volver al estado inicial con un comando, para repetir la demo desde cero.
- **Estable el día del evento:** probado la semana antes, con un endpoint de health check y logs que la otra startup pueda ver para depurar.
