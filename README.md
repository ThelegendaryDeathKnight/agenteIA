
---

## 🧩 Archivos clave

- **SOUL.md** → Define quién es el agente, su tono y límites.  
- **AGENT.md** → Contiene reglas específicas para cada proyecto.  
- **MEMORY.md** → Guarda hechos y preferencias para continuidad entre sesiones.  
- **raw/** → Carpeta de fuentes originales (no se modifican).  
- **wiki/** → Carpeta de conocimiento procesado en `.md`.  
- **schema/** → Define cómo se actualiza y organiza el wiki personal.  

---

## 🚀 Cómo usar este repositorio

1. **Guardar documentos en `raw/`**  
   - PDFs, manuales, tutoriales, papers.  

2. **Procesar documentos con el agente**  
   - Usar prompts optimizados para generar `.md` en `wiki/`.  
   - Cada `.md` debe incluir: resumen técnico, tabla de fallas/soluciones, ejemplo práctico y notas LaTeX.  

3. **Actualizar `schema/`**  
   - Definir reglas de ingestión (cómo se convierten los documentos de `raw/` en `wiki/`).  
   - Definir reglas de consulta (cómo se enlazan conceptos entre sí).  

4. **Mantener identidad y memoria**  
   - Ajustar `soul.md`, `agent.md` y `memory.md` según el avance del proyecto.  

---

## 📖 Referencia

Este proyecto se inspira en la propuesta de Andrej Karpathy sobre arquitecturas de agentes con identidad, reglas, memoria y wiki personal.  
El repositorio está diseñado para apoyar el trabajo académico y técnico en electrónica, programación y automatización.

---

## ⚠️ Restricciones éticas

- No inventar datos ni referencias.  
- Transparencia en el uso de fuentes.  
- Seguridad en ejemplos de hardware y software.  
- Responsabilidad académica: el agente apoya, pero no reemplaza el criterio del estudiante.
