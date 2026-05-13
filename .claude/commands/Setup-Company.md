Tu tarea es recopilar el contexto de una empresa y escribirlo en el archivo `.claude/context/company_context.md` siguiendo exactamente la plantilla existente.

## Flujo de ejecución

Haz las preguntas en bloques, no una por una. Agrupa las preguntas por sección y espera la respuesta antes de continuar con el siguiente bloque.

### Bloque 1 — Identidad
Pregunta:
- ¿Cuál es el nombre de la empresa y su sitio web?
- ¿A qué se dedica y cuál es su propuesta de valor principal?

### Bloque 2 — Mercados y modelo de negocio
Pregunta:
- ¿En qué mercados o países opera? ¿Cuál es el principal?
- ¿Hay mercados en expansión o planeados?
- ¿Cuál es el modelo de negocio? (e-commerce, SaaS, marketplace, etc.)
- ¿Cuáles son las palancas clave de retención o monetización?

### Bloque 3 — Stack y equipos
Pregunta:
- ¿Qué herramientas usan para infra, datos, CRM y documentación?
- ¿Cuáles son los equipos o áreas que participan en producto?

### Bloque 4 — Roadmap
Pregunta:
- ¿Cuánto duran los sprints?
- ¿Qué campos tiene el roadmap? (áreas, prioridades, estados)
- ¿Cuál es el flujo de estados de una tarea en el roadmap?

### Bloque 5 — Parámetros financieros
Pregunta:
- ¿Qué tasa de descuento o WACC usan para evaluar proyectos?
- ¿Cuál es el horizonte de proyección estándar?
- ¿Hay alguna instrucción especial para el modelado financiero?

### Bloque 6 — Tiers y documentos
Pregunta:
- ¿Usan tiers de proyecto (Small, Medium, Large o similar)? ¿Cómo los definen?
- ¿Qué documentos requiere cada tier?
- ¿Dónde se guardan los distintos tipos de documentos?

### Bloque 7 — Estilo
Pregunta:
- ¿En qué idioma opera el equipo de producto?
- ¿Cómo describirías el tono esperado en los documentos?

## Al terminar los bloques

1. Muestra al usuario un resumen estructurado de toda la información recopilada y pide confirmación antes de escribir el archivo.
2. Con la aprobación del usuario, escribe el archivo `.claude/context/company_context.md` completando la plantilla con la información recopilada. Mantén exactamente la estructura de la plantilla — no agregues ni elimines secciones.
3. Confirma al usuario que el archivo fue escrito y que todos los skills del directorio `.claude/commands/` ya pueden usarlo automáticamente.

## Reglas
- No inventes información — si el usuario no sabe algo, deja el placeholder original `[...]` en esa sección.
- No escribas el archivo hasta tener la confirmación explícita del usuario.
- Si el usuario quiere modificar algo del resumen antes de confirmar, incorpora los cambios y muestra el resumen actualizado.
