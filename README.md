# ICN292 – Laboratorio 3: Triage de devoluciones con n8n

- **Estudiante:** Daniela López García
- **Rol:** 202360502-6
- **RUT:** 27.518.225-7
- **Semilla:** S = 225 → U = $55.000  D = 14 días
- **Paralelo:** 101
- **Fecha:** 21-09-2026
- **Repositorio:** https://github.com/Danielalopezg/ICN292-Lab3-Lopez-Daniela

## Contenido

| Archivo | Qué es |
|---|---|
| `ICN292-Lab3-Lopez-Daniela.pdf` | Informe (parámetros, resultados de las 15 solicitudes, Partes A, B y C, capturas) |
| `ICN292-Lab3-Lopez-Daniela-triage.json` | Workflow de triage (Parte A): Webhook → Switch → Edit Fields → mindicador → Data Table → Gmail → Respond to Webhook |
| `ICN292-Lab3-Lopez-Daniela-emisor.json` | Workflow emisor que envía las 15 solicitudes por POST al webhook |
| `ICN292-Lab3-Lopez-Daniela-resumen.json` | Workflow programado de resumen diario con Summarize (Parte B) |
| `ICN292-Lab3-Lopez-Daniela-error-workflow.json` | Error Workflow que avisa por Gmail cuando un flujo falla (Parte C) |
| `ICN292-Lab3-Lopez-Daniela-pruebas-parteC.json` | Envío de los casos borde de la Parte C |

## Cómo reproducir

1. En n8n: **Workflows → Import from File** y seleccionar cada `.json`.
2. Crear una credencial **Gmail OAuth2** propia y asignarla a los nodos Gmail (los `.json` no incluyen credenciales).
3. Crear la Data Table `registro_devoluciones` con las columnas: id_solicitud, sku, unidades, monto, dias_desde_compra, estado_producto, email_cliente, ruta, causal, motivo, U, D, dolar_clp, monto_usd; y seleccionarla en los nodos Data Table.
4. Publicar el workflow de triage y el Error Workflow; en los workflows emisor y de pruebas, reemplazar la URL del webhook por la URL de producción propia.
5. Ejecutar el emisor: la tabla de resultados muestra identificador, ruta y motivo de cada solicitud.

