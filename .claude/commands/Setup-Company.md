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

## Cuándo usar esta skill

- El usuario quiere crear un archivo de contexto para su empresa
- Necesita una plantilla para estandarizar la redacción de requerimientos
- Quiere documentar el contexto de negocio que alimenta las decisiones de producto
- Pide un PRD template, brief de producto o ficha empresarial orientada a producto

---

## Flujo de trabajo

### Paso 1 — Recopilar información

Haz las preguntas en bloques, no una por una. Espera respuesta antes de continuar al siguiente bloque.

**Bloque 1 — Identidad:**
- ¿Cuál es el nombre de la empresa y su sitio web?
- ¿En qué sector o industria opera?
- ¿Cuál es su propuesta de valor principal?

**Bloque 2 — Mercados y modelo:**
- ¿En qué países o mercados opera? ¿Cuál es el principal?
- ¿Hay mercados en expansión?
- ¿Cuál es el modelo de negocio? (e-commerce, SaaS, marketplace, etc.)
- ¿Cuáles son las palancas clave de retención o monetización?

**Bloque 3 — Usuarios:**
- ¿Quiénes son los usuarios principales? (perfil, edad, necesidad clave)
- ¿Hay usuarios internos que interactúan con el producto? (domiciliarios, operadores, etc.)

**Bloque 4 — Stack y equipos:**
- ¿Qué herramientas usan para infra, datos, CRM y documentación?
- ¿Cuáles son los equipos o áreas que participan en producto?

**Bloque 5 — Roadmap:**
- ¿Cuánto duran los sprints?
- ¿Qué campos y estados tiene el roadmap?

**Bloque 6 — Parámetros financieros:**
- ¿Qué tasa de descuento o WACC usan para evaluar proyectos?
- ¿Cuál es el horizonte de proyección estándar?

**Bloque 7 — Tiers y documentos:**
- ¿Usan tiers de proyecto? ¿Cómo los definen?
- ¿Qué documentos requiere cada tier?
- ¿Dónde se guardan los distintos tipos de documentos?

**Bloque 8 — Marca y competencia:**
- ¿Cuál es el tono de comunicación del equipo de producto?
- ¿Cuáles son los competidores principales?
- ¿Cuáles son las métricas clave del negocio?

---

### Paso 2 — Mostrar resumen y confirmar

Antes de generar, muestra al usuario un resumen estructurado de toda la información recopilada y pide confirmación explícita.

Si el usuario quiere modificar algo, incorpora los cambios y muestra el resumen actualizado antes de continuar.

---

### Paso 3 — Generar los archivos

Con la confirmación del usuario, genera:

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
