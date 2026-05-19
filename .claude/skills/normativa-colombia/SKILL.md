---
name: normativa-colombia
description: Base de conocimiento normativa de Colombia para análisis contable, fiscal y financiero. Cubre NIIF para Pymes y Plenas, Plan Único de Cuentas (PUC), Estatuto Tributario (renta, IVA, retenciones), obligaciones DIAN, ICA municipal, Ley 43 de 1990 (revisoría fiscal) y NIA (Normas Internacionales de Auditoría). Úsala cuando necesites verificar cumplimiento normativo colombiano, clasificar cuentas, identificar obligaciones tributarias, evaluar riesgos fiscales o validar la presentación de estados financieros.
---

# Normativa Financiera y Tributaria de Colombia

Esta skill contiene los lineamientos normativos clave aplicables al análisis financiero en Colombia. Es la fuente de verdad cuando se necesite verificar cumplimiento, clasificación contable o tratamiento tributario.

## Archivos de referencia

| Archivo | Contenido |
|---|---|
| `referencias/niif-pymes.md` | NIIF para Pymes — Grupo 2 (mayoría de empresas en Colombia) |
| `referencias/niif-plenas.md` | NIIF Plenas — Grupo 1 (emisores de valores, entidades de interés público) |
| `referencias/puc-colombia.md` | Plan Único de Cuentas — clasificación contable |
| `referencias/estatuto-tributario.md` | Renta, IVA, GMF, riqueza, normalización tributaria |
| `referencias/retenciones-dian.md` | Tabla de retenciones en la fuente, IVA, ICA, autorretención |
| `referencias/ley-43-revisoria-fiscal.md` | Revisoría fiscal, código de ética, NIA aplicables |

---

## Marco normativo colombiano — Visión general

### Contabilidad

| Norma | Aplica a | Vigencia |
|---|---|---|
| **NIIF Plenas** (Grupo 1) | Emisores de valores, entidades del sistema financiero, entidades de interés público | Desde 2015 |
| **NIIF para Pymes** (Grupo 2) | Empresas medianas y grandes que no son de Grupo 1 | Desde 2016 |
| **Contabilidad Simplificada** (Grupo 3) | Microempresas (Decreto 2706/2012, ahora DUR 2420/2015) | Desde 2015 |

**Clasificación de grupos según activos/empleados (Decreto 2420 de 2015):**

| Grupo | Criterios |
|---|---|
| Grupo 1 | Cotiza en bolsa, capta recursos del público, supervisada por SFC |
| Grupo 2 | No cumple G1, planta de personal >10 empleados o activos totales >500 SMMLV |
| Grupo 3 | Microempresa: ≤10 empleados Y activos ≤500 SMMLV |

### Plan Único de Cuentas

- **PUC Comerciantes** (Decreto 2650 de 1993) — Empresas comerciales/industriales
- **PUC Entidades Financieras** (Resoluciones SFC)
- **PUC Salud, Cooperativas, Servicios Públicos** — Sectoriales

### Tributario (Estatuto Tributario)

- **Renta y complementarios** — Anual, declaración entre marzo-junio (gran contribuyente abril; otros junio-julio)
- **IVA** — Bimestral, cuatrimestral o anual según ingresos
- **Retención en la fuente** — Mensual
- **ICA** — Municipal, periodicidad varía por municipio
- **Impuesto de Industria, Comercio y Avisos** — Bogotá: bimestral
- **GMF (4×1000)** — Sobre transacciones financieras

### Auditoría y Revisoría Fiscal

- **Ley 43 de 1990** — Reglamenta la profesión del Contador Público
- **NIA (Normas Internacionales de Auditoría)** — Aplicables desde 2016
- **NICC 1** — Control de calidad en firmas
- **Código de Ética IFAC** — Adoptado en Colombia

---

## Quién debe tener Revisor Fiscal (Art. 203 Código de Comercio + Ley 43/90)

**Obligados:**
1. Sucursales de sociedades extranjeras
2. Sociedades por acciones (S.A., SAS si lo establecen estatutos)
3. Sociedades cuyos activos al 31/dic año anterior fueron ≥ 5.000 SMMLV
4. Sociedades cuyos ingresos brutos al 31/dic año anterior fueron ≥ 3.000 SMMLV
5. Entidades vigiladas por la Superintendencia Financiera
6. Entidades sin ánimo de lucro con activos o ingresos sobre los umbrales

**SMMLV 2026 (proyectado):** ~$1.500.000 — verificar valor vigente al momento del análisis.

---

## Plazos tributarios clave (referenciales — siempre verificar calendario DIAN del año)

| Obligación | Periodicidad | Plazo aproximado |
|---|---|---|
| Renta personas jurídicas (gran contribuyente) | Anual | Abril (cuotas) |
| Renta otros | Anual | Mayo-Julio (según NIT) |
| IVA | Bimestral o cuatrimestral | Mes siguiente al periodo |
| Retención en la fuente | Mensual | Mes siguiente |
| Información exógena | Anual | Marzo-Mayo |
| Medios magnéticos | Anual | Marzo-Mayo |

---

## Indicadores con tratamiento tributario diferenciado (Colombia)

- **Tarifa renta personas jurídicas 2026:** 35% (verificar reformas vigentes)
- **Tarifa renta presuntiva:** 0% desde 2021
- **Sobretasa financiera:** 5% adicional para entidades financieras con utilidad >$120.000 UVT
- **Beneficio ZESE (Zonas Especiales Económicas):** tarifas reducidas en ciertos territorios
- **Beneficios Ley 1429 (formalización), Ley 1819, Reformas tributarias recientes** — verificar vigencia

---

## Cómo usar esta skill

1. Identifica el tipo de pregunta: contable, tributaria, de auditoría o de presentación
2. Consulta el archivo de referencia correspondiente
3. **Siempre verifica fechas y valores** (UVT, SMMLV, tarifas) contra fuentes oficiales actuales:
   - DIAN: www.dian.gov.co
   - Consejo Técnico de la Contaduría Pública: www.ctcp.gov.co
   - Supersociedades: www.supersociedades.gov.co
4. Cita el artículo o norma específica cuando hagas afirmaciones técnicas
5. Si la norma ha cambiado o tiene reforma pendiente, adviértelo

---

## Banderas rojas tributarias frecuentes

- Diferencias significativas entre utilidad contable y utilidad fiscal sin explicación
- Inventarios con rotación lenta sin provisión por obsolescencia
- Cuentas por cobrar >360 días sin provisión de cartera
- Activos fijos depreciados con vida útil distinta a tabla DIAN
- Costos no soportados con factura electrónica válida
- Operaciones con vinculados sin estudio de precios de transferencia (si aplica)
- Compras a no obligados a facturar electrónicamente
- Ingresos no declarados detectables por cruces de exógena DIAN
