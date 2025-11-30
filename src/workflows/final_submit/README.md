Trabajo Final Laboratorio de Implementación I | Final submit

Descripción

En este repositorio se encuentra el notebook con el experimento 9102 utilizado para la competencia Kaggle de predicción de bajas bancarias.

Características

- **Semilla primigenia:** 500009
- **N° Experimento:** 9102
- **Optimización Bayesiana:** 20 iteraciones guardadas en el repositorio
- **Mejor score público:** 7.816M (corte 2300)
- **AUC validación:** 0.9321

Se seleccionó este experimento por su alta estabilidad entre cortes (variación 15%) y su desempeño consistente en diferentes configuraciones. El modelo forma parte de un ensemble de 4 semillas estables que alcanza ganancias proyectadas de 7.7M - 8.1M.

Hiperparámetros Óptimos

```yaml
num_leaves: 122
min_data_in_leaf: 2068
feature_fraction: 0.2222
learning_rate: 0.0051
num_iterations: 1579
```

Modificaciones Implementadas

Para optimizar el código nos basamos en buenas prácticas y experimentos colaborativos, en particular:

- **Catastrophe Analysis** con método Machine Learning para imputación de variables corruptas
- **Data Drifting** con deflación por IPC para ajustar variables monetarias
- **Feature Engineering Histórico** creando lags de orden 1 y 2 para todas las variables (~800 variables nuevas)
- Exclusión de `numero_de_cliente` y `foto_mes` para el modelado
- Tomar AUC como métrica y GBDT como método de boosting
- `training_pct = 1.0` (sin undersampling)

Resultados

| Corte | Ganancia (M) |
|-------|--------------|
| 1800  | 6.865        |
| 1900  | 6.965        |
| 2000  | 7.075        |
| 2100  | 6.795        |
| 2200  | 6.865        |
| **2300** | **7.816** |
| 2400  | 7.526        |

Autor

Nicolás  Caggiano
Materia: Laboratorio de Implementación I 2025
Maestría en Ciencias de Datos, Universidad Austral
