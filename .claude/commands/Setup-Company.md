---
name: product-requirements-context
description: "Genera un archivo de contexto empresarial completo para la creación de requerimientos de producto. Usa esta skill siempre que el usuario quiera crear un 'archivo de contexto', 'contexto de empresa', 'plantilla de requerimientos', 'PRD template', 'product requirements document', o cualquier documento base que establezca el contexto de una empresa para definir requerimientos de producto. También aplica cuando el usuario mencione 'brief de producto', 'ficha de empresa para producto', 'contexto para historias de usuario', o pida una plantilla reutilizable para documentar requerimientos alineados con la estrategia de una empresa. Funciona para cualquier empresa, industria o mercado."
---

Tu tarea es recopilar el contexto de una empresa y escribirlo en `.claude/context/company_context.md`.

Lee la plantilla de referencia antes de generar:
@.claude/references/template.md

---

## Flujo de trabajo

### Paso 1 — Obtener el nombre de la empresa

Pregunta únicamente: **¿Cuál es el nombre de la empresa y su sitio web (si lo tienes)?**

---

### Paso 2 — Búsqueda en línea

Con el nombre de la empresa, realiza búsquedas web para pre-llenar el contexto automáticamente. Busca en este orden:

1. Sitio web oficial de la empresa
2. LinkedIn de la empresa
3. Crunchbase o similares (modelo de negocio, mercados, tamaño)
4. Noticias recientes (expansión, nuevos productos, resultados)

**Campos a buscar:**
- Sector / industria y tamaño aproximado
- Países o mercados donde opera y modelo de entrada
- Modelo de negocio, canales y palancas de retención
- Usuarios principales (perfil, segmentos)
- Stack tecnológico público (apps propias, herramientas mencionadas)
- Competidores principales
- Métricas o logros públicos relevantes

**Regla:** Solo usa información que puedas confirmar con fuentes. Marca como `[COMPLETAR]` todo lo que no encuentres con certeza — nunca inventes datos.

---

### Paso 3 — Presentar hallazgos y completar gaps

Muestra al usuario lo que encontraste en formato de tabla con fuente:

> "Encontré esta información sobre [Empresa]. Revisa y dime qué corregir o agregar:"
>
> | Campo | Valor encontrado | Fuente |
> |-------|-----------------|--------|
> | Sector | [valor] | [fuente] |
> | Mercados | [valor] | [fuente] |
> | Stack tecnológico | [COMPLETAR] | No encontrado |

Luego pregunta **solo los campos que no encontraste**, agrupados en un solo bloque:

- Stack tecnológico interno (infra, datos, CRM, documentación, apps propias)
- Equipos o áreas que participan en producto
- Duración de sprints y estructura del roadmap (campos, áreas, estados)
- Parámetros financieros (WACC, horizonte de proyección, moneda)
- Tiers de proyecto y documentos requeridos por tier
- Dónde se guardan los distintos tipos de documentos
- Tono de comunicación del equipo de producto

---

### Paso 4 — Confirmar antes de generar

Muestra el contexto completo consolidado (información web + respuestas del usuario) y pide confirmación explícita antes de escribir el archivo.

Si el usuario quiere modificar algo, actualiza y muestra de nuevo.

---

### Paso 5 — Generar el archivo

Con confirmación del usuario, escribe `.claude/context/company_context.md` siguiendo exactamente la estructura de `references/template.md`, completando todas las secciones con la información recopilada.

Deja `[COMPLETAR]` en cualquier campo sin información confirmada.

Confirma al usuario que el archivo fue escrito y que todos los skills en `.claude/commands/` ya lo leen automáticamente.

---

## Reglas

- **No inventar datos** — si no hay información confirmada, usa `[COMPLETAR]`
- **No escribir el archivo** hasta tener confirmación explícita
- **Citar fuentes** en la tabla de hallazgos
- **Idioma:** el mismo que usa el usuario
- **Un solo archivo de salida:** `.claude/context/company_context.md`
