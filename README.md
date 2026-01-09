# Telecom X – Challenge ETL

## Propósito
**Objetivo:** aplicar un proceso ETL con Python (Pandas) sobre datos de TelecomX para habilitar análisis y visualizaciones.

## Instrucciones de ejecución
- Abrir `TelecomX_LATAM.ipynb` en Google Colab.  
- Ejecutar celdas en orden (de arriba hacia abajo).  
- Dependencias: `pandas`, `numpy`, `requests`, `matplotlib`, `seaborn`.

## Resultados
- **Churn general:** ~27% de los clientes abandonan el servicio.  
- **Contrato:** mes a mes → 42.7% de abandono; 1 año → 11.3%; 2 años → 2.8%.  
- **Método de pago:** cheque electrónico → 45.3% de abandono; pagos automáticos → ~16%.  
- **Cargos totales:** clientes fieles acumulan más gasto (mediana ≈ $1,683.60) frente a los que abandonan (≈ $703.55).  
- **Meses de servicio:** fidelidad → mediana 38 meses; abandono → mediana 10 meses.  

## Limpieza y Tratamiento de Datos:
- Importación de datos: Se descargó el archivo JSON desde una URL de GitHub utilizando la librería requests y se cargó en un DataFrame de pandas.
- Normalización de datos: Las estructuras anidadas dentro del JSON (columnas 'customer', 'phone', 'internet', 'account') se normalizaron usando json_normalize para crear un DataFrame plano (df_full).
- Renombrado de columnas: Los nombres de las columnas se estandarizaron, convirtiéndolos a minúsculas y reemplazando espacios y puntos por guiones bajos.
- Manejo de valores vacíos en 'churn': Se identificaron valores vacíos en la columna 'churn' y se reemplazaron por NaN para un manejo adecuado de los datos faltantes.
- Conversión de tipos de datos: Las columnas account_charges_total y account_charges_monthly se convirtieron a tipo numérico (float64).
- Estandarización de texto: Se convirtieron todos los valores de las columnas de texto a minúsculas y se eliminaron espacios extra.
- Creación de nuevas características: Se creó la columna cuentas_diarias dividiendo account_charges_monthly entre 30.
- Codificación de variables binarias: Varias columnas con valores 'yes'/'no' se codificaron a 1/0 para facilitar el análisis numérico.

## Conclusiones e Insights
- El churn ocurre principalmente en clientes **nuevos** y con **menor gasto acumulado**.  
- Los contratos de largo plazo y métodos de pago automáticos están asociados con **mayor fidelidad**.  
- El cheque electrónico y los contratos mes a mes son perfiles de **alto riesgo**.  

## Recomendaciones estratégicas
- Incentivar **contratos de largo plazo** con beneficios y descuentos.  
- Promover **métodos de pago automáticos** para reducir abandono.  
- Implementar **programas de fidelización temprana** en los primeros meses de servicio.  
- Monitorear clientes de **alto riesgo** (mes a mes + cheque electrónico) para ofrecer alternativas antes de que abandonen.  
