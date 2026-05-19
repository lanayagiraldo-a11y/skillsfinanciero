---
name: arbol-rentabilidad
description: Construye e interpreta el árbol de rentabilidad (descomposición DuPont y variantes) que muestra qué componentes empujan o frenan el ROE/ROA/ROIC. Visualiza el árbol en HTML, identifica el "driver" principal de la rentabilidad y traduce los hallazgos a lenguaje de accionista. Úsala cuando el archivo tenga una hoja "Arbol Rentab" / "Árbol Rentabilidad" o cuando el usuario pida explícitamente descomposición de rentabilidad.
---

# Árbol de Rentabilidad

El árbol de rentabilidad es una herramienta de **descomposición jerárquica** que muestra de dónde viene (o por qué se pierde) la rentabilidad de una empresa.

## ¿Por qué es útil para accionistas?

Decir "el ROE bajó del 18% al 12%" no le dice al accionista QUÉ pasó. El árbol descompone esa caída en sus causas reales: ¿bajaron los márgenes? ¿cayó la rotación de activos? ¿se desapalancó? ¿subió la tasa impositiva?

## Modelos de descomposición

### 1. DuPont de 3 factores (ROE)

```
ROE = Margen Neto × Rotación de Activos × Multiplicador del Patrimonio
ROE = (UN/Ventas) × (Ventas/Activos) × (Activos/Patrimonio)
```

Significado:
- **Margen Neto**: cuánto gana por cada peso vendido
- **Rotación de Activos**: cuánto vende por cada peso de activos
- **Apalancamiento Financiero (multiplicador)**: cuánto activo respalda cada peso de patrimonio

### 2. DuPont de 5 factores (más profundo)

```
ROE = (UN/UAI) × (UAI/EBIT) × (EBIT/Ventas) × (Ventas/Activos) × (Activos/Patrimonio)
       Carga      Carga       Margen           Rotación         Apalancamiento
       Fiscal    Financiera  Operacional       Activos
```

Permite identificar si la caída del ROE viene de:
- Impuestos
- Costos financieros
- Operación pura
- Eficiencia de uso de activos
- Estructura de capital

### 3. Árbol jerárquico completo (todos los drivers)

Estructura tipo árbol:

```
                            ROE
                             |
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
        Margen Neto    Rotac. Activos   Apalancamiento
              |
       ┌──────┴──────┐
       ▼             ▼
   Margen Bruto   Gastos / Ventas
       |
   ┌───┴───┐
   ▼       ▼
 Precio  Costo Variable
              /Unidad
```

Cada nodo se descompone hasta llegar a las palancas operativas reales.

## Estructura típica de hoja "Arbol Rentab" en Excel

Las hojas que vienen en archivos contables suelen tener una estructura como:

```
| Concepto                  | Periodo Anterior | Periodo Actual | Variación |
| ROE                       | 18.5%            | 12.3%          | -6.2 pp   |
|   Margen Neto             | 8.2%             | 5.5%           | -2.7 pp   |
|     Margen Operacional    | 12.5%            | 9.8%           | -2.7 pp   |
|       Margen Bruto        | 31.0%            | 28.5%          | -2.5 pp   |
|       Gastos Op./Ventas   | 18.5%            | 18.7%          | +0.2 pp   |
|     Gastos Financ./EBIT   | 21.4%            | 28.7%          | +7.3 pp   |
|     Tasa Impositiva       | 33.0%            | 33.5%          | +0.5 pp   |
|   Rotación de Activos     | 1.45             | 1.42           | -0.03     |
|   Apalancamiento (A/P)    | 1.55             | 1.58           | +0.03     |
```

O variantes equivalentes. Acepta jerarquía por indentación, numeración (1, 1.1, 1.1.1) o por columna de "Nivel".

## Cómo identificar la hoja correcta

Patrones de nombre comunes:
- "Arbol Rentab"
- "Árbol Rentabilidad"
- "Arbol de Rentabilidad"
- "DuPont"
- "Descomposicion ROE"
- "Rentabilidad"

Patrones de contenido (si el nombre es ambiguo):
- Hay un valor de ROE o ROA en la parte superior
- Aparecen "Margen", "Rotación", "Apalancamiento" como subcomponentes
- Hay relaciones multiplicativas (los hijos multiplicados dan el padre, o suman porcentajes que descomponen un total)

## Cómo procesar el árbol

### Paso 1: Leer la hoja
Usa la skill `anthropic-skills:xlsx` o lectura con pandas vía Bash para extraer la estructura.

### Paso 2: Construir el árbol en memoria
Cada nodo tiene: nombre, valor periodo anterior, valor actual, variación, nivel jerárquico, indicador padre.

### Paso 3: Identificar el "driver principal"
El driver principal es el nodo HOJA (sin hijos) que más contribuyó a la variación del ROE/ROA/ROIC raíz.

Fórmula simplificada de contribución:
```
Contribución del nodo X = (X actual − X anterior) × peso relativo del nodo
```

### Paso 4: Visualizar — Árbol Horizontal (estilo obligatorio)

El árbol se renderiza **horizontalmente** (raíz a la izquierda, hojas a la derecha), usando UL/LI con CSS puro. Este es el único estilo aceptado para todos los informes.

**Estructura de cada nodo (`<div class="hn">`):**
- Etiqueta arriba (`hn-lbl`)
- Dos cajas de valor lado a lado: azul oscuro = periodo actual, azul claro = periodo anterior (`hn-vals` con `.az` y `.cy`)
- Delta debajo (`hn-d up|dn|neu`)

**CSS obligatorio** (copiar en el `<style>` del informe):
```css
.arbol-h-wrap { background:#f0f9ff; border:2px solid #0284c7; border-radius:12px; padding:28px 32px; overflow-x:auto; margin:20px 0; }
.arbol-h-hdr { text-align:center; margin-bottom:16px; }
.arbol-h-title { font-size:13px; font-weight:700; color:#0c4a6e; text-transform:uppercase; letter-spacing:0.5px; margin-bottom:6px; }
.arbol-h-ley { display:flex; gap:18px; justify-content:center; align-items:center; font-size:11px; color:#374151; }
.arbol-h-ley .dot { width:12px; height:12px; border-radius:2px; flex-shrink:0; display:inline-block; }
.dot-az { background:#1e40af; } .dot-cy { background:#38bdf8; }
.hn { display:inline-flex; flex-direction:column; align-items:center; text-align:center; flex-shrink:0; }
.hn .hn-lbl { font-size:9.5px; font-weight:700; color:#1e293b; line-height:1.3; margin-bottom:3px; max-width:100px; }
.hn .hn-vals { display:flex; border:1.5px solid #334155; border-radius:3px; overflow:hidden; }
.hn .hn-vals .az { background:#1e40af; color:#fff; padding:5px 8px; font-size:12px; font-weight:800; min-width:46px; text-align:center; }
.hn .hn-vals .cy { background:#38bdf8; color:#0c4a6e; padding:5px 8px; font-size:12px; font-weight:800; min-width:46px; text-align:center; }
.hn .hn-d { font-size:9px; margin-top:2px; font-weight:600; }
.hn .hn-d.up { color:#16a34a; } .hn .hn-d.dn { color:#dc2626; } .hn .hn-d.neu { color:#6b7280; }
.root-hn .hn-lbl { font-size:11px; max-width:130px; }
.root-hn .az { background:#0c4a6e; font-size:14px; padding:7px 10px; min-width:56px; }
.root-hn .cy { background:#38bdf8; font-size:14px; padding:7px 10px; min-width:56px; }
.h-tree, .h-tree ul, .h-tree li { list-style:none; margin:0; padding:0; }
.h-tree { display:flex; align-items:center; }
.h-tree li { display:flex; align-items:center; }
.h-tree ul { display:flex; flex-direction:column; position:relative; }
.h-tree ul::before { content:''; position:absolute; left:0; top:30px; bottom:30px; width:2px; background:#94a3b8; }
.h-tree ul.solo::before { display:none; }
.h-tree ul > li { padding:9px 0 9px 18px; position:relative; }
.h-tree ul > li::before { content:''; position:absolute; left:0; top:50%; transform:translateY(-50%); width:18px; height:2px; background:#94a3b8; }
.h-tree ul.solo > li { padding-left:0; }
.h-tree ul.solo > li::before { display:none; }
.h-bar { width:18px; height:2px; background:#94a3b8; flex-shrink:0; }
```

**Patrón HTML del árbol** (adaptarlo con los datos reales):
```html
<div class="arbol-h-wrap">
  <div class="arbol-h-hdr">
    <div class="arbol-h-title">Fórmula: Indicador Raíz = Factor A × Factor B</div>
    <div class="arbol-h-ley">
      <span><span class="dot dot-az"></span> Año actual</span>
      <span><span class="dot dot-cy"></span> Año anterior</span>
    </div>
  </div>
  <ul class="h-tree">
    <li>
      <!-- RAÍZ -->
      <div class="hn root-hn">
        <div class="hn-lbl">Indicador<br>Raíz</div>
        <div class="hn-vals"><span class="az">XX%</span><span class="cy">YY%</span></div>
        <div class="hn-d up">▲ +Z pp</div>
      </div>
      <div class="h-bar"></div>
      <!-- NIVEL 2: hijos -->
      <ul>
        <li>
          <div class="hn">
            <div class="hn-lbl">Factor A</div>
            <div class="hn-vals"><span class="az">XX%</span><span class="cy">YY%</span></div>
            <div class="hn-d up">▲ +Z pp</div>
          </div>
          <div class="h-bar"></div>
          <!-- NIVEL 3: nietos de A -->
          <ul>
            <li><div class="hn"><div class="hn-lbl">Sub A1</div><div class="hn-vals"><span class="az">XX</span><span class="cy">YY</span></div><div class="hn-d neu">—</div></div></li>
            <li><div class="hn"><div class="hn-lbl">Sub A2</div><div class="hn-vals"><span class="az">XX</span><span class="cy">YY</span></div><div class="hn-d dn">▼ -Z</div></div></li>
          </ul>
        </li>
        <li>
          <div class="hn">
            <div class="hn-lbl">Factor B</div>
            <div class="hn-vals"><span class="az">XX</span><span class="cy">YY</span></div>
            <div class="hn-d up">▲ +Z</div>
          </div>
          <!-- sin hijos: no poner h-bar ni ul -->
        </li>
      </ul>
    </li>
  </ul>
</div>
```

**Reglas de construcción:**
- Nodo raíz: clase `root-hn` adicional (caja más grande, fondo azul oscuro)
- Nodo con hijos: siempre `<div class="h-bar"></div>` + `<ul>` después del `.hn`
- Nodo hoja (sin hijos): solo el `<div class="hn">`, sin h-bar ni ul
- Ul con un solo hijo: agregar clase `solo` para ocultar la barra vertical
- Clases de delta: `up` (verde), `dn` (rojo), `neu` (gris)
- Siempre incluir la leyenda de colores en el header del wrapper

## Reglas de oro

1. **Siempre validar que los nodos hijos reconstruyen al padre** (multiplicativamente o por suma). Si no cuadra, hay un dato malo.
2. **Distinguir variación absoluta de variación relativa** — son lecturas distintas
3. **No todos los componentes son malos cuando bajan**: bajar la tasa impositiva mejora el ROE pero no es resultado de gestión
4. **Identificar el componente más sensible**: el que tiene mayor impacto marginal en el ROE
5. **Traducir SIEMPRE el hallazgo** — el accionista no quiere ver "el factor financiero subió 7.3 pp"; quiere ver "la empresa pagó más al banco proporcionalmente, lo que se comió la utilidad"

## Plantilla de análisis para accionistas

Después de construir el árbol, generar 3-5 párrafos breves que sigan este patrón:

**Párrafo 1 — La foto general:**
> "La rentabilidad sobre el patrimonio (lo que rinde la plata de ustedes los socios) [subió/cayó] de X% a Y%. En términos llanos, por cada $100 que tienen invertidos, este año ganaron $Z (vs. $W el año anterior)."

**Párrafo 2 — La causa principal:**
> "La razón principal de este cambio fue [driver principal]. [Explicación en lenguaje llano de qué pasó con ese driver]. Esto se debe a [causa concreta: precios, costos, eficiencia, deuda...]"

**Párrafo 3 — Los drivers secundarios:**
> "También influyeron [drivers 2 y 3], aunque en menor medida. [Explicación breve]."

**Párrafo 4 — Comparación con benchmark si está disponible:**
> "El promedio del sector tiene un ROE de Z%, lo que nos ubica [por encima/debajo] de nuestros competidores típicos."

**Párrafo 5 — Acción recomendada:**
> "Para mejorar la rentabilidad de la plata de los socios, la palanca con mayor impacto es [palanca específica]. Recomendamos [acción concreta] en los próximos [tiempo]."

## Output esperado de esta skill

Cuando se invoca esta skill en el contexto de un análisis, debe producir:

1. **Estructura del árbol** (en formato JSON/objeto Python para visualización)
2. **Driver principal identificado** (nombre + magnitud de impacto)
3. **3-5 párrafos de análisis** en lenguaje de accionista
4. **Datos listos para insertar en la plantilla HTML** `informe-rentabilidad.html`
