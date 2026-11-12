# Aviso de lluvia para ropa tendida

Proyecto independiente para avisar cuando hay ropa expuesta y se detecta lluvia relevante. El primer piloto utiliza una indicación manual de «hay ropa» y una alerta local.

## Estado

Definición inicial. Sin sensor de lluvia, ubicación ni prototipo validados.

## Primer alcance

- Activar o desactivar manualmente el estado «hay ropa tendida».
- Detectar lluvia sostenida con una regla que se pruebe en el lugar real.
- Avisar localmente solo cuando ambos estados coincidan.
- Mostrar estado desconocido si falla la medición o está desactualizada.
- Considerar luego el aviso en la pantalla central.

## Documentos

- [Especificación del piloto](specs/001-alerta-lluvia/spec.md).
- [Método y arquitectura compartida](docs/metodologia.md).

## Próximas decisiones

Ubicación del sensor, protección, alimentación, forma de activación, regla para lluvia sostenida, alerta local y manejo de salpicaduras o condensación.

