# Indicadores de Sostenibilidad Financiera

Miden la salud estructural de la empresa en el largo plazo, su riesgo de quiebra y su capacidad de generar valor sosteniblemente.

---

## 1. Z-Score de Altman (riesgo de quiebra)

**Para empresas privadas (no cotizadas) — Modelo Z':**

Z' = 0.717·X1 + 0.847·X2 + 3.107·X3 + 0.420·X4 + 0.998·X5

**Donde:**
- X1 = Capital de Trabajo / Activos Totales
- X2 = Utilidades Retenidas / Activos Totales
- X3 = EBIT / Activos Totales
- X4 = Patrimonio Contable / Pasivo Total
- X5 = Ventas / Activos Totales

**Zonas:**
- 🟢 Z' > 2.90: Zona Segura
- 🟡 Z' entre 1.23 y 2.90: Zona Gris (atención)
- 🔴 Z' < 1.23: Zona de Quiebra (alta probabilidad en 2 años)

**Para empresas de servicios o no manufactureras — Z'':**

Z'' = 6.56·X1 + 3.26·X2 + 6.72·X3 + 1.05·X4

(Sin X5, ya que las ventas no son comparables entre sectores)

**Zonas:**
- 🟢 Z'' > 2.60: Segura
- 🟡 Z'' entre 1.10 y 2.60: Gris
- 🔴 Z'' < 1.10: Quiebra probable

**Cómo explicarlo a un accionista:** "Es como un termómetro de salud financiera. Combina cinco signos vitales en un solo número. Por debajo del umbral, la historia muestra que muchas empresas en esa zona terminaron en quiebra en los siguientes 2 años."

---

## 2. Tasa de Crecimiento Sostenible (Modelo Higgins)

**Fórmula:** g* = ROE × (1 − Tasa de Reparto de Dividendos)

**Significado:** Es la tasa máxima a la que la empresa puede crecer sin necesidad de financiación externa adicional (sin más deuda ni emisión de acciones).

**Diagnóstico:**
- Si crecimiento real > g*: La empresa necesita financiación externa o agotará caja
- Si crecimiento real < g*: La empresa genera más caja de la que necesita
- Si crecimiento real ≈ g*: Balance saludable

**Cómo explicarlo a un accionista:** "Sin pedir más plata prestada ni meter más capital, la empresa puede crecer máximo $X% al año. Si quiere crecer más rápido, hay que decidir: pedir más al banco, reinvertir más utilidades (menos dividendos), o conseguir nuevos socios."

---

## 3. EVA — Valor Económico Agregado

**Fórmula:** EVA = NOPAT − (Capital Invertido × WACC)

**Equivalente:** EVA = Capital Invertido × (ROIC − WACC)

**Interpretación:**
- 🟢 EVA positivo: la empresa crea valor económico real
- 🔴 EVA negativo: destruye valor (aunque tenga utilidad contable)

**Cómo explicarlo a un accionista:** "Es la utilidad 'verdadera' después de descontar el costo de TODA la plata usada en el negocio (incluida la de ustedes). Si una empresa da $100 millones de utilidad contable pero el capital invertido tendría que rendir $120 millones para compensar su costo, el EVA es −$20: la empresa destruyó $20 millones de valor ese año."

---

## 4. Generación de Caja Libre (Free Cash Flow)

**Fórmula:**
```
EBITDA
− Impuestos sobre EBIT
− CAPEX (inversión en activos fijos)
− Cambios en Capital de Trabajo
= Flujo de Caja Libre (FCF)
```

**Rangos de referencia (% sobre ventas):**
- 🟢 Verde: >8%
- 🟡 Amarillo: 3-8%
- 🔴 Rojo: <3% o negativo

**Cómo explicarlo a un accionista:** "Es la caja que la empresa genera 'libre' — después de pagar todo lo necesario para mantenerse operando (impuestos, inversiones, capital de trabajo). Es la plata real que se puede usar para pagar deuda, dividendos o crecer."

---

## 5. Calidad de la Utilidad

**Fórmula:** Flujo de Caja Operativo / Utilidad Neta

**Interpretación:**
- 🟢 >1.0: las utilidades se convierten efectivamente en caja
- 🟡 entre 0.7 y 1.0: aceptable, revisar capital de trabajo
- 🔴 <0.7: utilidades de "papel" — riesgo

**Cómo explicarlo a un accionista:** "Una empresa puede mostrar utilidades en sus estados financieros pero no tener caja. Este indicador nos dice si la utilidad 'huele a plata' o solo a papel."

---

## 6. Cobertura del Servicio de la Deuda (DSCR)

**Fórmula:** EBITDA / (Servicio de la Deuda — Capital + Intereses)

**Rangos de referencia:**
- 🟢 Verde: >1.5
- 🟡 Amarillo: 1.2-1.5
- 🔴 Rojo: <1.2

**Cómo explicarlo a un accionista:** "Es el indicador que más mira el banco. Mide si la caja del negocio alcanza para pagar las cuotas de las deudas (intereses + capital). Por debajo de 1.2, los bancos no prestan."

---

## 7. Composición del Patrimonio

**Indicadores clave:**
- Capital social / Patrimonio
- Reservas / Patrimonio
- Utilidades retenidas / Patrimonio
- Revalorización del patrimonio / Patrimonio

**Diagnóstico:** Un patrimonio sano tiene una porción importante de utilidades retenidas (la empresa se autocapitaliza). Un patrimonio dominado por revalorizaciones es "papel" no realizable.

---

## 8. Crecimiento Real vs. Inflación

**Fórmula crecimiento real:** ((1 + crecimiento nominal) / (1 + inflación)) − 1

**Cómo explicarlo a un accionista:** "Si la empresa creció 8% pero la inflación fue 9%, la empresa se hizo más pequeña en términos reales. Hay que crecer SOBRE la inflación para realmente avanzar."

---

## Banderas rojas en sostenibilidad

- Z-Score en zona de quiebra o gris descendente
- Crecimiento real > tasa sostenible 2 periodos seguidos sin estructura financiera sólida
- EVA negativo persistente
- Flujo de caja libre negativo 2 años seguidos sin razón estratégica (inversión)
- Calidad de utilidad <0.7 (utilidades sin caja)
- DSCR por debajo de 1.2 con deuda creciente
