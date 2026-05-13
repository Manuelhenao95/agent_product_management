# Contexto de Requerimientos — [NOMBRE EMPRESA]

---

## BLOQUE A — CONTEXTO EMPRESARIAL

### 1. Identidad de la empresa

| Campo | Valor |
|-------|-------|
| Nombre | [NOMBRE EMPRESA] |
| Sitio web | [URL] |
| Sector / Industria | [COMPLETAR] |
| Mercado principal | [COMPLETAR] |
| Otros mercados | [COMPLETAR] |
| Modelo de negocio | [COMPLETAR] |
| Propuesta de valor | [COMPLETAR] |

### 2. Usuarios principales

| Segmento | Descripción | Necesidad clave |
|----------|-------------|-----------------|
| [Segmento 1] | [Perfil demográfico y comportamental] | [Qué necesita resolver] |
| [Segmento 2] | [COMPLETAR] | [COMPLETAR] |

**Usuarios internos que interactúan con el producto:**
- [Rol interno 1] — [qué hace en el sistema]
- [Rol interno 2] — [COMPLETAR]

### 3. Canales y plataformas

| Canal | Estado | Notas |
|-------|--------|-------|
| Web | [Activo / En desarrollo / N/A] | [COMPLETAR] |
| App móvil (iOS) | [Activo / En desarrollo / N/A] | [COMPLETAR] |
| App móvil (Android) | [Activo / En desarrollo / N/A] | [COMPLETAR] |
| Tiendas físicas | [Activo / En desarrollo / N/A] | [COMPLETAR] |
| Otros | [COMPLETAR] | [COMPLETAR] |

### 4. Stack tecnológico

| Capa | Herramienta |
|------|------------|
| Infraestructura | [COMPLETAR] |
| Datos / Analytics | [COMPLETAR] |
| CRM / Marketing | [COMPLETAR] |
| Documentación | [COMPLETAR] |
| Otros relevantes | [COMPLETAR] |

### 5. Equipos y áreas

[Lista de equipos o áreas que participan en producto]

- [Equipo 1]
- [Equipo 2]
- [COMPLETAR]

### 6. Tono de marca y comunicación

| Atributo | Descripción |
|----------|-------------|
| Tono general | [COMPLETAR — ej: cercano, técnico, formal] |
| Idioma principal | [COMPLETAR] |
| Estilo de documentación | [COMPLETAR — ej: directo, sin relleno, tablas para comparaciones] |

**Competidores principales:**
- [Competidor 1] — [fortaleza principal]
- [Competidor 2] — [COMPLETAR]

**Métricas clave del negocio:**
- [Métrica 1] — [COMPLETAR]
- [Métrica 2] — [COMPLETAR]

---

## BLOQUE B — PLANTILLA DE REQUERIMIENTOS

> Esta sección es la estructura repetible para cada nuevo requerimiento.
> Convención de IDs: `REQ-[SIGLAS_EMPRESA]-[MÓDULO]-[###]`
> Ejemplo: `REQ-LKA-ENTREGA-001`

---

### 7. Encabezado del requerimiento

| Campo | Valor |
|-------|-------|
| ID | `REQ-[SIGLAS]-[MÓDULO]-[###]` |
| Nombre | [Nombre corto del requerimiento] |
| Módulo / Área | [COMPLETAR] |
| Tier | [S / M / L] |
| Prioridad | [1 – 5] |
| Estado | [Backlog / En definición / En curso / Finalizado] |
| PM responsable | [COMPLETAR] |
| Fecha | [COMPLETAR] |
| Referencia | [Link al Opportunity Brief si existe] |

---

### 8. Cuerpo del requerimiento

#### Problema
[Descripción clara del problema que resuelve este requerimiento. Quién se ve afectado, con qué frecuencia, con qué evidencia.]

#### User stories

```
Como [tipo de usuario],
quiero [acción o funcionalidad],
para [beneficio o resultado esperado].
```

| ID Story | User Story | Criterios de aceptación |
|----------|------------|------------------------|
| [REQ-XXX-001-US1] | Como [usuario]... | - [ ] [Criterio 1] |
| | | - [ ] [Criterio 2] |
| [REQ-XXX-001-US2] | Como [usuario]... | - [ ] [Criterio 1] |

#### Reglas de negocio

1. [Regla 1 — condición o restricción del sistema]
2. [Regla 2]
3. [COMPLETAR]

#### Riesgos y supuestos

| Tipo | Descripción |
|------|-------------|
| Supuesto | [Qué debe ser verdad para que funcione] |
| Riesgo | [Qué podría fallar o impactar negativamente] |
| Dependencia | [Equipo, sistema o dato requerido] |

#### Checklist de pre-entrega

- [ ] Criterios de aceptación verificados en staging
- [ ] Eventos de tracking implementados
- [ ] SAC informado si hay impacto en atención al cliente
- [ ] Ops informado si hay impacto operativo
- [ ] Rollback plan documentado
- [ ] [Ítem específico del requerimiento]
