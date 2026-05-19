---
name: product-requirements-context
description: "Genera un archivo de contexto empresarial completo para la creación de requerimientos de producto. Usa esta skill siempre que el usuario quiera crear un 'archivo de contexto', 'contexto de empresa', 'plantilla de requerimientos', 'PRD template', 'product requirements document', o cualquier documento base que establezca el contexto de una empresa para definir requerimientos de producto. También aplica cuando el usuario mencione 'brief de producto', 'ficha de empresa para producto', 'contexto para historias de usuario', o pida una plantilla reutilizable para documentar requerimientos alineados con la estrategia de una empresa. Funciona para cualquier empresa, industria o mercado."
---

Tu tarea es construir el contexto de una empresa sección por sección, confirmando con el usuario antes de avanzar a la siguiente.

Lee la plantilla de referencia antes de iniciar:
@.claude/references/template.md

---

## Flujo de trabajo

### Paso 1 — Obtener el nombre de la empresa

Pregunta únicamente: **¿Cuál es el nombre de la empresa y su sitio web (si lo tienes)?**

---

### Paso 2 — Búsqueda en línea

Con el nombre, busca en web (sitio oficial, LinkedIn, Crunchbase, noticias recientes) para pre-llenar el mayor número de campos posible. Solo usa información confirmada — marca como `[COMPLETAR]` lo que no encuentres con certeza.

---

### Paso 3 — Construir sección por sección

Presenta cada sección de la plantilla **una a la vez**, siguiendo este protocolo por sección:

1. **Muestra la sección pre-llenada** con lo que encontraste en web + `[COMPLETAR]` donde no hay datos
2. **Pregunta** al usuario si hay algo que corregir, agregar o dejar como está
3. **Espera confirmación** — el usuario dice "ok", "listo", "siguiente" o hace correcciones
4. **Si hay correcciones**, actualiza la sección y muéstrala de nuevo antes de avanzar
5. **Solo cuando el usuario confirme**, avanza a la siguiente sección

**Orden de secciones:**
1. Identidad
2. Mercados
3. Modelo de negocio
4. Usuarios
5. Stack tecnológico
6. Equipos
7. Roadmap y ciclos de trabajo
8. Competencia
9. Métricas clave del negocio
10. Tiers de proyecto
11. Dónde guardar los documentos
12. Estilo de comunicación

Al presentar cada sección, usa este formato:

> **Sección X de 12 — [Nombre]**
> [contenido pre-llenado en formato tabla o lista]
> ¿Corriges algo o avanzamos?

---

### Paso 4 — Generar el archivo

Una vez confirmadas las 12 secciones, escribe `.claude/context/company_context.md` con todo el contenido consolidado siguiendo exactamente la estructura de `references/template.md`.

Confirma al usuario que el archivo fue escrito y que todos los skills en `.claude/commands/` ya lo leen automáticamente.

---

## Reglas

- **Una sección a la vez** — nunca presentes dos secciones juntas
- **No inventar datos** — si no hay información confirmada, usa `[COMPLETAR]`
- **No escribir el archivo** hasta que las 12 secciones estén confirmadas
- **Si el usuario no sabe un campo**, déjalo como `[COMPLETAR]` y avanza
- **Citar fuente** cuando el dato venga de búsqueda web
- **Idioma:** el mismo que usa el usuario
