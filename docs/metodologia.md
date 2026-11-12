# Base de los proyectos maker

Este paquete prepara cuatro repositorios independientes: plantas, ropa tendida, recordatorio de salida y luz de disponibilidad. Cada carpeta puede publicarse como un repositorio privado distinto. Son propuestas iniciales para revisar; no describen dispositivos construidos ni integraciones ya verificadas.

## Método de trabajo

Usaremos especificaciones vivas: primero el comportamiento esperado y sus criterios de aceptación; después las decisiones de diseño, arquitectura y tecnología; finalmente tareas pequeñas, prototipo y evidencia. Cada cambio de comportamiento actualiza la especificación en el mismo repositorio que el trabajo correspondiente.

El README de cada repositorio orienta al lector. `specs/` guarda el comportamiento verificable. Las decisiones técnicas futuras irán en `docs/decisions/`. No se crearán carpetas de código, CAD o electrónica vacías.

Spec Kit es una ayuda opcional para ordenar este flujo. Su inicialización formal en cada repositorio se hará cuando exista un checkout local y se confirme la estructura generada por la versión instalada. Estos archivos no implican que Spec Kit ya esté instalado.

## Arquitectura transversal propuesta

Cada objeto físico debe funcionar por sí solo para su caso principal. Cuando convenga mostrar avisos en la pantalla central, el proyecto enviará eventos mediante un contrato común por definir. La pantalla decidirá cómo presentar prioridad, antigüedad y estado desconocido; no asumirá la lógica del sensor. Wi-Fi local es un candidato para avisos automáticos. NFC puede servir para interacciones deliberadas de proximidad. El transporte, el formato de eventos y la seguridad se decidirán con un primer prototipo de integración.

## Pendientes comunes

1. Validar con una prueba física el comportamiento principal de cada proyecto.
2. Elegir sensores, alimentación, carcasa y ubicación según esa prueba.
3. Definir contrato de avisos solo para los proyectos que realmente lo necesiten.
4. Registrar decisiones y resultados de las pruebas en cada repositorio.

