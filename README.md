markdown
# Modelo analítico en BigQuery con Dataform

Pipeline ELT sobre el dataset público `thelook_ecommerce` de BigQuery.

## Arquitectura
bigquery-public-data.thelook_ecommerce → staging (vistas) → marts (tablas)

## Qué incluye
- Declaración de fuentes públicas.
- Capa staging: limpieza y renombrado de columnas.
- Capa marts: tabla de hechos de ventas y agregado diario por categoría.
- Tablas particionadas por fecha y clusterizadas para reducir costo de consulta.
- Assertions de calidad: unicidad, nulos y condiciones por fila.
- Ejecución programada con release y workflow configurations.
- Service account dedicada con roles mínimos de BigQuery.

## Resultado del particionado
Consulta sin filtro de fecha: [X MB]. Con filtro de un mes: [Y MB].

## Stack
Google Cloud: BigQuery, Dataform, IAM, Secret Manager. GitHub.