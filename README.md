End-to-End Data Engineering &amp; Predictive Maintenance project for Oil &amp; Gas Pipelines. Utilizing PySpark on Databricks, BigQuery, and Power BI to identify failure patterns and optimize maintenance scheduling. Developed by Nexus Data Analytics
# 🚀 Nexus: Pipeline de Analítica Predictiva para Integridad de Infraestructura
# 📝 Descripción del Proyecto
Nexus es un pipeline de datos end-to-end diseñado para el monitoreo y mantenimiento predictivo de redes de tuberías industriales. El proyecto resuelve el reto de procesar grandes volúmenes de telemetría en la nube y sincronizar los resultados analíticos con un servidor local para la toma de decisiones en tiempo real.

Este repositorio demuestra la capacidad de implementar arquitecturas híbridas, manejo de Big Data con PySpark y automatización de flujos ETL bajo restricciones de red del mundo real.

# 🏗️ Arquitectura del Sistema
El flujo de datos sigue una arquitectura moderna de Medallion Architecture simplificada:

Ingesta: Datos brutos de sensores (espesor, presión, temperatura) cargados en Databricks File System (DBFS).

Procesamiento (Spark): Limpieza, normalización y feature engineering (Cálculo de Vida Útil Remanente y Stress Index).

Transporte: Creación de un túnel seguro mediante Bore (TCP Tunneling) para saltar firewalls y restricciones de IP dinámica.

Almacenamiento: Carga automatizada en PostgreSQL 18 local mediante SQLAlchemy y Psycopg2.

Visualización: Dashboard interactivo en Tableau Public / Databricks SQL para monitoreo de activos.

# 🛠️ Stack Tecnológico
# Lenguajes: Python (PySpark, Pandas).

Procesamiento: Databricks (Spark Cluster).

Base de Datos: PostgreSQL 18.

Infraestructura: Bore (Networking/Tunneling), JDBC/ODBC.

BI: Tableau Public / Databricks SQL Warehouse.

# 🚀 Desafíos Técnicos y Soluciones
Conectividad Híbrida: Se implementó una solución de túneles reversos para permitir que un entorno Cloud (Databricks) se comunicara de forma segura con una base de datos On-Premise sin necesidad de una VPN costosa.

Optimización de Memoria: Uso de transformaciones nativas de Spark para manejar el procesamiento distribuido, optimizando el paso de DataFrames de Spark a Pandas solo en la etapa final de carga.

Integridad de Datos: Manejo de excepciones de codificación (UTF-8/Latin1) y automatización de esquemas en PostgreSQL.

📈 Resultados e Impacto
Automatización: Reducción del tiempo de procesamiento de reportes de integridad en un 90%.

Mantenimiento Predictivo: Identificación proactiva de tramos de tubería con menos de 5 años de vida útil estimada, permitiendo la planificación de reparaciones antes de fallas críticas.

📋 Cómo Ejecutar este Proyecto
Configuración Local:

Bash
# Levantar el túnel de comunicación
bore local 5433 --to bore.pub
Databricks:

Importar el notebook /notebooks/Nexus_ETL_Pipeline.ipynb.

Configurar el cluster con el runtime 14.3 LTS.

Instalar librerías: psycopg2-binary, sqlalchemy.

Ejecución: Correr todas las celdas para procesar y disparar la sincronización.
### -
# 👤 Autor
## Erlinton Eloy Eligon Pineda
## Junior Data Engineer | IT Specialist

### LinkedIn
### 
### Blog: ¡Datos, luego existo!
