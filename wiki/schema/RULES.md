# 📐 Reglas de ingestión, consulta y mantenimiento del Wiki

## Ingestión (raw → wiki)
1. Todo documento en `raw/` debe convertirse en un archivo `.md` en `wiki/`.
2. El `.md` debe seguir la plantilla estándar:
   - Resumen técnico (300–500 palabras).
   - Tabla de fallas y soluciones.
   - Ejemplo práctico (Arduino, ESP32, Raspberry o síntesis propia).
   - Notas para documentación en LaTeX (APA/IEEE).
3. No se inventan datos ni referencias externas.
4. Cada archivo `.md` debe incluir advertencias de uso en ejemplos de hardware/software.

## Consulta
- Los `.md` en `wiki/` deben enlazarse entre sí con links internos.
- El agente debe usar primero el contenido del wiki antes de buscar en la web.
- Cada concepto debe tener al menos una referencia cruzada.

## Mantenimiento
- Revisar consistencia de formato en todos los `.md`.
- Actualizar este `schema/` si cambia la plantilla.
- Validar que cada archivo tenga título, tabla, ejemplo y notas LaTeX.
