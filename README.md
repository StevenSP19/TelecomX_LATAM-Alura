# Telecom X – Challenge ETL

## Propósito
**Objetivo:** aplicar un proceso ETL con Python (Pandas) sobre datos de TelecomX para habilitar análisis y visualizaciones.

## Estructura del proyecto
- `data/raw`: datos crudos (API/JSON)
- `data/processed`: datos limpios transformados
- `notebooks`: cuadernos de análisis (`TelecomX_LATAM.ipynb`)
- `src`: scripts auxiliares (opcional)
- `reports`: gráficos y hallazgos (opcional)

## Flujo ETL
1. **Extract:** obtención desde API/JSON.  
2. **Transform:** limpieza, tipificación, normalización.  
3. **Load:** exportación a CSV/Parquet para análisis.  

## Instrucciones de ejecución
- Abrir `TelecomX_LATAM.ipynb` en Google Colab.  
- Ejecutar celdas en orden (de arriba hacia abajo).  
- Dependencias: `pandas`, `numpy`, `requests`, `matplotlib`, `seaborn`.  
- Resultado: `data/processed/telecomx_clean.csv` (nombre tentativo).  

## Resultados principales
- **Churn general:** ~27% de los clientes abandonan el servicio.  
- **Contrato:** mes a mes → 42.7% de abandono; 1 año → 11.3%; 2 años → 2.8%.  
- **Método de pago:** cheque electrónico → 45.3% de abandono; pagos automáticos → ~16%.  
- **Cargos totales:** clientes fieles acumulan más gasto (mediana ≈ $1,683.60) frente a los que abandonan (≈ $703.55).  
- **Meses de servicio:** fidelidad → mediana 38 meses; abandono → mediana 10 meses.  

## Conclusiones e Insights
- El churn ocurre principalmente en clientes **nuevos** y con **menor gasto acumulado**.  
- Los contratos de largo plazo y métodos de pago automáticos están asociados con **mayor fidelidad**.  
- El cheque electrónico y los contratos mes a mes son perfiles de **alto riesgo**.  

## Recomendaciones estratégicas
- Incentivar **contratos de largo plazo** con beneficios y descuentos.  
- Promover **métodos de pago automáticos** para reducir abandono.  
- Implementar **programas de fidelización temprana** en los primeros meses de servicio.  
- Monitorear clientes de **alto riesgo** (mes a mes + cheque electrónico) para ofrecer alternativas antes de que abandonen.  

## Contribución
- Se aceptan mejoras vía *pull requests*.  
- Reportar problemas en la sección *Issues*.  

## Licencia
Este proyecto se distribuye bajo la licencia MIT.  
