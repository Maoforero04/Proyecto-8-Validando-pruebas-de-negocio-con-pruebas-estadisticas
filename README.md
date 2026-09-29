# Proyecto-8-Validando-pruebas-de-negocio-con-pruebas-estadisticas
A/B Test: Landing Page Experiment 🧪

🎯 Objetivo del proyecto

Evaluar un experimento A/B realizado sobre una página de inicio (landing page), comparando dos versiones (A y B), con el fin de determinar cuál genera mayor conversión y mayor valor económico para el negocio, y así apoyar una decisión de negocio basada en datos.

El análisis busca responder preguntas clave como:
- ¿Qué versión de la página convierte más usuarios?
- ¿Qué versión genera mayor gasto promedio por cliente?
- ¿Existen diferencias en la efectividad de los distintos canales de tráfico?
- ¿El tipo de usuario (nuevo vs. recurrente) influye en la conversión?

📊 Dataset utilizado

landing_experiment.csv — 40,000 registros de usuarios expuestos a la página A o B durante un periodo de 28 días (enero 2026).
- Columna	- Tipo de dato	- Descripción
- user_id -	Categórica (UUID) -	Identificador único del usuario
- date	- Fecha	- Fecha en la que el usuario fue expuesto a la página
- landing	- Categórica	- Versión de la página mostrada (A, B)
- region	- Categórica	- Región geográfica del usuario
- dispositivo	- Categórica -	Tipo de dispositivo utilizado (Mobile, Desktop)
- traffic_source	- Categórica	- Canal por el que llegó el usuario (Organic, Ads, Email, Referral)
- user_type -	Categórica	- Tipo de usuario según historial previo (Nuevo, Recurrente).
- converted -	Binaria (0/1)	- Indica si el usuario realizó una conversión.
- gasto -	Numérica (float)	- Monto gastado por el usuario (0 si no convirtió).

🧭 Etapas del análisis
1. Carga y validación de datos — revisión de nulos, tipos de dato, balance de grupos (A/B), consistencia de categorías y valores atípicos.
2. Comparación de gasto promedio (A vs. B) — prueba t (Welch/varianzas iguales, según corresponda) sobre usuarios convertidos, con verificación previa del supuesto de homogeneidad de varianzas.
3. Comparación de tasa de conversión (A vs. B) — prueba z de dos proporciones.
4. Relación entre fuente de tráfico y conversión — prueba de chi-cuadrado de independencia, con verificación del supuesto de frecuencias esperadas.
5. Relación entre tipo de usuario y conversión — prueba de chi-cuadrado de independencia, con verificación del supuesto de frecuencias esperadas.
6. Visualización de resultados — gráficos de barras agrupadas (volumen absoluto) y apiladas (proporciones) para traffic_source y user_type.
7. Insight ejecutivo — conclusiones y recomendaciones de negocio accionables, basadas en los resultados de todas las pruebas anteriores.

▶️ Cómo ejecutar el notebook
- Descarga o clona este repositorio.
- Abre el notebook (.ipynb) en Google Colab:
- Ve a colab.research.google.com
- Selecciona Archivo > Subir notebook y carga el archivo .ipynb, o ábrelo directamente desde GitHub con Archivo > Abrir notebook > GitHub, pegando la URL del repositorio.
- Sube el archivo landing_experiment.csv a la sesión de Colab (panel izquierdo > ícono de carpeta > subir archivo), o móntalo desde Google Drive si prefieres persistencia entre sesiones.
- Ejecuta las celdas en orden (Entorno de ejecución > Ejecutar todas).
