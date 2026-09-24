---
layout: article
title: "Mercado Español de Turismos – Análisis y Electrificación"
excerpt: "Análisis en Power BI del mercado español de turismos a partir de más de 6 millones de registros de matriculaciones de la DGT. El proyecto analiza la evolución del mercado, la posición de las principales marcas y modelos y el avance de la electrificación entre 2024 y agosto de 2026."
badges: ["📊 Power BI", "🚗 Automoción", "⚡ Electrificación", "⭐ Galería Power BI"]
cover: /assets/images/proyectos/mercado-automovilistico-turismos-electricos/home.png
readmore: true
---

## Objetivo del proyecto

Este proyecto analiza la evolución del **mercado español de turismos** a partir de los datos oficiales de matriculaciones publicados por la **Dirección General de Tráfico (DGT)**.

El objetivo no era únicamente visualizar el número de matriculaciones, sino construir un informe que permitiera entender **cómo está evolucionando el mercado, qué marcas concentran la mayor cuota, cuáles están creciendo o retrocediendo y qué papel está desempeñando la electrificación en su transformación**.

El análisis presta especial atención a los turismos electrificados y a las diferentes tecnologías presentes en los datos —**PHEV, REEV, BEV y FCEV**—, estudiando su evolución, distribución geográfica y las marcas y modelos que están impulsando su crecimiento.

El periodo disponible para el análisis comprende desde **enero de 2024 hasta agosto de 2026**.

Los datos de **2023** también forman parte del modelo, aunque no están disponibles como periodo de navegación. Su incorporación permite disponer del histórico necesario para calcular correctamente las **variaciones interanuales de 2024**.

---

## Preguntas de análisis

El dashboard está diseñado para responder a diferentes preguntas de negocio:

- ¿Cómo está evolucionando el mercado español de turismos?
- ¿Qué marcas concentran el mayor volumen de matriculaciones y cuota de mercado?
- ¿Qué marcas están creciendo o retrocediendo respecto al mismo periodo del año anterior?
- ¿Qué peso tienen los turismos electrificados dentro del mercado?
- ¿Cómo se distribuye la electrificación entre las diferentes provincias?
- ¿Cómo está evolucionando el reparto entre PHEV, REEV, BEV y FCEV?
- ¿Qué marcas concentran una mayor cuota dentro del mercado electrificado?
- ¿Qué modelos están registrando un mayor volumen de matriculaciones electrificadas?

El informe permite recorrer estas preguntas desde una **visión general del mercado** hasta llegar al detalle específico de marcas, tecnologías y modelos electrificados.

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
    src="https://app.powerbi.com/view?r=eyJrIjoiMDU1ZDFjOGYtOTlkMS00YTg1LWE1NmMtY2YwNTgzZWE2NjQ2IiwidCI6IjY4NTE5ZTQ4LTgzZjMtNDM1Zi1hMzhhLTFhN2FhNzdiYTk4NyIsImMiOjh9&pageName=f5e73aa00910033b019c"
    frameborder="0"
    allowFullScreen="true"
    style="position:absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>

---

## Fuente de datos

La fuente principal del proyecto son los **ficheros de matriculaciones de vehículos publicados por la Dirección General de Tráfico (DGT)**.

El conjunto de datos utilizado supera los **6 millones de registros** e incluye información como:

- Fecha de matriculación.
- Marca del vehículo.
- Modelo.
- Tipo de vehículo.
- Tipo de propulsión.
- Provincia y municipio de matriculación.

A diferencia de un dataset previamente preparado para análisis, los ficheros originales requieren un proceso considerable de **limpieza, transformación y clasificación** antes de poder construir indicadores consistentes para el análisis.

Los resultados del proyecto proceden de una **explotación propia de los microdatos de la DGT**, por lo que pueden existir pequeñas diferencias respecto a estadísticas sectoriales publicadas por otras fuentes debido a diferencias en los criterios de clasificación y tratamiento de los registros.

---

## Preparación y transformación de los datos

La preparación de los datos se realizó principalmente mediante **Power Query**, creando un proceso de transformación capaz de integrar los diferentes ficheros de matriculaciones.

Entre las principales transformaciones realizadas se encuentran:

- Tratamiento y conversión de fechas.
- Identificación y filtrado de los registros correspondientes a turismos.
- Decodificación de los códigos de propulsión utilizados por la DGT.
- Clasificación de los vehículos según su tecnología.
- Estandarización de marcas.
- Limpieza y normalización de modelos.
- Creación de agrupaciones específicas para analizar la electrificación.
- Preparación de las dimensiones geográficas necesarias para el análisis territorial.
- Construcción de una tabla calendario para realizar análisis temporales.

### Normalización de marcas y modelos

Uno de los principales retos del proyecto fue la **normalización de los modelos de vehículos**.

Los datos originales contienen numerosas denominaciones para variantes de un mismo modelo, incluyendo referencias a motorizaciones, acabados y tecnologías como **TDI, TFSI, PHEV, HEV o BEV**.

Esto podía provocar que distintas versiones de un mismo vehículo aparecieran como modelos independientes y dificultar el análisis agregado.

El proceso de limpieza permitió pasar de aproximadamente **24.500 combinaciones originales de marca y modelo a unas 20.500 combinaciones normalizadas**, obteniendo una clasificación más consistente para analizar marcas y modelos.

---

## Modelado y análisis con DAX

Una vez preparados los datos, se desarrollaron diferentes medidas en **DAX** para analizar tanto el comportamiento actual del mercado como su evolución temporal.

Entre los principales indicadores utilizados se encuentran:

- Número de matriculaciones.
- Matriculaciones acumuladas **YTD**.
- Matriculaciones del mismo periodo del año anterior.
- Variación interanual.
- Cuota de mercado.
- Cuota de mercado dentro del segmento electrificado.
- Cuota de electrificación.
- Evolución mensual y anual.

### Comparaciones entre periodos equivalentes

Uno de los aspectos más importantes del análisis fue garantizar que las comparaciones interanuales se realizaran sobre **periodos equivalentes**.

Los datos de 2026 están disponibles hasta agosto. Comparar directamente este periodo con todo el año 2025 produciría una variación engañosa.

Por ello, las medidas YTD utilizan la última fecha disponible como referencia y comparan el resultado con **el mismo periodo del año anterior**.

De esta forma, para 2026 los indicadores acumulados de enero a agosto se comparan con **enero-agosto de 2025**, mientras que los años históricos completos pueden analizarse utilizando su periodo correspondiente.

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

El objetivo es que el usuario pueda recorrer el análisis progresivamente, comenzando por la situación global del mercado y profundizando posteriormente en marcas, electrificación y modelos.

![Home]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/home.png' | relative_url }})

---

## Visión General

La primera página proporciona una perspectiva global del **mercado español de turismos**.

Su objetivo es ofrecer el contexto necesario antes de profundizar en marcas o electrificación.

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

Esta sección analiza la **posición de las marcas dentro del mercado español** combinando volumen de matriculaciones, cuota de mercado y evolución interanual.

Incluye:

- Ranking de las **10 marcas con mayor número de matriculaciones**.
- Cuota de mercado de cada marca.
- Variación respecto al mismo periodo del año anterior.
- Evolución mensual de las **cinco marcas con mayor volumen de matriculaciones**.
- Análisis conjunto de **variación interanual y cuota de mercado** para las principales marcas.

Uno de los elementos centrales de esta página es el gráfico de dispersión, que permite analizar simultáneamente dos dimensiones.

La posición vertical representa la **cuota de mercado**, mientras que el eje horizontal muestra la **variación interanual de las matriculaciones**.

Esta representación permite contextualizar la posición de las principales marcas, diferenciando entre aquellas con una presencia consolidada, las que están perdiendo matriculaciones y aquellas que presentan ritmos elevados de crecimiento.

![Mercado]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P2.PNG' | relative_url }})

---

## Electrificación

Esta página se centra específicamente en la evolución de los **turismos electrificados**.

En lugar de considerar la electrificación como una única categoría, el análisis diferencia entre las tecnologías presentes en los datos:

- **PHEV** – Híbrido enchufable.
- **REEV** – Eléctrico de autonomía extendida.
- **BEV** – Eléctrico de batería.
- **FCEV** – Eléctrico de pila de combustible.

La página incluye:

- Matriculaciones por tecnología.
- Comparación con el mismo periodo del año anterior.
- **Cuota de electrificación por provincia**.
- Distribución de las matriculaciones de turismos electrificados.
- Evolución mensual según el tipo de tecnología eléctrica.

Este enfoque permite analizar no solo **cuánto está creciendo la electrificación**, sino también cómo está cambiando su composición interna y qué tecnologías están impulsando ese crecimiento.

El análisis territorial permite además observar que la penetración de los vehículos electrificados **no es homogénea en todo el país**, existiendo diferencias relevantes entre provincias.

![Electrificación]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P3.PNG' | relative_url }})

---

## Marcas y Modelos Electrificados

Una vez analizada la evolución global de la electrificación, esta sección profundiza en las **marcas y modelos que están detrás de las matriculaciones electrificadas**.

El objetivo es pasar de una visión agregada del segmento a identificar qué marcas concentran una mayor presencia, cómo están evolucionando y qué modelos destacan por volumen de matriculaciones.

El análisis incluye:

- **Top 10 de marcas por matriculaciones de turismos electrificados**.
- **Cuota de cada marca dentro del mercado electrificado**.
- **Variación interanual** de las matriculaciones electrificadas por marca.
- Distribución de matriculaciones por **tecnología y marca**.
- **Top 5 de modelos electrificados** con mayor número de matriculaciones.
- Gráfico de dispersión que combina **cuota dentro del mercado electrificado y variación interanual** para contextualizar la posición de las principales marcas.

Este nivel de detalle permite observar cómo el crecimiento de la electrificación **no se distribuye de forma uniforme entre todas las marcas** y facilita identificar tanto actores consolidados como marcas que están aumentando rápidamente su presencia en el mercado español.

![Marcas y Modelos Electrificados]({{ '/assets/images/proyectos/mercado-automovilistico-turismos-electricos/P4.PNG' | relative_url }})

---

## Conclusiones

La última página del informe transforma las visualizaciones anteriores en una **síntesis de los principales hallazgos del análisis**.

Para el periodo **enero-agosto de 2026**, el análisis permite destacar cinco conclusiones principales:

### 1. La electrificación crece por encima del conjunto del mercado

Entre enero y agosto de 2026, las matriculaciones de turismos aumentan un **6,8 % interanual**, mientras que las matriculaciones de turismos electrificados crecen un **36,3 %**.

Este crecimiento eleva la cuota de electrificación desde aproximadamente el **17,6 % hasta el 22,5 %**, un incremento de alrededor de **4,9 puntos porcentuales**.

### 2. El PHEV pasa a liderar el reparto de los electrificados

En 2024, los **BEV** representaban aproximadamente el **53,6 %** de las matriculaciones electrificadas analizadas.

En 2025, el **PHEV** pasa a concentrar el mayor volumen y en enero-agosto de 2026 mantiene el liderazgo, con aproximadamente un **53,3 %**, frente al **46,0 %** correspondiente a los BEV.

La evolución muestra un cambio en la composición del segmento electrificado, con un mayor peso de los híbridos enchufables.

### 3. Toyota lidera el mercado general

En enero-agosto de 2026, **Toyota** ocupa la primera posición por matriculaciones de turismos dentro de los datos analizados.

Su evolución permite observar cómo el liderazgo del mercado no depende únicamente del crecimiento interanual, sino también del volumen y de la posición acumulada de cada marca.

### 4. BYD destaca dentro del mercado electrificado

**BYD** lidera las matriculaciones de turismos electrificados en enero-agosto de 2026, con **29.938 matriculaciones** y aproximadamente un **16,15 % de cuota dentro del mercado electrificado** analizado.

La marca registra además un crecimiento aproximado del **111 % interanual**.

A nivel de modelos, **ATTO 2 y SEAL U** se sitúan entre los tres modelos electrificados con mayor número de matriculaciones, reforzando la presencia de la marca dentro del segmento.

### 5. La electrificación presenta diferencias territoriales

La cuota de electrificación aumenta en la mayoría de los territorios analizados en 2026, aunque su penetración presenta diferencias relevantes entre provincias.

**Navarra** destaca con la mayor cuota de electrificación, situada en torno al **42 % de las matriculaciones de turismos nuevos** analizadas.

El análisis territorial muestra además que un mayor volumen absoluto de matriculaciones no implica necesariamente una mayor penetración relativa de la electrificación.

La página funciona así como un **resumen ejecutivo del proyecto**, trasladando los resultados del análisis a conclusiones fácilmente interpretables y conectando la evolución general del mercado con las tecnologías, las marcas, los modelos y las diferencias territoriales.

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
- **Electrificación** → creación de una clasificación que permita analizar por separado PHEV, REEV, BEV y FCEV.
- **Análisis de cuota** → diferenciación entre la cuota del mercado general, la cuota de electrificación y la cuota de cada marca dentro del mercado electrificado.
- **Diseño** → organización de una cantidad elevada de información manteniendo una estructura visual consistente.
- **Usabilidad** → incorporación de navegación y ayuda contextual para facilitar la interpretación del informe.

El resultado combina **preparación de datos, modelado, análisis, visualización y experiencia de usuario**, buscando que cada decisión de diseño responda a una necesidad analítica concreta.

---

## Herramientas utilizadas

- **Power BI** → desarrollo del dashboard y visualización de datos.
- **Power Query** → importación, limpieza y transformación de los datos.
- **DAX** → creación de KPIs, cálculos temporales, cuotas y variaciones interanuales.
- **Figma** → diseño de elementos gráficos y definición de la interfaz visual del informe.

---

## Publicación

Este dashboard ha sido publicado en la [**Power BI Data Stories Gallery**](https://community.fabric.microsoft.com/discussions/datastoriesgallery/mercado-espa%C3%B1ol-de-turismos-evoluci%C3%B3n-y-electrificaci%C3%B3n/5367981), la galería oficial de la comunidad de Microsoft Power BI.

También puedes [**abrir el dashboard directamente en Power BI**](https://app.powerbi.com/view?r=eyJrIjoiMDU1ZDFjOGYtOTlkMS00YTg1LWE1NmMtY2YwNTgzZWE2NjQ2IiwidCI6IjY4NTE5ZTQ4LTgzZjMtNDM1Zi1hMzhhLTFhN2FhNzdiYTk4NyIsImMiOjh9&pageName=f5e73aa00910033b019c).

---

## Resultado

El proyecto transforma más de **6 millones de registros públicos de matriculaciones** en una herramienta de análisis que permite estudiar el mercado español de turismos desde diferentes niveles: **evolución general, marcas, territorio, tecnologías, electrificación y modelos**.

Más allá de la construcción del dashboard, el proyecto integra diferentes fases habituales en un proceso de análisis de datos: desde la **preparación, clasificación y normalización de la información** hasta el desarrollo de métricas, comparaciones temporales, análisis de tendencias y comunicación visual de resultados.

El resultado es un informe diseñado no solo para mostrar datos, sino para facilitar su **exploración, interpretación y comprensión**, combinando análisis de mercado, modelado de datos, visualización y una experiencia de navegación orientada al usuario.