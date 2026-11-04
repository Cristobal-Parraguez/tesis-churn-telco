# Modelo predictivo para la identificación del riesgo de abandono de clientes en servicios digitales de telecomunicaciones

Tesina para optar al título de Ingeniería en Informática, Universidad Bernardo O'Higgins (2026).

- **Autores:** Manuel Ramírez Reyes y Cristóbal Parraguez Aguilera
- **Profesor guía:** Cristian Lorenzo Vidal Silva

## Descripción

El notebook compara regresión logística, Random Forest y XGBoost, con y sin ponderación de clases, frente a un clasificador de referencia basado en la prevalencia. Usa el conjunto público Telco Customer Churn de IBM (7.043 clientes de una empresa ficticia). La métrica principal es la precisión promedio (AP). El modelo se selecciona con validación cruzada estratificada de 5 pliegues y se evalúa una sola vez en un conjunto de prueba aislado (20 %, semilla 42).

**Resultado principal (conjunto de prueba):** XGBoost sin ponderación, AP = 0,6607 (referencia: 0,2654); ROC-AUC = 0,8463; IC 95 % de ΔAP = [0,3527; 0,4391].

## Contenido del repositorio

| Archivo o carpeta | Contenido |
|---|---|
| `ModeloPredictivoTesis.ipynb` | Notebook completo: carga y validación de datos, modelos, pruebas CP-01 a CP-15 y análisis de la revisión por expertos (celda 15). |
| `Evidencias_ModeloPredictivoTesis.zip` | Paquete de evidencias de la ejecución: CSV, JSON, figuras, modelo serializado, `requirements.txt`, `entorno.json` y manifiesto SHA-256. |
| `revision_expertos/` | Resultados anónimos de la revisión por expertos (n = 2): respuestas del formulario, tabla por ítem, gráfico y respuestas abiertas. |

## Cómo reproducir la ejecución

1. Abrir `ModeloPredictivoTesis.ipynb` en Google Colab.
2. Ejecutar **Entorno de ejecución → Ejecutar todas**. El notebook descarga el conjunto de datos desde el repositorio de IBM y genera la carpeta `resultados_tesis/`.
3. Para la celda 15 (revisión por expertos), subir antes a Colab el archivo `revision_expertos/respuestas_formulario_expertos.csv`.

Las versiones de las bibliotecas están en `requirements.txt` y `entorno.json`, dentro del paquete de evidencias.

## Datos

Telco Customer Churn, de IBM (repositorio [IBM/telco-customer-churn-on-icp4d](https://github.com/IBM/telco-customer-churn-on-icp4d)). Son datos de ejemplo de una empresa ficticia y se usan solo con fines académicos.

## Limitaciones

Los resultados corresponden a una reevaluación interna sobre datos sin fechas. No demuestran que el modelo anticipe el abandono en un horizonte de tiempo ni que una campaña basada en él sea rentable.
