---
name: catalogo-indicadores-financieros
description: Catálogo completo de indicadores financieros con fórmulas, rangos de referencia, interpretación y traducción a lenguaje de accionista. Cubre liquidez, rentabilidad, endeudamiento, eficiencia, capacidad financiera (margen de contribución + capacidad instalada), viabilidad de proyectos (VPN, TIR, sensibilidad), sostenibilidad (Altman Z, crecimiento sostenible) y productividad. Úsala cuando necesites calcular un indicador, interpretar un valor obtenido o explicar a un accionista qué significa una cifra.
---

# Catálogo de Indicadores Financieros

Este catálogo es la referencia maestra del sistema multi-agente. Cada categoría tiene su propio archivo de referencia con fórmulas, interpretación y traducción a lenguaje llano.

## Cómo usar este catálogo

1. Identifica qué tipo de análisis estás haciendo
2. Consulta el archivo de referencia correspondiente en `referencias/`
3. Aplica la fórmula con los datos de la empresa
4. Compara con el rango de referencia
5. Traduce el resultado a lenguaje de accionista usando la sección "Cómo explicarlo"

## Archivos de referencia disponibles

| Archivo | Cuándo consultarlo |
|---|---|
| `referencias/liquidez.md` | Capacidad de pago de corto plazo |
| `referencias/rentabilidad.md` | Si la empresa está generando ganancias suficientes |
| `referencias/endeudamiento.md` | Nivel de deuda y capacidad de pagarla |
| `referencias/eficiencia.md` | Qué tan bien usa los recursos (cartera, inventarios, activos) |
| `referencias/capacidad-financiera.md` | Margen de contribución, punto de equilibrio, capacidad instalada vs. ociosa |
| `referencias/viabilidad-proyectos.md` | VPN, TIR, payback, análisis de sensibilidad para proyectos |
| `referencias/sostenibilidad.md` | Riesgo de quiebra (Altman Z), crecimiento sostenible, EVA |
| `referencias/productividad.md` | Productividad por empleado, por activo, por unidad de capacidad |

## Reglas obligatorias al usar indicadores

1. **Nunca presentes un indicador solo** — siempre acompañado de: fórmula usada, valor obtenido, rango de referencia, interpretación y recomendación.
2. **Siempre usa semáforos**: 🟢 verde (saludable) / 🟡 amarillo (atención) / 🔴 rojo (acción inmediata). Los criterios de cada semáforo están en cada archivo de referencia.
3. **Compara contra 3 referencias cuando sea posible**: histórico de la empresa, sector y meta interna.
4. **Traduce al final**: cada indicador termina con una frase en lenguaje llano que cualquier accionista entendería sin formación financiera.
5. **Si faltan datos**, dilo claramente. No inventes cifras.
