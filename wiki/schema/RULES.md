# rules.md — Reglas de ingestión, consulta y mantenimiento del Wiki

> **Ubicación canónica:** `wiki/schema/rules.md`
> **Estado:** vigente
> **Obligatoriedad:** de cumplimiento obligatorio para el tutor/agente.
> **Documentos relacionados:** `soul.md`, `contexto.md`, `roles.md`, `errores.md`, `fails.md`, `log.md`, `processed/archivos.md`, `MEMORY.md`, `README.md`, `AGENT.md`.

---

## 0. Principios generales

1. El Wiki es la **fuente primaria** del tutor. `raw/` es respaldo y origen; `processed/` es la capa curada.
2. Todo dato debe ser **trazable**: archivo, sección, página, versión.
3. **No se inventan** datos, referencias, mediciones ni rutas.
4. El **formato de análisis inicial** es Markdown con tablas (y bloques JSON cuando se requiera estructura). El PDF se deriva **después** de ese análisis; nunca al revés.
5. Toda regla aquí descrita es **obligatoria**; si una regla cambia, se actualiza la versión y la fecha al final de este archivo y se registra en `log.md`.
6. Ante ambigüedad, **detenerse y reportar** antes de inventar una solución.

---

## 1. Ingestión (`raw/` → `wiki/processed/`)

### 1.1 Flujo obligatorio

1. Identificar el PDF/origen en `raw/`.
2. Asignar **nombre canónico** según §1.3.
3. Analizar y convertir a `.md` en `wiki/processed/` con la plantilla estándar (§1.2). El análisis inicial se hace en Markdown con tablas; si el documento lo requiere, incluir bloques JSON para metadatos estructurados.
4. Revisar manualmente fórmulas, tablas, imágenes y OCR. **No inventar texto faltante.**
5. Registrar en `wiki/processed/archivos.md` (§3.5).
6. Registrar en `wiki/log.md` con: fecha, archivo origen, archivo destino, responsable, motivo.
7. Si el PDF original cambia, crear nueva versión del `.md` (§1.7) y anotar diferencias en `log.md`.

### 1.2 Plantilla estándar obligatoria

**Bloque de metadatos en tabla Markdown** (obligatorio al inicio de cada `.md`):

| Campo | Valor |
|---|---|
| `titulo` | <título del documento> |
| `fuente_raw` | `raw/<ruta exacta>.pdf` |
| `tipo` | libro \| manual \| hoja_datos \| apunte \| norma \| otro |
| `autor` | <autor o "desconocido"> |
| `anio` | <año o "s/d"> |
| `paginas_origen` | <rango> |
| `fecha_ingesta` | YYYY-MM-DD |
| `version_md` | v0.1 |
| `estado` | borrador \| revisado \| validado \| deprecado |
| `etiquetas` | [tema1, tema2, tema3] |
| `enlaces` | [./otro.md, ...] |
| `licencia` | <licencia o restricciones de uso> |

**Bloque JSON opcional para automatización** (inmediatamente después de la tabla, dentro de un cercado ```json):

```json
{
  "titulo": "",
  "fuente_raw": "",
  "tipo": "",
  "autor": "",
  "anio": "",
  "paginas_origen": "",
  "fecha_ingesta": "YYYY-MM-DD",
  "version_md": "v0.1",
  "estado": "borrador",
  "etiquetas": [],
  "enlaces": [],
  "licencia": ""
}
```

La tabla Markdown es la **fuente legible**; el bloque JSON es la **fuente parseable** por el script de validación. Ambos deben coincidir.

**Contenido mínimo obligatorio:**

1. **Resumen técnico** — 300–500 palabras. Si el documento es extenso, resumen **ejecutivo** con remisión a secciones internas.
2. **Tabla de conceptos clave** — término, definición, unidad o rango (si aplica), página de origen.
3. **Tabla de fallas y soluciones** — síntoma, causa probable, verificación, solución, página.
4. **Ejemplo práctico** — Arduino, ESP32, Raspberry Pi o síntesis propia. Debe indicar si fue **probado**, en qué placa, versión de IDE y librerías.
5. **Notas para LaTeX (APA/IEEE)** — cómo citar, paquetes recomendados, advertencias de compilación.
6. **Referencias cruzadas internas** — al menos **un** enlace a otro `.md` del Wiki (enlaces relativos dentro de `wiki/`).
7. **Advertencias de uso** — eléctricas, térmicas, de compilación, de versiones, de compatibilidad.
8. **Limitaciones del documento** — qué no cubre, qué queda pendiente.
9. **Estado declarado** — coherente con la tabla y el JSON.

Si falta algún apartado → `estado: borrador` + tarea registrada en `log.md`.

### 1.3 Nomenclatura canónica

- Formato: `tema_subtema_fuente.md` o `AAAA-MM-DD_tema_fuente.md`.
- **Sin espacios ni acentos.** Usar guion bajo.
- Un solo `.md` por tema; si ya existe, **actualizar**, no duplicar.

### 1.4 Documentos que no encajan en la plantilla

Si es un manual, libro o código extenso:

- No forzar la plantilla completa.
- Crear un `.md` **índice** con metadatos y resumen ejecutivo.
- Crear `.md` **hijos** por capítulo o tema dentro de `processed/`.
- Enlazar los hijos desde el índice padre con links internos relativos.

### 1.5 Chunking de PDF grandes

- Si el PDF tiene **más de 100 páginas**, se divide en secciones temáticas **cuando el Markdown proporcionado de ese PDF carezca de información vital** (fórmulas, tablas, diagramas, datos numéricos, pasos críticos).
- Si el Markdown derivado conserva toda la información vital, **no se fragmenta**; se mantiene un solo `.md`.
- Cada sección fragmentada genera un `.md` propio con metadatos heredados del padre (`fuente_raw`, `autor`, `anio`, `licencia`).
- El `.md` padre queda como índice navegable.

### 1.6 Duplicados y solapamiento

- Si dos fuentes cubren el mismo tema, se conservan **ambos** `.md`.
- Se crea un `.md` comparativo que indique coincidencias, contradicciones y cuál se prioriza, **con justificación**.
- No se elimina ningún original sin marcarlo `estado: deprecado` y enlazar al reemplazo.

### 1.7 Control de versiones del original

- Si el PDF/origen cambia, crear nueva versión del `.md` (`version_md: v0.2`).
- Anotar diferencias respecto a la versión anterior en `log.md`.
- No sobrescribir versiones anteriores; conservarlas para trazabilidad.

### 1.8 Prohibiciones

- No inventar datos ni referencias externas.
- No copiar texto sin procesar; siempre resumir o sintetizar.
- No omitir advertencias de hardware/software en los ejemplos.
- No ingerir material con licencia restrictiva sin autorización explícita de Cristian.

---

## 2. Consulta

### 2.1 Orden de búsqueda (prioridad explícita)

1. `wiki/processed/` — Markdown procesados y validados.
2. `wiki/raw/` — PDF originales.
3. `wiki/schema/` — `roles.md`, `errores.md`, `rules.md`, `fails.md`.
4. Archivos `.md` sueltos de `wiki/` — `AGENT.md`, `MEMORY.md`, `README.md`, `contexto.md`, `log.md`, `processed/archivos.md`, `soul.md`.
5. Fuentes externas (web) — **solo con autorización de Cristian**; registrar URL, fecha de consulta y motivo.

### 2.2 Búsqueda por concepto, no por nombre

- Buscar por **pertinencia temática** usando etiquetas, índice y contenido.
- Si la primera búsqueda falla, intentar **sinónimos y términos relacionados** antes de declarar ausencia.

### 2.3 Manejo de contradicciones

Si dos `.md` se contradicen:

1. Reportar **ambas versiones**.
2. Indicar archivo, sección, página y versión de cada una.
3. Aplicar jerarquía de prioridad:
   1. Norma técnica vigente.
   2. Hoja de datos del fabricante.
   3. Manual oficial del software.
   4. Material de clase.
   5. Apuntes o resúmenes.
4. Ante empate, priorizar: `fecha_ingesta` más reciente → `estado: validado` > `revisado` > `borrador` → fuente más especializada.
5. **No resolver arbitrariamente**: señalar la contradicción a Cristian y explicar la diferencia.

### 2.4 Formato de cita obligatorio

```
Fuente: <archivo>.md
Sección: <nombre>
Página origen: <n>
Versión: <v0.x>
Estado: borrador | revisado | validado | deprecado
```

### 2.5 Frescura

- Si hay versiones múltiples del mismo tema, usar la de mayor `version_md` y `estado: validado` (o `revisado`).
- Si la versión más reciente es `borrador`, **advertirlo** antes de usarla.

### 2.6 Enlaces internos

- Todo `.md` debe enlazar al menos a otro `.md` del Wiki.
- Enlaces **relativos** dentro de `wiki/`.
- Enlaces **bidireccionales** cuando aplique: cada concepto enlaza a su fuente y a conceptos relacionados.
- Un concepto sin referencia cruzada se considera **incompleto**.

### 2.7 Límite de contexto

- Si el documento es muy largo, **resumir y enlazar a la sección exacta**.
- No volcar bloques extensos en la respuesta si no son necesarios.

### 2.8 Trazabilidad

- Toda respuesta debe indicar de qué `.md` o PDF proviene el dato (ver §2.4).
- Si una respuesta combina varias fuentes, citarlas todas.

### 2.9 Fallback a web

- Solo si está autorizado por Cristian.
- Registrar: URL, fecha de consulta y motivo.
- Nunca usar la web para reemplazar contenido que ya existe en `processed/`.

---

## 3. Mantenimiento

### 3.1 Frecuencia

| Actividad | Frecuencia |
|---|---|
| Revisión de formato | Mensual |
| Revisión de enlaces rotos | Mensual |
| Revisión de huérfanos | Mensual |
| Revisión de contradicciones | En cada ingesta nueva |
| Revisión de `estado` por archivo | Trimestral |
| Revisión de temas activos | Mensual |
| Revisión de temas inactivos | Trimestral |

### 3.2 Validación mínima por archivo

Cada `.md` debe tener:

- Tabla de metadatos completa y válida.
- Bloque JSON coherente con la tabla (si existe).
- Título.
- Resumen.
- Tabla de fallas o conceptos.
- Ejemplo.
- Notas LaTeX.
- Advertencias de uso.
- Al menos una referencia cruzada.
- Estado declarado.

Si falta algo → `estado: borrador` + tarea en `log.md`.

### 3.3 Validación automática (implementar ya)

- Implementar **script de validación** en cuanto se cree este archivo.
- El script debe verificar:
  - Existencia y coherencia de la tabla de metadatos.
  - Coherencia entre tabla Markdown y bloque JSON.
  - Presencia de secciones obligatorias.
  - Enlaces internos rotos.
  - Archivos huérfanos.
  - Cumplimiento de nomenclatura (§1.3).
- Salida del script: reporte en `log.md` con fecha, hallazgos y archivos afectados.
- El script se ejecuta **mensualmente** como mínimo, y **en cada ingesta** si es posible.

### 3.4 Enlaces rotos y huérfanos

- **Enlaces rotos:** corregir ruta o eliminar enlace; anotar en `log.md`.
- **Huérfanos** (`.md` sin enlaces entrantes): enlazarlos desde `processed/archivos.md` o desde un `.md` temático.

### 3.5 Índice general

`wiki/processed/archivos.md` debe listar **todos** los `.md` de `processed/` con:

- Nombre.
- Tema.
- Estado.
- Versión.
- Fecha de ingesta.
- Enlace interno.

### 3.6 Changelog

`wiki/log.md` registra:

- Fecha.
- Acción (ingesta / edición / deprecación / corrección / validación).
- Archivo afectado.
- Motivo.
- Responsable (Cristian o tutor).

### 3.7 Deprecación

- Un `.md` se marca `estado: deprecado` cuando queda obsoleto por una fuente mejor.
- **No se elimina**; se conserva para trazabilidad.
- Añadir al inicio del archivo una nota indicando **qué lo reemplaza** (enlace relativo).

### 3.8 Métricas

- Número de archivos validados.
- Número de enlaces rotos.
- Número de huérfanos.
- Días desde la última revisión.

### 3.9 Responsable y validación

- Responsable primario: **Cristian David Villegas Díaz**.
- El estado `validado` **solo lo otorga Cristian**. El tutor/agente puede proponer `revisado`, pero no `validado`.
- Co-responsable operativo: el tutor/agente, según `roles.md`.

### 3.10 Integración con otros esquemas

Los siguientes archivos deben mantenerse **consistentes entre sí**:

- `schema/roles.md` — roles del tutor.
- `schema/errores.md` — errores de conversación.
- `schema/fails.md` — fallas técnicas reutilizables.
- `schema/rules.md` — este archivo.
- `wiki/log.md`, `wiki/processed/archivos.md`, `wiki/MEMORY.md`, `wiki/contexto.md`.

Cualquier cambio en uno que afecte a otro debe propagarse y registrarse en `log.md`.

### 3.11 Versionado de `rules.md`

- Cada modificación **relevante** sube versión menor.
- Cambios **estructurales** suben versión mayor.
- Los cambios se registran en `log.md`.

---

## 4. Integración con `contexto.md` y `README.md`

- `contexto.md` debe incluir una sección explícita:

  > "Las reglas de ingestión, consulta y mantenimiento están en `schema/rules.md` y son de **obligado cumplimiento**."

- `README.md` debe enlazar a `schema/rules.md`.

---

## 5. Checklist antes de publicar un `.md`

- [ ] ¿Tiene tabla de metadatos completa?
- [ ] ¿Tiene bloque JSON coherente con la tabla (si aplica)?
- [ ] ¿Tiene título?
- [ ] ¿Tiene resumen (300–500 palabras)?
- [ ] ¿Tiene tabla de fallas o conceptos?
- [ ] ¿Tiene ejemplo (probado o marcado como no probado)?
- [ ] ¿Tiene notas LaTeX?
- [ ] ¿Tiene advertencias de uso?
- [ ] ¿Está enlazado a otros `.md`?
- [ ] ¿Está declarado el `estado`?
- [ ] ¿Está registrado en `processed/archivos.md` y `log.md`?

---

## 6. Checklist de implementación del esquema

- [x] Definir formato de análisis inicial: Markdown + tablas + JSON opcional.
- [x] Definir índice general en `wiki/processed/archivos.md`.
- [x] Definir chunking solo si el Markdown pierde información vital.
- [x] Definir que `estado: validado` lo otorga Cristian.
- [ ] Crear `schema/rules.md` con esta versión.
- [ ] Añadir tabla de metadatos a todos los `.md` existentes.
- [ ] Implementar **ya** el script de validación automática.
- [ ] Revisar enlaces internos y referencias cruzadas.
- [ ] Actualizar `contexto.md` apuntando a estas reglas.
- [ ] Resolver contradicciones pendientes detectadas.

---

## 7. Versionado

- `v0.1` — creación inicial.
- `v0.2` — frontmatter YAML, jerarquía de contradicciones, integración con `fails.md`, chunking de PDF grandes, validación automática, checklist.
- `v0.3` — corrección y unificación con diagnóstico previo; licencias, control de versiones del original, métricas y checklist de implementación.
- `v1.0` — versión final consensuada con Cristian: metadatos en tabla Markdown + JSON opcional; índice en `processed/archivos.md`; chunking condicionado a pérdida de información vital; `validado` solo por Cristian; script de validación automática a implementar ya.

---

**Versión:** v1.0 — 2025-01-01
**Autor:** Cristian David Villegas Díaz
**Próxima revisión:** mensual
