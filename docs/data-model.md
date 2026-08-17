# Modelo de datos

## Entidad: Proyecto

Cada registro representa un proyecto individual que será procesado por el sistema.

| Campo | Tipo | Rango / Formato | Descripción |
|---|---|---|---|
| project_id | texto | P001 | Identificador único |
| project_name | texto | — | Nombre del proyecto |
| manager | texto | — | Responsable del proyecto |
| start_date | fecha | YYYY-MM-DD | Fecha de inicio |
| end_date | fecha | YYYY-MM-DD | Fecha de finalización |
| budget | decimal | >= 0 | Presupuesto aprobado |
| actual_cost | decimal | >= 0 | Costo acumulado |
| expected_progress | decimal | 0-100 | Avance esperado |
| actual_progress | decimal | 0-100 | Avance real |
| status | texto | — | Estado actual del proyecto |

## Indicadores derivados

El sistema calculará posteriormente:

- Desviación del avance.
- Porcentaje de presupuesto utilizado.
- Desviación presupuestaria.
- Duración del proyecto.
- Días transcurridos.
- Días restantes.
- Nivel de riesgo.

## Reglas iniciales

- `project_id` debe ser único.
- `budget` no puede ser negativo.
- `actual_cost` no puede ser negativo.
- `expected_progress` debe estar entre 0 y 100.
- `actual_progress` debe estar entre 0 y 100.
- `end_date` debe ser posterior a `start_date`.