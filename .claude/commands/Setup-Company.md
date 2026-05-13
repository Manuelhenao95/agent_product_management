---
name: product-requirements-context
description: "Genera un archivo de contexto empresarial completo para la creación de requerimientos de producto. Usa esta skill siempre que el usuario quiera crear un 'archivo de contexto', 'contexto de empresa', 'plantilla de requerimientos', 'PRD template', 'product requirements document', o cualquier documento base que establezca el contexto de una empresa para definir requerimientos de producto. También aplica cuando el usuario mencione 'brief de producto', 'ficha de empresa para producto', 'contexto para historias de usuario', o pida una plantilla reutilizable para documentar requerimientos alineados con la estrategia de una empresa. Funciona para cualquier empresa, industria o mercado."
---

Tu tarea es recopilar el contexto de una empresa y generar dos archivos:
1. `.claude/context/company_context.md` — contexto resumido que usan los skills del flujo de trabajo
2. `contexto_requerimientos_[nombre_empresa].md` — documento completo de contexto + plantilla de requerimientos

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
3. Crunchbase o similares (para modelo de negocio, mercados, funding)
4. Noticias recientes (para expansión, mercados, productos nuevos)

**Campos a buscar:**
- Sector / industria
- Países o mercados donde opera
- Modelo de negocio y propuesta de valor
- Canales (app, web, tiendas físicas)
- Usuarios principales (a quién le vende)
- Competidores principales
- Métricas o logros públicos relevantes

**Regla:** Solo usa información que puedas confirmar con fuentes. Marca como `[COMPLETAR]` todo lo que no encuentres con certeza — nunca inventes datos.

---

### Paso 3 — Presentar hallazgos y completar gaps

Muestra al usuario lo que encontraste en formato de tabla organizada por sección. Ejemplo:

> "Encontré esta información sobre [Empresa]. Revisa y dime qué corregir o agregar:"
>
> | Campo | Valor encontrado | Fuente |
> |-------|-----------------|--------|
> | Sector | Pet Commerce | laika.com.co |
> | Mercados | Colombia, Chile | LinkedIn |
> | ... | ... | ... |
> | Stack tecnológico | [COMPLETAR] | No encontrado |

Luego haz preguntas **solo para los campos que no pudiste encontrar** en línea, agrupadas en bloques:

**Campos internos (no disponibles públicamente):**
- Stack tecnológico (infra, datos, CRM, documentación)
- Equipos o áreas que participan en producto
- Duración de sprints y estructura del roadmap
- Parámetros financieros (WACC, horizonte de proyección)
- Tiers de proyecto y documentos requeridos por tier
- Dónde se guardan los documentos
- Tono de comunicación del equipo de producto

---

### Paso 4 — Confirmar antes de generar

Muestra un resumen final consolidado (información web + respuestas del usuario) y pide confirmación explícita antes de escribir cualquier archivo.

Si el usuario quiere modificar algo, actualiza el resumen y muéstralo de nuevo.

---

### Paso 5 — Generar los archivos

Con confirmación del usuario, genera:

**Archivo 1:** `.claude/context/company_context.md`
Contexto resumido siguiendo la estructura actual del archivo. Lo usan todos los skills del flujo automáticamente.

**Archivo 2:** `contexto_requerimientos_[nombre_empresa_en_minusculas].md`
Documento completo basado en `references/template.md` con:
- Bloque A completo con toda la información de la empresa
- Bloque B con la plantilla de requerimientos personalizada al sector (ejemplos de user stories, KPIs y riesgos adaptados a la industria)
- IDs con el formato `REQ-[SIGLAS_EMPRESA]-[MÓDULO]-[###]`
- Campos sin información marcados como `[COMPLETAR]`

---

## Reglas de generación

- **Idioma:** genera en el mismo idioma que usa el usuario
- **Ejemplos:** adapta user stories, KPIs y riesgos al sector específico de la empresa
- **No inventar datos:** si no hay información confirmada, usa `[COMPLETAR]`
- **Tono:** profesional pero accesible, listo para usar por cualquier miembro del equipo
- **Longitud del archivo 2:** entre 150 y 300 líneas
- **No escribir los archivos** hasta tener confirmación explícita del usuario
- **Citar fuentes** en la tabla de hallazgos para que el usuario pueda verificar
