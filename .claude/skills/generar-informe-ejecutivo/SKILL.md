---
name: generar-informe-ejecutivo
description: Genera informes financieros ejecutivos en HTML interactivo, Word (.docx), Excel (.xlsx) y PDF, en lenguaje de accionista, con semáforos visuales, gráficos automáticos y estructura de 3 capas (resumen ejecutivo, análisis detallado, anexo técnico). Tiene plantillas pre-hechas para informes trimestrales, anuales y de junta directiva. Úsala cuando necesites entregar el producto final al usuario después de haber consolidado el análisis de los especialistas.
---

# Generación de Informes Ejecutivos

Esta skill se encarga de **traducir el análisis financiero en un producto entregable** que pueda ser presentado a una junta directiva o accionistas.

## Estructura obligatoria de todo informe

Todo informe que genere este sistema debe tener **3 capas**:

### Capa 1 — Resumen Ejecutivo (1 página)
- Encabezado: empresa, periodo, fecha del informe
- 3-5 hallazgos clave (bullets, sin tecnicismos)
- Tablero de semáforos (5-8 indicadores principales con 🟢🟡🔴)
- Recomendaciones accionables (qué hacer en 30/60/90 días)

### Capa 2 — Análisis Explicado (3-8 páginas)
- Una sección por cada tipo de análisis solicitado
- Cada indicador con: fórmula → valor → semáforo → traducción a lenguaje llano
- Gráficos automáticos (ver más abajo)
- Comparativos: histórico empresa + sector + meta interna

### Capa 3 — Anexo Técnico
- Cifras detalladas, fuentes de datos
- Supuestos utilizados
- Fórmulas y memorias de cálculo
- Para tu equipo o auditores

---

## Plantillas disponibles

| Plantilla | Cuándo usarla |
|---|---|
| `plantillas/informe-trimestral.html` | Análisis Q1, Q2, Q3, Q4 — foco en evolución vs. trimestre anterior y vs. mismo trimestre año pasado |
| `plantillas/informe-anual.html` | Cierre de año — incluye análisis estratégico, sostenibilidad, viabilidad y proyección |
| `plantillas/informe-junta.html` | Presentación para junta directiva — más ejecutivo, menos detalle, máximo gráfico |
| `plantillas/informe-rentabilidad.html` | **Análisis específico de rentabilidad con árbol DuPont** — úsala cuando el usuario adjunte un archivo Excel con hojas "Indicadores" + "Árbol Rentabilidad", o cuando pida explícitamente descomposición de ROE/ROA. Incluye dashboard de 4 KPIs, árbol visual con driver principal resaltado, 5 párrafos de análisis para accionistas, tablas de indicadores por categoría y 4 gráficos complementarios. Combinar con la skill `arbol-rentabilidad`. |

---

## Formatos de salida

### HTML interactivo
- Usa la plantilla correspondiente como base
- Inserta gráficos con Chart.js (CDN: `https://cdn.jsdelivr.net/npm/chart.js`)
- Semáforos como CSS (verde #16a34a, amarillo #eab308, rojo #dc2626)
- Tablas responsivas
- Botón "imprimir/exportar" PDF al final

### Word (.docx)
- Usar la skill `anthropic-skills:docx`
- Aplicar estilos de encabezado, tablas con bordes, paleta corporativa
- Insertar imágenes de los gráficos previamente generados

### Excel (.xlsx)
- Usar la skill `anthropic-skills:xlsx`
- Hojas separadas: "Resumen", "Indicadores", "Estados Financieros", "Proyecciones", "Sensibilidad"
- Formato condicional para semáforos (verde/amarillo/rojo automático según rangos)
- Gráficos nativos de Excel

### PDF
- Generar primero HTML o Word, luego convertir
- Usar la skill `anthropic-skills:pdf` para combinar/finalizar

---

## Sello de autoría — OBLIGATORIO en todos los informes

Todo informe generado por este sistema debe incluir el sello de **Edith Royero** en dos lugares:

**En el header** (dentro del `<div class="header">` o `<div class="cover">`):
```html
<div class="sello-header">
  <div class="sello-icono">ER</div>
  <div>
    <div class="sello-nombre">Edith Royero</div>
    <div class="sello-cargo">Financiera</div>
  </div>
</div>
```

**En el footer** (dentro del `<div class="footer">`):
```html
<div class="sello-footer-wrap">
  <div class="sello-icono-footer">ER</div>
  <div>
    <div class="sello-footer-nombre">Edith Royero</div>
    <div class="sello-footer-cargo">Financiera</div>
    <div class="sello-footer-prep">Análisis preparado y certificado por</div>
  </div>
</div>
```

El CSS del sello ya está incluido en todas las plantillas. Al generar un informe desde cero (sin usar plantilla), copiar el bloque CSS marcado con `/* SELLO — Edith Royero */` de cualquier plantilla.

---

## Reglas de estilo (obligatorias)

1. **Encabezado profesional**: nombre empresa, NIT, periodo analizado, fecha emisión, autor ("Sistema Analítico Financiero")
2. **Nunca usar jerga sin explicar**: si dices "EBITDA" la primera vez, agrega "(la caja que genera el negocio antes de intereses, impuestos y depreciación)"
3. **Usar analogías cotidianas**: "como si fuera una hipoteca", "como el termómetro de un paciente", "como una alcancía"
4. **Gráficos siempre con título y conclusión**: cada gráfico debe tener un título descriptivo Y una frase debajo que diga qué muestra
5. **Semáforos en TODO indicador**: nunca presentar un número sin su semáforo
6. **Limitar tablas a 7±2 filas**: si son más, partir o resumir
7. **Recomendaciones en formato 30/60/90 días**: corto, mediano, largo plazo

---

## Plantilla de gráficos recomendados por tipo de análisis

| Análisis | Gráficos sugeridos |
|---|---|
| Liquidez | Barras evolutivas razón corriente + línea capital de trabajo |
| Rentabilidad | Cascada (waterfall) Ventas → Margen Bruto → Operacional → Neto |
| Endeudamiento | Donut composición pasivos + barras Deuda/EBITDA evolutivo |
| Capacidad financiera | Gráfico cruzado capacidad usada (X) vs. margen contribución (Y) con cuadrantes |
| Viabilidad | Tornado de sensibilidad + cascada del flujo de caja |
| Sectorial | Radar comparativo empresa vs. sector |
| Sostenibilidad | Línea Z-Score histórico con bandas de color |
| Productividad | Barras ingresos por empleado vs. sector |

---

## Flujo de generación de un informe

```
1. Recibir análisis consolidado del orquestador
2. Identificar plantilla a usar (trimestral / anual / junta)
3. Generar cada gráfico necesario
4. Llenar Capa 1 (Resumen ejecutivo)
5. Llenar Capa 2 (Análisis detallado)
6. Llenar Capa 3 (Anexo técnico)
7. Generar formato(s) solicitado(s): HTML / Word / Excel / PDF
8. Guardar en: empresas/[nombre-empresa]/analisis-YYYY-MM/
9. Entregar al usuario con ruta de los archivos generados
```

---

## Convención de nombres de archivos

```
empresas/
└── [nombre-empresa-en-kebab-case]/
    └── analisis-YYYY-MM/
        ├── informe-ejecutivo.html
        ├── informe-ejecutivo.docx
        ├── indicadores-detallados.xlsx
        ├── informe-junta.pdf
        └── data/
            ├── grafico-rentabilidad.png
            └── ...
```
