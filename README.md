# Sistema Analítico Financiero Multi-Agente

Sistema multi-agente de análisis financiero construido sobre Claude Code (Anthropic).
Diseñado para análisis de junta directiva y accionistas en lenguaje claro, sin tecnicismos.

**Instalable en cualquier empresa:** los agentes son genéricos. Cada empresa se configura
sola con su carpeta en `empresas/<nombre-empresa>/`, donde quedan sus análisis por período.

## Estructura del sistema

```
.claude/
├── agents/                         # Agentes especializados
│   ├── analista-financiero-senior.md   # Orquestador principal (Claude Opus)
│   ├── analista-datos-financieros.md   # Extrae y calcula indicadores
│   ├── contador-colombia.md            # Calidad contable NIIF / PUC
│   ├── revisor-fiscal-colombia.md      # Riesgos fiscales y tributarios
│   ├── analista-viabilidad-proyectos.md # VPN, TIR, WACC, sensibilidad
│   ├── analista-sectorial.md           # Benchmarking sectorial Colombia
│   └── auditor-integridad-financiera.md # Verifica fórmulas y sesgos
│
└── skills/                         # Habilidades compartidas
    ├── catalogo-indicadores-financieros/ # Fórmulas e interpretación
    ├── generar-informe-ejecutivo/        # Plantillas HTML (trimestral, anual, junta, rentabilidad)
    ├── arbol-rentabilidad/               # Árbol DuPont horizontal
    ├── normativa-colombia/               # NIIF, ET, PUC, Ley 43
    └── traducir-lenguaje-accionista/     # Glosario técnico → lenguaje llano

empresas/                           # Informes generados por empresa
└── [nombre-empresa]/
    └── analisis-YYYY-MM/
        └── informe-*.html
```

## Agentes

| Agente | Modelo | Rol |
|---|---|---|
| `analista-financiero-senior` | Opus | Orquestador. Coordina el equipo, consolida y entrega al accionista |
| `analista-datos-financieros` | Sonnet | Extrae datos de Excel/PDF y calcula indicadores |
| `contador-colombia` | Sonnet | Calidad contable, NIIF, clasificación de cuentas |
| `revisor-fiscal-colombia` | Sonnet | Riesgos fiscales, cumplimiento DIAN, exposición tributaria |
| `analista-viabilidad-proyectos` | Sonnet | Evaluación de inversiones: VPN, TIR, WACC, escenarios |
| `analista-sectorial` | Sonnet | Benchmarking vs. sector y competidores colombianos |
| `auditor-integridad-financiera` | Sonnet | Verifica fórmulas, cuadres contables y sesgos en el análisis |

## Flujo de trabajo

```
Usuario adjunta Excel/PDF
        ↓
Analista Senior (orquestador)
  ├── Analista Datos Financieros  ─┐
  ├── Contador Colombia            ├─ EN PARALELO
  ├── Revisor Fiscal Colombia      │
  └── Analista Sectorial          ─┘
        ↓
Auditor de Integridad Financiera  ← valida antes de publicar
        ↓
Informe HTML ejecutivo → accionistas / junta directiva
```

## Informes generados

Los informes HTML incluyen:
- Semáforos visuales por indicador (🟢🟡🔴)
- Árbol de rentabilidad operativa horizontal (estilo DuPont)
- Gráficos interactivos con Chart.js
- Lenguaje para accionistas sin formación financiera
- Sello de autoría configurable por empresa (ej.: **Edith Royero | Financiera**)

## Uso

Abre Claude Code en este directorio. El agente orquestador se activa automáticamente.
Adjunta el archivo Excel con los estados financieros o indicadores precalculados.

---

*Sistema analítico multi-agente · Edith Royero — Financiera · Origen: Transportes La Carolina*
