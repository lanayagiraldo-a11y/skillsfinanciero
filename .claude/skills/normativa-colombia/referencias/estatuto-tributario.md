# Estatuto Tributario Nacional — Referencia para Análisis Financiero

Resumen de los principales impuestos nacionales en Colombia que afectan el análisis financiero. **Las tarifas y umbrales cambian con reformas tributarias** — siempre verificar vigencia.

## Impuesto sobre la Renta y Complementarios

### Tarifa general personas jurídicas
- **2026 (proyectado):** 35% (general)
- Sobretasa entidades financieras: +5% si utilidad > 120.000 UVT (~$5.500 millones)
- Sobretasa generación de energía hidroeléctrica: +3% (Ley 2277/2022)

### Renta presuntiva
- Eliminada para personas jurídicas desde 2021 (tarifa 0%)

### Beneficios y descuentos tributarios vigentes
- **Crédito fiscal por inversiones en CTeI** (Art. 256 ET)
- **Descuento por donaciones** (Art. 257 ET)
- **Beneficio ZESE** (zonas afectadas por conflicto, fronterizas)
- **Régimen ZOMAC** (Zonas Más Afectadas por el Conflicto Armado)
- **Régimen Simple de Tributación** (Art. 903 a 916 ET) — alternativa para pequeños

### Costos y deducciones — Reglas clave
- Costos y deducciones deben tener **soporte de factura electrónica válida** (Art. 771-2 ET)
- Pagos en efectivo limitados a 100 UVT (Art. 771-5 ET)
- Intereses deducibles solo si la deuda no excede 2 veces el patrimonio líquido (subcapitalización, Art. 118-1 ET)
- Pagos al exterior: deducibles solo con certificación de no obligación de retener o con la retención (Art. 121 ET)
- Operaciones con paraísos fiscales: retención del 35% y limitaciones de deducibilidad

### Ingresos no constitutivos / Rentas exentas relevantes
- Aportes obligatorios al sistema de seguridad social
- Algunos ingresos por enajenación de acciones inscritas en BVC (Art. 36-1 ET)
- Inversiones nuevas en sectores específicos (verificar Art. 235-2 ET vigente)

## Impuesto sobre las Ventas (IVA)

### Tarifas
- **General:** 19%
- **Reducida (5%):** algunos alimentos básicos, vivienda, salud, transporte aéreo nacional
- **Excluidos:** servicios médicos, educación, transporte público de pasajeros, servicios públicos domiciliarios estrato 1, 2 y 3

### Régimen de IVA
- Responsables: facturan IVA, declaran y pagan
- No responsables: pequeños que no superan ciertos umbrales (Art. 437 parágrafo 3 ET)

### Periodicidad de declaración
- **Bimestral:** grandes contribuyentes y empresas con ingresos > 92.000 UVT año anterior
- **Cuatrimestral:** ingresos entre 0 y 92.000 UVT
- **Anual:** régimen simple

## Gravamen a los Movimientos Financieros (GMF) — "4×1000"

- Tarifa: 0.4% (4 por mil) sobre transacciones financieras
- Algunos retiros están exentos hasta cierto monto en una sola cuenta marcada
- Es **deducible al 50% en renta** (Art. 115 ET)

## Impuesto al Patrimonio (vigencia 2023-2026 por Ley 2277/2022)

Aplica a personas naturales con patrimonio > 72.000 UVT (~$3.300 millones).
- Tarifa: marginal 0.5% / 1% / 1.5%

(No aplica a personas jurídicas en 2026, salvo reforma)

## Retenciones en la fuente

Ver archivo `retenciones-dian.md` para tabla completa.

## Información Exógena

- **Resolución DIAN** anual define quiénes y qué reportan
- Cruces obligatorios entre lo declarado y lo reportado por terceros
- Errores en exógena son la principal fuente de requerimientos DIAN

## Régimen Simple de Tributación

Alternativa al impuesto sobre la renta para:
- Personas jurídicas o naturales con ingresos brutos < 100.000 UVT año anterior
- Tarifas reducidas según actividad (consolida renta, ICA y avisos)
- Excluyen GMF (paga)
- Pago bimestral con declaración anual

## Precios de Transferencia

- Aplican a operaciones con vinculados del exterior o residentes en paraísos fiscales
- Obligación de informe local + maestro + país por país (si umbral cumple)
- Estudios técnicos: arms length principle
- Importante para análisis de empresas multinacionales o con holding extranjera

## UVT (Unidad de Valor Tributario)

- **2026 (proyectado):** ~$49.799 — verificar resolución DIAN del año
- Sirve para indexar topes, sanciones, tarifas progresivas

## Banderas rojas tributarias en análisis financiero

1. **Diferencia significativa contable-fiscal** sin explicación documentada
2. **Cartera vieja sin provisión** que afecta impuesto diferido
3. **Pagos en efectivo** que excedan límites (riesgo no deducibilidad)
4. **Operaciones con vinculados** sin estudio de precios de transferencia
5. **Compras a no obligados** a facturar electrónicamente
6. **Activos fijos con vida útil contable distinta a fiscal** sin impuesto diferido
7. **Provisiones contables no fiscales** (laborales, garantías) sin reconocer DT
8. **Excedente de intereses** que viole regla de subcapitalización (deducibilidad limitada)
9. **Costos sin proveedor inscrito en RUT** correctamente
10. **Donaciones** no documentadas con requisitos del Art. 125 ET

## Sanciones más comunes (Estatuto Tributario)

- **Por no declarar (Art. 643):** 20% del valor de las consignaciones del periodo
- **Por extemporaneidad (Art. 641):** 5% por mes o fracción de retraso, hasta 100%
- **Por corrección (Art. 644):** 10% del mayor valor a pagar
- **Por inexactitud (Art. 647):** 100% de la diferencia
- **Sanción mínima (Art. 639):** 10 UVT (~$498.000 en 2026)

## Calendario tributario referencia 2026

| Obligación | Plazo |
|---|---|
| Renta Personas Jurídicas Grandes Contribuyentes | Abril (cuotas previas en febrero) |
| Renta otras Personas Jurídicas | Mayo-Julio (según últimos dígitos NIT) |
| IVA bimestre 1 | Marzo |
| IVA bimestre 6 | Enero año siguiente |
| Información Exógena Personas Jurídicas | Mayo-Junio |
| Medios Magnéticos | Mayo-Junio |
| Retención en la Fuente mensual | Mes siguiente, según últimos dígitos |

**Siempre verificar el Decreto de Calendario Tributario emitido por la DIAN cada año.**
