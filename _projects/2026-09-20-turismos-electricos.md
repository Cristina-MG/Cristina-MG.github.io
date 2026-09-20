---
layout: article
title: "Mercado Español de Turismos – Análisis y Electrificación"
excerpt: "Análisis en Power BI del mercado español de turismos a partir de más de 6 millones de registros de matriculaciones de la DGT. El proyecto analiza la evolución del mercado, la posición de fabricantes y modelos y el avance de la electrificación entre 2024 y agosto de 2026."
badges: ["📊 Power BI", "🚗 Automoción", "⚡ Electrificación"]
cover: /assets/images/proyectos/mercado-automovilistico-turismos-electricos/home.png
readmore: true
---

## Objetivo del proyecto

Este proyecto analiza la evolución del **mercado español de turismos** a partir de los datos oficiales de matriculaciones publicados por la **Dirección General de Tráfico (DGT)**.

El objetivo no era únicamente visualizar el número de matriculaciones, sino construir un informe que permitiera entender **cómo está evolucionando el mercado, qué fabricantes concentran la mayor cuota y qué papel está desempeñando la electrificación en su transformación**.

El análisis presta especial atención a los turismos electrificados y a las diferentes tecnologías presentes en el mercado —**PHEV, REEV, BEV y FCEV**—, estudiando su evolución, distribución geográfica y los fabricantes y modelos que están impulsando su crecimiento.

El periodo disponible para el análisis comprende desde **enero de 2024 hasta agosto de 2026**.

Los datos de **2023** también forman parte del modelo, aunque no están disponibles como periodo de navegación. Su incorporación permite disponer del histórico necesario para calcular correctamente las **variaciones interanuales de 2024**.

---

## Preguntas de análisis

El dashboard está diseñado para responder a diferentes preguntas de negocio:

- ¿Cómo está evolucionando el mercado español de turismos?
- ¿Qué marcas concentran el mayor volumen de matriculaciones y cuota de mercado?
- ¿Qué fabricantes están creciendo o retrocediendo respecto al mismo periodo del año anterior?
- ¿Qué peso tienen los turismos electrificados dentro del mercado?
- ¿Cómo se distribuye la electrificación entre las diferentes provincias?
- ¿Qué tecnologías eléctricas están ganando mayor presencia?
- ¿Qué fabricantes y modelos están impulsando el crecimiento del mercado electrificado?

El informe permite recorrer estas preguntas desde una **visión general del mercado** hasta llegar al detalle específico de fabricantes, tecnologías y modelos electrificados.

---

## Dashboard interactivo

El informe está publicado en Power BI y puede explorarse directamente desde el portfolio.

El usuario puede seleccionar diferentes periodos, navegar entre las distintas áreas de análisis e interactuar con las visualizaciones.

<button onclick="document.getElementById('pbiframe-turismos').style.display='block'; this.style.display='none';" style="padding:10px 20px; background:#0078D7; color:white; border:none; border-radius:6px; cursor:pointer; font-size:16px;">
  ▶ Ver dashboard interactivo
</button>

<div id="pbiframe-turismos" style="display:none; margin-top:20px; position:relative; padding-bottom:62%; height:0; overflow:hidden;">
  <iframe
    title="Turismos electrificados mercado español"
    src="https://app.powerbi.com/view?r=eyJrIjoiMDU1ZDFjOGYtOTlkMS00YTg1LWE1NmMtY2YwNTgzZWE2NjQ2IiwidCI6IjY4NTE5ZTQ4LTgzZjMtNDM1Zi1hMzhhLTFhN2FhNzdiYTk4NyIsImMiOjh9"
    frameborder="0"
    allowFullScreen="true"
    style="position:absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>

---

## Fuente de datos

La fuente principal del proyecto son los **ficheros de matriculaciones de vehículos publicados por la Dirección General de Tráfico (DGT)**.

El conjunto de datos utilizado supera los **6 millones de registros** y contiene información como:

- Fecha de matriculación.
- Marca del vehículo.
- Modelo.
- Tipo de vehículo.
- Tipo de propulsión.
- Provincia y municipio de matriculación.

A diferencia de un dataset previamente preparado para análisis, los ficheros originales requieren un proceso considerable de **limpieza, transformación y clasificación** antes de poder construir indicadores fiables.

---

## Preparación y transformación de los datos

La preparación de los datos se realizó principalmente mediante **Power Query**, creando un proceso de transformación capaz de integrar los diferentes ficheros de matriculaciones.

Entre las principales transformaciones realizadas se encuentran:

- Tratamiento y conversión de fechas.
- Identificación y filtrado de los registros correspondientes a turismos.
- Decodificación de los códigos de propulsión utilizados por la DGT.
- Clasificación de los vehículos según su tecnología.
- Normalización de fabricantes.
- Limpieza y normalización de modelos.
- Creación de agrupaciones específicas para analizar la electrificación.
- Construcción de una tabla calendario para realizar análisis temporales.

### Normalización de marcas y modelos

Uno de los principales retos del proyecto fue la **normalización de los modelos de vehículos**.

Los datos originales contienen numerosas denominaciones para variantes de un mismo modelo, incluyendo referencias a motorizaciones, acabados y tecnologías como **TDI, TFSI, PHEV, HEV o BEV**.

Esto podía provocar que distintas versiones de un mismo vehículo aparecieran como modelos independientes y dificultar el análisis agregado.

El proceso de limpieza permitió pasar de aproximadamente **24.500 combinaciones originales de marca y modelo a unas 20.500 combinaciones normalizadas**, obteniendo una clasificación más consistente para analizar fabricantes y modelos.

---

## Modelado y análisis con DAX

Una vez preparados los datos, se desarrollaron diferentes medidas en **DAX** para analizar tanto el comportamiento actual del mercado como su evolución temporal.

Entre los principales indicadores utilizados se encuentran:

- Número de matriculaciones.
- Matriculaciones acumuladas **YTD**.
- Matriculaciones del mismo periodo del año anterior.
- Variación interanual.
- Cuota de mercado.
- Cuota de turismos electrificados.
- Evolución mensual y anual.

### Comparaciones entre periodos equivalentes

Uno de los aspectos más importantes del análisis fue garantizar que las comparaciones interanuales fueran realizadas sobre **periodos equivalentes**.

Los datos de 2026 están disponibles hasta agosto. Comparar directamente este periodo con todo el año 2025 produciría una variación engañosa.

Por ello, las medidas YTD utilizan la última fecha disponible como referencia y comparan el resultado con **el mismo periodo del año anterior**.

La inclusión de los datos de 2023 responde al mismo criterio: aunque el usuario navega por el periodo **2024–agosto de 2026**, el histórico de 2023 permite calcular correctamente la variación interanual correspondiente a 2024.

---

## Portada (Home)

El informe comienza con una **portada de navegación** desde la que se puede acceder directamente a las distintas áreas del análisis.

La navegación está estructurada en cinco bloques:

- **Visión General**
- **Mercado**
- **Electrificación**
- **Marcas y Modelos**
- **Conclusiones**

El objetivo es que el usuario pueda recorrer el análisis progresivamente, comenzando por la situación global del mercado y profundizando posteriormente en fabricantes, electrificación y modelos.

![Home]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/home.png' | relative_url }})

---

## Visión General

La primera página proporciona una perspectiva global del **mercado español de turismos**.

Su objetivo es ofrecer el contexto necesario antes de profundizar en fabricantes o electrificación.

Incluye:

- Principales **KPIs de matriculaciones** y evolución respecto al año anterior.
- Distribución de las **matriculaciones por provincia**.
- Evolución anual del mercado.
- Evolución mensual de las matriculaciones.
- Evolución mensual según el **tipo de propulsión**.

La combinación de indicadores temporales y geográficos permite detectar tendencias generales, diferencias territoriales y patrones de estacionalidad.

![Visión General]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P1.PNG' | relative_url }})

---

## Mercado

Esta sección analiza la **posición de los fabricantes dentro del mercado español** combinando volumen de matriculaciones, cuota de mercado y evolución interanual.

Incluye:

- Ranking de las **10 marcas con mayor número de matriculaciones**.
- Cuota de mercado de cada fabricante.
- Variación respecto al mismo periodo del año anterior.
- Evolución mensual de las **cinco marcas con mayor volumen de matriculaciones**.
- Análisis conjunto de **variación interanual y cuota de mercado** para las principales marcas.

Uno de los elementos centrales de esta página es el gráfico de dispersión, que permite analizar simultáneamente dos dimensiones.

La posición vertical representa la **cuota de mercado**, mientras que el eje horizontal muestra la **variación interanual de las matriculaciones**.

Esta representación permite diferenciar entre fabricantes que mantienen una posición consolidada, marcas que están perdiendo matriculaciones y competidores con menor cuota pero elevados ritmos de crecimiento.

![Mercado]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P2.PNG' | relative_url }})

---

## Electrificación

Esta página se centra específicamente en la evolución de los **turismos electrificados**.

En lugar de considerar la electrificación como una única categoría, el análisis diferencia entre las principales tecnologías presentes en los datos:

- **PHEV** – Híbrido enchufable.
- **REEV** – Eléctrico de autonomía extendida.
- **BEV** – Eléctrico de batería.
- **FCEV** – Eléctrico de pila de combustible.

La página incluye:

- Matriculaciones por tecnología.
- **Cuota de electrificación por provincia**.
- Distribución de las matriculaciones de turismos electrificados.
- Evolución mensual según el tipo de tecnología eléctrica.

Este enfoque permite analizar no solo **cuánto está creciendo la electrificación**, sino también cómo está cambiando su composición interna y qué tecnologías están impulsando ese crecimiento.

El análisis territorial permite además comprobar que la penetración de los vehículos electrificados **no es homogénea en todo el país**, existiendo diferencias entre provincias.

![Electrificación]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P3.PNG' | relative_url }})

---

## Marcas y Modelos Electrificados

Una vez analizada la evolución global de la electrificación, esta sección profundiza en los **fabricantes y modelos que están detrás de ese crecimiento**.

El objetivo es pasar de una visión agregada del mercado electrificado a identificar los vehículos y fabricantes que están contribuyendo a su expansión.

El análisis permite estudiar:

- Principales fabricantes de turismos electrificados.
- Posición de las marcas dentro del segmento.
- Evolución de sus matriculaciones.
- Modelos con mayor presencia.
- Distribución de las matriculaciones entre las diferentes tecnologías.

Este nivel de detalle permite observar cómo el crecimiento de la electrificación **no se distribuye de forma uniforme entre todos los fabricantes** y facilita detectar tanto marcas consolidadas como nuevos competidores que están aumentando rápidamente su presencia en el mercado español.

![Marcas y Modelos Electrificados]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P4.PNG' | relative_url }})

---

## Conclusiones

La última página del informe transforma las visualizaciones anteriores en una **síntesis de los principales hallazgos del análisis**.

El objetivo es que el usuario pueda finalizar el recorrido con una visión clara de las tendencias más relevantes detectadas en los datos, relacionando la evolución general del mercado con el avance de la electrificación y el comportamiento de fabricantes y modelos.

Entre las tendencias observadas destacan:

- El mercado español de turismos presenta una evolución positiva en el periodo analizado.
- El segmento electrificado muestra un crecimiento considerablemente superior al conjunto del mercado.
- Las matriculaciones presentan **patrones de estacionalidad**, con diferencias relevantes entre meses.
- La penetración de la electrificación presenta diferencias territoriales entre provincias.
- Las distintas tecnologías electrificadas no evolucionan al mismo ritmo, modificando progresivamente la composición del segmento.
- El análisis por fabricantes permite detectar tanto marcas consolidadas como nuevos competidores con elevados ritmos de crecimiento.

La página funciona así como un **resumen ejecutivo del proyecto**, trasladando los resultados del análisis a conclusiones fácilmente interpretables.

![Conclusiones]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P5.PNG' | relative_url }})

---

## Ayuda integrada en el informe

Además del análisis de datos, uno de los objetivos del proyecto fue facilitar la **interpretación y navegación del dashboard**.

Para ello se desarrolló un sistema de **ayuda contextual integrado en las propias páginas del informe**.

Al activarlo, se muestra una capa explicativa sobre el dashboard que identifica mediante llamadas numeradas los principales elementos de cada página.

La ayuda explica, entre otros aspectos:

- Cómo utilizar el **selector de periodo**.
- Qué información contiene cada ranking.
- Cómo interpretar las evoluciones mensuales.
- Qué representan determinadas visualizaciones.
- Cómo analizar conjuntamente métricas como **cuota de mercado y variación interanual**.

De esta forma, el usuario mantiene visible el contexto de la página mientras recibe las indicaciones necesarias para interpretar cada elemento.

El objetivo es reducir la curva de aprendizaje y conseguir que el informe pueda ser utilizado por personas que **no hayan participado en su desarrollo ni conozcan previamente el modelo de datos**.

![Ayuda contextual]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/AYUDA.PNG' | relative_url }})

---

## Principales retos del proyecto

Este proyecto ha requerido trabajar con un nivel de complejidad superior al de un dashboard construido sobre un dataset previamente preparado.

Los principales retos fueron:

- **Volumen de datos** → tratamiento de más de 6 millones de registros procedentes de diferentes ficheros.
- **Calidad del dato** → limpieza y normalización de miles de denominaciones de marcas y modelos.
- **Clasificación** → transformación de los códigos originales de la DGT en categorías comprensibles para el análisis.
- **Análisis temporal** → construcción de comparaciones YTD entre periodos equivalentes.
- **Histórico auxiliar** → incorporación de 2023 para calcular las variaciones interanuales de 2024 sin necesidad de mostrar ese año como periodo de navegación.
- **Electrificación** → creación de una clasificación que permita analizar por separado las distintas tecnologías.
- **Diseño** → organización de una cantidad elevada de información manteniendo una estructura visual consistente.
- **Usabilidad** → incorporación de navegación y ayuda contextual para facilitar la interpretación del informe.

El resultado combina **preparación de datos, modelado, análisis, visualización y experiencia de usuario**, buscando que cada decisión de diseño responda a una necesidad analítica concreta.

---

## Herramientas utilizadas

- **Power BI** → desarrollo del dashboard y visualización de datos.
- **Power Query** → importación, limpieza y transformación de los datos.
- **DAX** → creación de KPIs, cálculos temporales, cuotas y variaciones interanuales.
- **Python** → apoyo en elementos específicos del proyecto y visualización.
- **Figma** → diseño de elementos gráficos y definición de la interfaz visual del informe.

---

## Resultado

El proyecto transforma varios millones de registros públicos de matriculaciones en una herramienta de análisis que permite estudiar el mercado español de turismos desde diferentes niveles: **evolución general, fabricantes, territorio, tecnologías, electrificación y modelos**.

Más allá de la construcción del dashboard, el proyecto integra diferentes fases habituales en un proceso de análisis de datos: desde la **preparación y normalización de la información** hasta el desarrollo de métricas, análisis de tendencias y comunicación visual de resultados.

El resultado es un informe diseñado no solo para mostrar datos, sino para facilitar su **exploración, interpretación y comprensión**.