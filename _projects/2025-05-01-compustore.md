---
layout: article
title: "Dashboard de Ventas 2025 – CompuStore"
excerpt: "Dashboard en Power BI diseñado para la Dirección de CompuStore. Ofrece una visión ejecutiva de las ventas anuales, con KPIs clave, evolución mensual con proyección, análisis por categorías de producto y ranking de vendedores."
cover: /assets/images/proyectos/CompuStore/P1.png
readmore: true
---

## Objetivo del proyecto

Proporcionar a la **Dirección de CompuStore** una visión clara y rápida del rendimiento de las ventas durante 2025.  
El objetivo es facilitar la **toma de decisiones estratégicas** mediante indicadores clave, tendencias mensuales y comparativas por categorías y vendedores.  

Este proyecto busca simular un escenario real en el que la gerencia necesita un panel **sencillo pero completo**, que muestre tanto la foto general del negocio como los puntos donde poner mayor atención.

---

## Dashboard interactivo

El dashboard está estructurado para responder a las preguntas más frecuentes de la Dirección:  
- ¿Cuál es el nivel de ventas actual en comparación con meses anteriores?  
- ¿Qué categorías de productos generan mayor facturación?  
- ¿Quiénes son los vendedores con mejor rendimiento?  
- ¿Cómo se proyectan las ventas en los próximos meses si se mantiene la tendencia actual?  

<button onclick="document.getElementById('pbiframe').style.display='block'; this.style.display='none';" style="padding:10px 20px; background:#0078D7; color:white; border:none; border-radius:6px; cursor:pointer; font-size:16px;">
  ▶ Ver dashboard interactivo
</button>

<div id="pbiframe" style="display:none; margin-top:20px; position:relative; padding-bottom:65%; height:0; overflow:hidden;">
  <iframe 
    title="CompuStore" 
    src="https://app.powerbi.com/view?r=eyJrIjoiZWU2ZjM2MmItZWUyYi00NThhLTlhYTAtMmU4ZWNkMWRlODczIiwidCI6IjY4NTE5ZTQ4LTgzZjMtNDM1Zi1hMzhhLTFhN2FhNzdiYTk4NyIsImMiOjh9" 
    frameborder="0" allowFullScreen="true"
    style="position:absolute; top:0; left:0; width:100%; height:100%;">
  </iframe>
</div>

Una vez dentro del informe, la Dirección puede identificar de un vistazo:  
- Los **KPIs globales** del año: ventas totales, número de unidades y ticket medio.  
- La **evolución mensual**, incluyendo una proyección de los próximos meses.  
- El **peso de cada categoría** de producto dentro de las ventas.  
- El **ranking del Top 3 de vendedores**, clave para premiar rendimiento y detectar áreas de mejora.  

---

## Versión móvil

El dashboard también ha sido adaptado a la vista de **teléfono móvil**, lo que garantiza que los directivos puedan consultarlo en cualquier momento, incluso fuera de la oficina.  

En esta versión, la estructura se reorganiza para priorizar la lectura en pantallas pequeñas:  
- **KPIs principales** al inicio.  
- Gráfico de **ventas mensuales con forecast** justo después.  
- Desglose por **categorías** en segundo nivel.  
- Ranking de vendedores y filtros de exploración situados al final.  

![Versión Móvil]({{ '/assets/images/proyectos/CompuStore/movil.gif' | relative_url }})

---

## Dataset y Modelado

Los datos utilizados han sido **simulados con fines educativos**, pero el diseño del modelo reproduce buenas prácticas de proyectos reales:  

- **Tabla de calendario personalizada** con campos calculados (Año, Mes, Nombre de Mes, Trimestre, etc.) para habilitar segmentación temporal.  
- **Medidas en DAX** diseñadas para el análisis ejecutivo: ventas totales, ticket medio, ventas acumuladas por mes, proyección simple de forecast y ranking dinámico de vendedores.  
- Uso de **segmentadores interactivos** (mes, trimestre y categoría de producto) que permiten personalizar la vista de análisis sin perder claridad.  
- **Diseño adaptado a escritorio y móvil**, priorizando la simplicidad visual y el acceso rápido a la información clave.  

Este enfoque garantiza que, aunque los datos sean ficticios, la lógica de análisis y visualización sigue un estándar totalmente aplicable a un entorno profesional.
