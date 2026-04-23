# Análisis de Churn y Segmentación RFM — KredMex Fintech

## Descripción del Proyecto
KredMex es una fintech mexicana de créditos personales con 1,000 clientes 
activos. La Directora de Retención necesitaba entender por qué se estaban 
perdiendo clientes y quiénes eran los más propensos a dejar de pagar, 
para poder tomar acciones preventivas antes de que el churn ocurriera.

Este proyecto está directamente relacionado con mi tesis de licenciatura 
sobre comportamiento de pago en el sector fintech mexicano.

## Problema que resolvimos
El equipo de retención no sabía:
- Qué perfil de cliente tiene mayor probabilidad de hacer churn
- Cómo segmentar a los clientes según su nivel de riesgo
- A qué clientes llamar esta semana para evitar pérdidas inmediatas

## Lo que hicimos
**Análisis exploratorio**
- Revisión de nulos, duplicados y estadísticas descriptivas
- Análisis de correlación para identificar qué variables predicen mejor el churn
- Hallazgo clave: días de atraso y score de riesgo son los mejores predictores

**Análisis con SQL**
- Tasa de churn por producto con conteo condicional (CASE WHEN)
- Comparación del perfil promedio entre clientes que se van vs los que se quedan
- Ranking de churn por estado usando window functions (RANK)
- Identificación de clientes en riesgo crítico para acción inmediata

**Segmentación RFM**
Modelo de segmentación basado en Recencia, Frecuencia y Monto:
- 🟢 CAMPEÓN — paga puntual, frecuente y montos altos
- 🟡 EN DESARROLLO — activo pero con margen de mejora
- 🟠 EN RIESGO — señales tempranas de deterioro
- 🔴 CRÍTICO — atraso mayor a 30 días o score bajo — acción inmediata

**Reporte en Excel**
- Hoja especial "Clientes en Riesgo" — lista accionable para el equipo 
  de cobranza con los clientes a llamar esta semana
- Dashboard visual incrustado

## Hallazgos principales
- Tasa de churn del 40% en todos los productos — problema sistémico 
  en la originación del crédito, no en el producto específico
- Un cliente con más de 3 días de atraso tiene perfil de churn
- Clientes con score de riesgo menor a 52 tienen alta probabilidad de irse
- 11 clientes identificados como críticos para contacto inmediato
- $54M MXN en revenue potencial en riesgo por contratos inactivos

## Recomendación principal
Endurecer los requisitos de originación de crédito y ofrecer beneficios 
por pago puntual para incentivar el cumplimiento desde el primer mes.

## Herramientas utilizadas
- **Python** — pandas, matplotlib, seaborn, numpy, correlación estadística
- **SQL** — SQLite con CASE WHEN, window functions, RANK, filtros compuestos
- **Excel** — reporte con hoja de acción inmediata para equipo de cobranza

## Archivos
- `Dia2_ef.ipynb` — notebook completo con análisis y segmentación RFM
- `analisis_clientes_KREDMEX.xlsx` — reporte Excel con lista de llamadas
