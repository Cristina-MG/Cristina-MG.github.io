---
layout: article
title: "Dashboard de Ventas 2025 – CompuStore"
excerpt: "En este proyecto he desarrollado un dashboard en Power BI para el área de dirección de CompuStore. El informe ofrece una visión ejecutiva de las ventas anuales, con KPIs clave, evolución mensual con proyección, análisis por categorías de producto y ranking de los mejores vendedores."
cover: /assets/images/proyectos/CompuStore/P1.PNG
readmore: true
---

## Objetivo del proyecto

Proporcionar a la **Dirección de CompuStore** una visión clara y rápida del rendimiento de las ventas durante 2025.  
El objetivo es facilitar la **toma de decisiones estratégicas** mediante indicadores clave, tendencias mensuales y comparativas por categorías y vendedores.

---

## Panel General: Ventas 2025

La vista principal ofrece un resumen ejecutivo de indicadores:

- **Ventas Totales**, **Unidades Vendidas** y **Ticket Medio** en KPIs destacados.
- Evolución mensual de ventas con proyección (forecast) para los próximos meses.
- Distribución de ventas por categoría de producto (Dispositivos, Componentes, Almacenamiento, Periféricos).
- Ranking con el **Top 3 de vendedores** más relevantes del año.

![Panel General]({{ '/assets/images/proyectos/CompuStore/P1.PNG' | relative_url }})

---

## Versión móvil

El dashboard también ha sido adaptado a la vista de **teléfono móvil**, manteniendo la lógica ejecutiva:  
KPIs principales al inicio, seguido de la evolución mensual, análisis por categoría y ranking de vendedores, con filtros situados al final para facilitar la exploración.

![Versión Móvil]({{ '/assets/images/proyectos/CompuStore/movil.gif' | relative_url }})

---

## Dataset y Modelado

Los datos han sido **simulados con fines educativos**.  
El modelo en Power BI incluye:

- Tabla de calendario personalizada con columnas de año, mes y trimestre.
- Medidas creadas en **DAX** (ventas totales, ticket medio, forecast simple, ranking de vendedores).
- Segmentadores de **mes, trimestre y categoría de producto**.
- Diseño adaptado para **escritorio y móvil**, con un enfoque en claridad y usabilidad.
