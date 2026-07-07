# 📖 Diccionario de Datos: Churn Bancario

Este documento describe las 13 variables utilizadas en el análisis de deserción de clientes.

| Variable | Tipo de Dato | Descripción |
| :--- | :--- | :--- |
| `ID_Orden` | Categórico (Texto) | Identificador único de la transacción o registro del cliente. |
| `Fecha_Alta` | Temporal (Datetime) | Fecha en la que el cliente abrió su cuenta en el banco. |
| `Ciudad` | Categórico (Texto) | Hub geográfico al que pertenece el cliente (ej. Ciudad de México, Bogotá). |
| `Edad` | Numérico (Entero) | Edad del cliente en años. |
| `Balance` | Numérico (Flotante) | Saldo total de la cuenta en el momento del análisis ($ USD). |
| `NumProductos` | Numérico (Entero) | Cantidad de productos financieros contratados (1 a 4). |
| `MiembroActivo` | Binario (0 o 1) | Indica si el cliente interactúa frecuentemente con el banco (1 = Sí). |
| `TieneTarjeta` | Binario (0 o 1) | Indica si el cliente posee una tarjeta de crédito activa (1 = Sí). |
| `Churn` | Binario (0 o 1) | **Variable Objetivo**. Indica si el cliente abandonó el banco (1 = Sí). |