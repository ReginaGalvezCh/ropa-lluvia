# Especificación 001: alerta de lluvia con ropa tendida

**Estado:** propuesta para validar. No hay ubicación, sensor ni prototipo físico validados.

## Propósito y escena

Dar tiempo para retirar ropa tendida en un balcón estrecho cuando aparece lluvia que podría alcanzarla. La persona indica que dejó ropa afuera y puede alejarse del balcón. Este piloto no mide si la ropa está seca.

## Alcance del primer piloto

- La persona activa o desactiva manualmente «hay ropa afuera». El estado debe ser visible junto al tendedero y fácil de cambiar al colgar o retirar la ropa.
- El módulo observa lluvia en un punto cercano y representativo de la exposición de la ropa.
- Si «hay ropa afuera» está activo y se detecta lluvia sostenida, emite una señal local.
- Si «hay ropa afuera» está inactivo, no emite un aviso para entrar ropa.
- Si la medición falla o vence, señala «estado de lluvia desconocido», sin tratarlo como seco.
- Evita repetir continuamente el mismo aviso. La forma de silenciarlo y restablecerlo se decidirá tras observar el uso.

La pantalla central y el transporte de mensajes quedan fuera del piloto. Una integración futura deberá entregar origen, tipo, severidad, hora de lectura y vigencia mediante un contrato compartido aún no acordado.

## Ubicación y protección: decisión antes de elegir hardware

Comparar al menos dos puntos de montaje posibles junto al tendedero. Para cada uno, registrar con foto o croquis:

1. Distancia y altura respecto de la ropa; si recibe agua cuando la ropa la recibe y si queda bajo un techo o borde distinto.
2. Exposición a lluvia con viento, goteo desde arriba, riego, salpicaduras y condensación.
3. Espacio de paso en el balcón, estabilidad de la sujeción y acceso para activar «hay ropa afuera».
4. Ruta del agua lejos de la electrónica, necesidad de mantener expuesta la zona que detecta lluvia y acceso para mantenimiento.
5. Alcance de la señal local desde dentro del departamento y posible ubicación de la alimentación.

No se elegirá una placa, sensor, carcasa definitiva ni alimentación hasta revisar estos puntos y las primeras observaciones en el lugar. Ninguna pieza energizada se expondrá al agua durante la exploración inicial.

## Modo «hay ropa afuera»

La activación manual es la referencia inicial. No se inferirá la presencia de ropa a partir de humedad o lluvia. Antes de implementar, decidir si el mando será un interruptor de posición o un botón con indicador; en ambos casos, la persona debe poder reconocer el estado vigente. Tras un reinicio, el estado no debe quedar ambiguo ni pasar silenciosamente a «sin ropa»: se probará cómo se conserva o se pide confirmación.

Riesgo de uso: olvidar activar el modo al tender, o dejarlo activo después de retirar la ropa. Registrar ambos errores en las pruebas de uso; una detección automática solo se considerará si aportara una mejora demostrable.

## Regla de aviso y falsas alarmas

«Lluvia sostenida» significa una lectura compatible con lluvia durante un intervalo que todavía debe calibrarse en el balcón. Una única gota o salpicadura breve no bastará por sí sola. Se observarán por separado lluvia que alcanza la ropa, lluvia que solo alcanza el sensor, goteo desde una superficie, salpicadura, condensación y secado del sensor. La duración, intensidad y condiciones de restablecimiento se fijarán a partir de esas observaciones, sin inventar umbrales antes de medir.

La señal local debe seguir siendo el resultado del piloto aunque no exista red. Si en una etapa posterior se envían mensajes, una lectura sin hora válida o fuera de su vigencia no deberá presentarse como lluvia actual.

## Plan de primera validación

Primero observar el lugar sin electrónica energizada. Anotar fecha, hora, ubicación, condición del clima, presencia real de ropa y qué zonas se mojaron. Una aplicación controlada de agua puede comprobar el comportamiento del sensor, pero se registrará como simulación y no como lluvia real.

| Escenario | Resultado esperado |
| --- | --- |
| Agua sostenida en una ubicación que representa la exposición de la ropa; modo activo | Una señal local reconocible; registrar tiempo hasta el aviso. |
| Misma condición; modo inactivo | Sin aviso para entrar ropa. |
| Salpicadura breve aislada | No convertirse automáticamente en aviso de lluvia sostenida. |
| Condensación o goteo desde arriba | Registrar si provocan aviso y si corresponden a un riesgo real para la ropa. |
| Agua en la ropa pero no en el punto de medición | Identificar un fallo de ubicación; no declarar que el punto elegido sirve. |
| Medición interrumpida o antigua | Mostrar estado desconocido, distinto de seco. |
| Reinicio con ropa afuera | Estado manual comprensible y verificable; registrar si exige confirmación. |
| Aviso activo mientras continúa la lluvia | No repetirlo continuamente; documentar cómo se silencia y restablece. |

En cada ensayo registrar configuración, resultado observado, tiempo de respuesta, fotos o video cuando sea útil y cualquier falso aviso u omisión. Los criterios numéricos de tiempo y tasa de falsas alarmas se acordarán después de la primera observación, antes de dar el piloto por aceptado.

## Criterios para pasar a diseño de hardware

- Existe una ubicación candidata respaldada por observaciones de exposición de sensor y ropa.
- El estado manual y la señal local son claros en la escena de uso.
- Se conocen al menos las fuentes principales de falsos avisos y omisiones del lugar.
- Hay una forma de distinguir lectura vigente, lectura antigua y fallo.
- Quedan definidos los criterios medibles de aceptación para el prototipo.

## Fuera de alcance por ahora

Pronóstico meteorológico, afirmar que la ropa está seca, detección automática de ropa, compra de componentes e integración con la pantalla central.