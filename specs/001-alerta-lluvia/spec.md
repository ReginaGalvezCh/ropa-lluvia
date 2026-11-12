# Especificación 001: alerta de lluvia con ropa tendida

**Estado:** propuesta para validar.

## Propósito

Dar tiempo para retirar la ropa cuando aparece lluvia relevante, sin avisar cuando no hay ropa.

## Comportamiento esperado

1. La persona marca si hay ropa tendida.
2. Con ropa marcada y lluvia sostenida, el dispositivo emite un aviso local.
3. Sin ropa marcada, la lluvia no genera un aviso de ropa.
4. Si el sensor falla o sus datos son antiguos, el sistema señala estado desconocido en vez de afirmar que no llueve.
5. Se evita repetir continuamente el mismo aviso; la regla de restablecimiento se definirá en la prueba.

## Criterios de aceptación del piloto

- El aviso aparece cuando se simula lluvia sostenida con «hay ropa» activo.
- El aviso no aparece con «hay ropa» inactivo.
- Una salpicadura breve no equivale automáticamente a lluvia sostenida.
- La pérdida del sensor se distingue del estado seco.

## Fuera de alcance por ahora

Pronóstico meteorológico, detección automática de ropa y pantalla central.

## Preguntas abiertas

¿Dónde se instalará? ¿Qué duración o intensidad cuenta como lluvia relevante? ¿Cómo se confirma o silencia un aviso? ¿Qué fallos pueden causar condensación, viento y salpicaduras?

