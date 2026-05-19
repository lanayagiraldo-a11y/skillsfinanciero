# Viabilidad Financiera de Proyectos

Indicadores y métodos para evaluar si una inversión o proyecto vale la pena financieramente.

---

## 1. Flujo de Caja del Proyecto

**Estructura típica:**
```
Año 0: −Inversión Inicial (CAPEX + Capital de Trabajo)
Año 1..n:
  + Ingresos
  − Costos y Gastos Operativos
  − Depreciación
  = EBIT
  − Impuestos
  = NOPAT
  + Depreciación (se devuelve, no es salida de caja)
  − Cambios en Capital de Trabajo
  − CAPEX adicional
  = Flujo de Caja Libre
Año n (final):
  + Valor Terminal (valor residual + recuperación capital de trabajo)
```

**Regla:** Trabajar con flujos **después de impuestos**.

---

## 2. VPN — Valor Presente Neto (NPV)

**Fórmula:** Σ [Flujo de Caja_t / (1 + WACC)^t] − Inversión Inicial

**Criterio de decisión:**
- 🟢 VPN > 0: el proyecto crea valor (acepta)
- 🟡 VPN = 0: indiferente
- 🔴 VPN < 0: destruye valor (rechaza)

**Cómo explicarlo a un accionista:** "Es 'cuánta plata vale hoy' todo lo que el proyecto va a generar en el futuro, después de descontar lo que ese dinero podría rendir en otra inversión. Si es positivo, el proyecto añade riqueza a la empresa; si es negativo, sería mejor invertir esa plata en otra cosa."

---

## 3. TIR — Tasa Interna de Retorno (IRR)

**Definición:** Tasa de descuento que hace VPN = 0.

**Criterio de decisión:**
- 🟢 TIR > WACC: aceptable
- 🔴 TIR < WACC: rechazar

**Rangos de referencia en Colombia (proyectos privados):**
- Bajo riesgo: TIR esperada >12%
- Riesgo medio: TIR esperada >18%
- Alto riesgo: TIR esperada >25%

**Cómo explicarlo a un accionista:** "Es el 'rendimiento anual' del proyecto. Si el proyecto rinde 22% y la plata les costaría 15%, el proyecto les deja 7 puntos limpios. Si rinde 10% y cuesta 15%, están perdiendo 5 puntos."

---

## 4. TIR Modificada (TIRM / MIRR)

**Por qué usarla:** La TIR clásica asume reinversión a la misma TIR (poco realista). La TIRM asume reinversión al WACC.

**Cómo explicarlo a un accionista:** "Es una versión más conservadora y realista del rendimiento del proyecto. Si la TIR clásica da muy alta (>40%), confirme con TIRM porque puede estar inflada."

---

## 5. Payback Simple

**Fórmula:** Tiempo en que los flujos de caja acumulados igualan la inversión inicial.

**Rangos de referencia:**
- 🟢 Verde: <3 años (proyectos comerciales) / <5 años (proyectos industriales)
- 🟡 Amarillo: 3-5 / 5-8 años
- 🔴 Rojo: >5 / >8 años

**Cómo explicarlo a un accionista:** "Es cuánto se demora la empresa en recuperar la plata invertida. Es el indicador favorito porque es intuitivo, pero no toma en cuenta lo que pasa después del payback ni el valor del dinero en el tiempo."

---

## 6. Payback Descontado

**Diferencia:** Igual al payback pero descontando los flujos al WACC. Da un tiempo de recuperación más realista (siempre mayor o igual al payback simple).

---

## 7. Índice de Rentabilidad (IR / PI)

**Fórmula:** Valor Presente de Flujos Futuros / Inversión Inicial

**Criterio:**
- 🟢 IR > 1: crea valor
- 🔴 IR < 1: destruye valor

**Cómo explicarlo a un accionista:** "Por cada $1 invertido, el proyecto vale $X hoy en valor presente. Un IR de 1.4 significa que cada peso invertido se convierte en $1.40 de valor presente."

---

## 8. WACC — Costo Promedio Ponderado de Capital

**Fórmula:** WACC = (E/V) × Ke + (D/V) × Kd × (1 − T)

**Donde:**
- E: patrimonio / V: valor total / D: deuda
- Ke: costo del patrimonio (CAPM: Rf + β × (Rm − Rf) + riesgo país)
- Kd: costo de la deuda (tasa promedio)
- T: tasa impuesto

**Componentes típicos en Colombia (2024-2026):**
- Rf (tasa libre de riesgo, TES 10 años): ~10-11%
- Prima de mercado (Rm − Rf): ~5-7%
- Riesgo país Colombia: ~2-3%
- Beta sectorial: depende del sector (transporte ~1.0; tech ~1.3; servicios públicos ~0.6)

**Cómo explicarlo a un accionista:** "Es el costo promedio del dinero que usa la empresa, mezclando lo que cobra el banco (deuda) y lo que esperan ustedes los socios (patrimonio). Un proyecto que rinda menos que el WACC les hace perder valor aunque dé utilidad contable."

---

## 9. Análisis de Sensibilidad

**Proceso:** Variar UNA variable clave a la vez ±10%, ±20%, ±30% y ver impacto en VPN/TIR.

**Variables típicas a sensibilizar:**
- Precio de venta
- Volumen de ventas
- Costos variables
- Costos fijos
- Inversión inicial
- WACC
- Valor terminal

**Resultado:** Tabla de "elasticidades" que muestra cuál variable mueve más el VPN.

**Cómo explicarlo a un accionista:** "El proyecto está sano siempre que el precio no caiga más del 12% o el costo no suba más del 18%. Más allá de eso, deja de ser rentable. Esto nos dice 'qué tanto aire' tiene el proyecto."

---

## 10. Análisis de Escenarios

**Tres escenarios estándar:**
| Escenario | Probabilidad | Supuestos |
|---|---|---|
| Pesimista | 25% | Caídas de 15-20% en variables favorables, aumentos en costos |
| Base | 50% | Supuestos esperados |
| Optimista | 25% | Mejoras de 10-15% en variables favorables |

**VPN Esperado:** Σ (VPN_escenario × Probabilidad)

**Cómo explicarlo a un accionista:** "Si las cosas salen como esperamos, ganamos $X. Si salen mal, perdemos $Y. Si salen muy bien, ganamos $Z. Ponderado por probabilidad, lo más razonable es esperar ganar $W."

---

## 11. Análisis de Punto Muerto del Proyecto

**Variables clave a calcular:**
- Precio mínimo de venta para VPN=0
- Volumen mínimo para VPN=0
- Costo máximo aceptable para VPN=0

**Cómo explicarlo a un accionista:** "Si vendemos por debajo de $X precio o por debajo de Y unidades, el proyecto deja de ser rentable. Eso es lo que NO puede pasar."

---

## Reglas de decisión combinadas

| VPN | TIR vs WACC | Payback vs Aceptable | Decisión |
|---|---|---|---|
| Positivo | TIR > WACC | Dentro de aceptable | 🟢 Aceptar |
| Positivo | TIR > WACC | Mayor al aceptable | 🟡 Evaluar liquidez |
| Positivo bajo | TIR ≈ WACC | Cualquiera | 🟡 Sensibilizar antes de decidir |
| Negativo | TIR < WACC | Cualquiera | 🔴 Rechazar |

---

## Banderas rojas en proyectos

- VPN dependiente >50% del valor terminal (proyecto especulativo)
- TIR demasiado alta (>40%) sin causa lógica — revisar supuestos
- Análisis de sensibilidad muestra que con caídas pequeñas (<10%) el VPN se vuelve negativo
- Proyecto sin escenario pesimista calculado
- WACC inferior a la tasa libre de riesgo (mal calculado)
