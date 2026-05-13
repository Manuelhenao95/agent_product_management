# PM Agent — Product Management Skill Stack

Stack de skills para Claude Code que implementa el flujo completo de documentación de producto. Diseñado para ser reutilizable en cualquier empresa.

---

## Estructura

```
.claude/
├── context/
│   ├── company_context.md      ← contexto de empresa (editable)
│   └── project_state.md        ← estado del proyecto activo (runtime, no se commitea)
└── commands/
    ├── Setup-Company.md        → /Setup-Company
    ├── New-Feature.md          → /New-Feature
    ├── Opportunity-Brief.md    → /Opportunity-Brief
    ├── Competitive-Analysis.md → /Competitive-Analysis
    ├── PRD.md                  → /PRD
    ├── Experiment-Brief.md     → /Experiment-Brief
    ├── Launch-Checklist.md     → /Launch-Checklist
    └── Retrospectiva.md        → /Retrospectiva
```

---

## Primeros pasos

### 1. Configurar el contexto de empresa
Ejecuta `/Setup-Company`. El agente te guía por preguntas para llenar `company_context.md` con los datos de tu empresa. Solo se hace una vez.

### 2. Iniciar un proyecto
Ejecuta `/New-Feature`. El agente pregunta el nombre del proyecto y el tier, inicializa el estado, y arranca el primer paso automáticamente.

---

## Flujo de trabajo por tier

| Tier | Cuándo aplica | Flujo |
|------|--------------|-------|
| **S — Small** | Fix conocido, bajo riesgo | PRD → Launch Checklist → Retrospectiva |
| **M — Medium** | Feature con ambigüedad | Opportunity Brief → PRD → Launch Checklist → Retrospectiva |
| **L — Large** | Apuesta estratégica | Opportunity Brief → Competitive Analysis → PRD → Experiment Brief → Launch Checklist → Retrospectiva |

Al finalizar cada paso, el agente pregunta: *"¿Continuamos con el siguiente paso?"* — si confirmas, ejecuta el paso siguiente sin que tengas que hacer nada más.

---

## Skills disponibles

| Skill | Descripción |
|-------|-------------|
| `/Setup-Company` | Configura el contexto de empresa guiado por preguntas |
| `/New-Feature` | Punto de entrada al flujo. Pregunta nombre y tier, y arranca |
| `/Opportunity-Brief` | Valida si el problema vale la pena resolver antes del PRD |
| `/Competitive-Analysis` | Analiza cómo resuelven el problema los competidores |
| `/PRD` | Define qué debe construir Tech exactamente |
| `/Experiment-Brief` | Diseña un A/B test antes de construir |
| `/Launch-Checklist` | Verifica que todo está listo antes de lanzar |
| `/Retrospectiva` | Documenta resultados y aprendizajes post-lanzamiento |

Cada skill también puede ejecutarse de forma independiente, sin pasar por `/New-Feature`.

---

## Adaptar a otra empresa

1. Edita `.claude/context/company_context.md` con el contexto de la nueva empresa (o ejecuta `/Setup-Company` para hacerlo guiado).
2. Los skills no requieren ningún cambio.

---

## Requisitos

- [Claude Code](https://claude.ai/code) instalado
- Proyecto abierto en Claude Code para que los skills estén disponibles
