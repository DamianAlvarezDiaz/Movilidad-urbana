Proyecto 5: Movilidad urbana y productividad económica en ciudades de LATAM
Introducción
Eres analista de datos en el Latin American Development Bank.

Tu equipo debe entregar un reporte para entender cómo la movilidad urbana (niveles de congestión, tiempos de viaje, retrasos) se relaciona con la productividad económica (PIB per cápita, desempleo) en las principales ciudades latinoamericanas.

El objetivo del banco es identificar en qué ciudades invertir en infraestructura de transporte para aumentar la productividad y el bienestar de la población.

Para ello, usarás dos fuentes reales de datos:

Movilidad urbana: TomTom Traffic Index (datos de tráfico en tiempo real).
Economía urbana: OECD Cities (PIB per cápita, desempleo y población).
Tu misión será limpiar, unir y analizar ambas bases para obtener información útil para la toma de decisiones.

💡 Preguntas del negocio:

¿Qué ciudades de América Latina presentan alta congestión y baja productividad económica?
¿Cuáles muestran los mejores indicadores combinados (movilidad eficiente y economía fuerte)?
¿Qué variables parecen tener una relación más fuerte con el desarrollo urbano?
🎯 Objetivos de aprendizaje del proyecto
Al finalizar este proyecto, podrás:

Crear un dataset único y limpio a partir de dos fuentes diferentes.
Aplicar limpieza, estandarización y validación de tipos de datos.
Filtrar y enfocar el análisis en ciudades latinoamericanas.
Calcular indicadores agregados (por ciudad–año).
Realizar análisis exploratorios y visuales.
Documentar todos los pasos en Jupyter Notebook, exportar un dataset final y listo para análisis.
🛠️ Herramientas de la lección
Jupyter Notebook
Python: pandas, numpy, seaborn, matplotlib
Dataset del proyecto
En este proyecto trabajarás con dos fuentes principales de información:

tomtom_traffic.csv : Datos sobre congestión vehicular y condiciones de tráfico en ciudades del mundo. Puedes descargarlo aquí.
oecd_city_economy.csv : Indicadores económicos y ambientales por ciudad, recopilados por la OECD (Organización para la Cooperación y el Desarrollo Económico). Puedes descargarlo aquí.
Ambas tablas se complementan para entender cómo la eficiencia del tráfico urbano se relaciona con el desempeño económico en ciudades latinoamericanas.

Dataset 1: tomtom_traffic.csv
Registra información sobre niveles de tráfico y congestión en tiempo real en distintas ciudades monitoreadas por TomTom, una empresa global de geolocalización.

Cada registro corresponde a una actualización puntual del estado del tráfico en una ciudad.

Columna	Tipo de Dato (Ejemplo)	Descripción
Country	STRING (ej. "ARE")	Código ISO-3 del país (ARE = Emiratos Árabes Unidos).
City	STRING (ej. "abu-dhabi")	Nombre estandarizado de la ciudad o área metropolitana monitoreada.
UpdateTimeUTC	DATETIME (ej. "2025-01-13 04:01:30.001")	Fecha y hora (UTC) de la actualización de tráfico.
JamsDelay	FLOAT (ej. 650.7)	Retraso total (en minutos) provocado por la congestión en todas las vías monitoreadas.
TrafficIndexLive	FLOAT (ej. 36.0)	Índice de tráfico actual (0–100). Valores mayores indican mayor congestión.
JamsLengthInKms	FLOAT (ej. 109.1)	Longitud total (en km) de los embotellamientos activos.
JamsCount	INTEGER (ej. 162)	Número total de embotellamientos activos en el momento del registro.
TrafficIndexWeekAgo	FLOAT (ej. 30.0)	Índice de tráfico registrado exactamente una semana antes.
UpdateTimeUTCWeekAgo	DATETIME (ej. "2025-01-06 04:01:30.000")	Fecha de referencia de la medición anterior (una semana antes).
TravelTimeLivePer10KmsMins	FLOAT (ej. 11.614767)	Tiempo medio actual (en minutos) necesario para recorrer 10 km bajo condiciones reales de tráfico.
TravelTimeHistoricPer10KmsMins	FLOAT (ej. 10.26533)	Tiempo medio histórico (en minutos) para recorrer 10 km en condiciones normales (sin congestión).
MinsDelay	FLOAT (ej. 1.349437)	Diferencia entre el tiempo actual y el histórico. Representa los minutos de retraso promedio por cada 10 km debido a la congestión.
Dataset 2: oecd_city_economy.csv
Contiene indicadores anuales sobre economía urbana, empleo, contaminación y población recopilados por la OECD (Organización para la Cooperación y el Desarrollo Económicos).

Cada registro representa una ciudad en un año específico, lo que permite comparar niveles de productividad y desarrollo urbano entre países.

Columna	Tipo de Dato (Ejemplo)	Descripción
Year	INTEGER (ej. 2023)	Año del registro del indicador económico.
City	STRING (ej. "buenos-aires")	Nombre de la ciudad o área metropolitana.
Country	STRING (ej. "Argentina")	País al que pertenece la ciudad.
City GDP/capita	FLOAT (ej. 15782.00)	Producto Interno Bruto per cápita en dólares (USD). Refleja el nivel de productividad económica por habitante.
Unemployment %	FLOAT (ej. 6.2)	Porcentaje de desempleo de la población económicamente activa.
PM2.5 (μg/m³)	FLOAT (ej. 15.2)	Concentración promedio anual de partículas finas PM2.5, indicador de contaminación del aire.
Population (M)	FLOAT (ej. 15.30)	Población total de la ciudad, expresada en millones de habitantes.
📝 Plan de acción (pensamiento programatico)
Contexto del negocio
Tu misión será construir una tabla unificada que combine variables de movilidad urbana (TomTom) con variables económicas (OECD) para ciudades de América Latina en 2024.

El objetivo es generar una base limpia, estandarizada y lista para futuros análisis sobre cómo la movilidad urbana puede influir en la productividad económica.

Tu trabajo culminará con la exportación del dataset final completamente depurado y el notebook de Jupyter con todo el proceso documentado.

🔄 Flujo general del proyecto
Paso	Acción	Resultado esperado
1	Cargar y explorar los datasets	Identificar las columnas, tipos de datos, y comprender la estructura general de los archivos.
2	Limpiar y corregir formatos	Estandarizar nombres de columnas, y corregir tipos de datos
3	Extraer el año y filtrar año 2024	Trabajar solo con el período más reciente y relevante, el año 2024.
4	Calcular promedios de tráfico por ciudad	Obtener una vista consolidada de la movilidad urbana.
5	Combinar datasets de tráfico y economía	Unir los dos DataFrames en un solo dataset con información unificada por ciudad.
6	Visualizar relaciones entre variables	Generar gráficos para explorar patrones entre tráfico y economía.
7	Elaborar informe e incluir reflexión final	Redactar un informe ejecutivo con hallazgos, implicaciones y reflexiones personales sobre la relación entre economía y movilidad.
⚙️ Detalles clave
Tabla principal: la de tráfico (tomtom_traffic.csv), que será agregada por ciudad y año.
Cardinalidad: muchos registros de tráfico por ciudad, se resumen antes de unir.
Estandarización: los nombres de ciudades y países deben coincidir entre fuentes.
Resultado final: una tabla con una fila por ciudad y año (2024), lista para análisis o visualización posterior.
📒 Sigue el flujo de trabajo descrito en cada celda del Jupyter Notebook, allí encontrarás instrucciones paso a paso, pre-código y notas que te servirán de guía para completar con éxito el proyecto.

Exportar dataset
Ejecuta la celda que genera el CSV.
Haz clic en el logo de la carpeta 📁, que aparece en la barra central de este espacio.
Observa que este espacio es donde esta guardado tu Notebook y el archivo que se generó.
Descarga el CSV: da clic derecho sobre el nombre del CSV y después en Download.
