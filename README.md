# Análisis de Negocios de RappiPlus

## Objetivo / Pregunta de negocio
¿RappiPlus es rentable, dónde pierde usuarios en el proceso de compra y qué tan bien retiene a sus clientes? El objetivo fue evaluar el desempeño integral del servicio para apoyar decisiones de negocio basadas en datos.

## Datos
Se trabajó con 3 datasets relacionados con la operación de RappiPlus:

| Archivo | Contenido |
|---|---|
| `orders_clean` | Pedidos: id_pedido, cantidad, categoría, revenue, costo, profit, país |
| `catalog_clean` | Catálogo de productos: categoría, costo unitario, proveedor |
| `marketing_clean` | Gasto de marketing por canal y campaña |

Datos correspondientes a 25,000+ pedidos a lo largo de 6 meses (enero-junio).

## Proceso
1. **Carga y limpieza:** unión de los 3 datasets con Python (Pandas), validación de tipos de datos y consistencia entre tablas.
2. **KPIs de rentabilidad:** cálculo de revenue, costos y gasto de marketing para obtener el margen de ganancia real del negocio.
3. **Funnel de conversión:** construcción del embudo completo (first_visit → view_item → add_to_cart → begin_checkout → add_payment_info → purchase) usando SQL, midiendo la tasa de conversión entre cada etapa.
4. **Retención por cohortes:** agrupación de usuarios por mes de primera compra y seguimiento de su actividad en semanas posteriores.
5. **Test A/B:** evaluación de un cambio de UI en el checkout con prueba estadística chi-cuadrado para validar significancia.
6. **Visualización:** construcción de un dashboard ejecutivo en Power BI con las métricas clave.

## Entregable
- Notebook completo: [`S12 Estudiante_Proyecto_Final (2).ipynb`](./S12%20Estudiante_Proyecto_Final%20(2).ipynb)
- Dashboard interactivo: [`Panel de control de RappiPlus_Stiven.pbix`](./Panel%20de%20control%20de%20RappiPlus_Stiven.pbix)

## Insights
- **Rentabilidad:** Ingresos de $51.8M, costo de $43M y $2.7M en marketing → margen de ganancia de ~12%.
- **Embudo de conversión:** De 7,796 usuarios en la primera visita a 6,240 compras. La mayor fuga ocurre entre "checkout" y "pago" (~12 pp de caída).
- **Retención por cohortes:** ~42% de los usuarios siguen activos en la semana 1, de forma consistente en los 4 meses analizados.
- **Prueba A/B:** Se probó un cambio de UI en el checkout (control 15.69% vs tratamiento 16.29% de conversión). Con una prueba chi-cuadrado (p=0.43), el cambio no mostró impacto estadísticamente significativo.

## Recomendación / Siguiente paso
Si esto fuera un caso de negocio real, priorizaría rediseñar el paso de "pago" dentro del checkout, ya que ahí se concentra la mayor fuga de usuarios (–12 pp) — antes de invertir en más tráfico o marketing, conviene arreglar esa fuga porque tiene mayor impacto inmediato en ingresos. Además, dado que el test A/B no fue significativo, recomendaría repetirlo con una muestra más grande o probar un cambio más audaz en el flujo de pago, en lugar de descartar la hipótesis por completo.

## Panel de control en Power BI
![Overview Ejecutivo](dashboard-overview.png.png)
![Detalle](dashboard-detalle.png.png)

## Cómo ejecutar
Requisitos: Python 3.x, pandas, numpy, scipy, matplotlib.
Abrir `S12 Estudiante_Proyecto_Final (2).ipynb` con Jupyter Notebook o Google Colab. El archivo `.pbix` requiere Power BI Desktop.

## Herramientas utilizadas
Python (Pandas), SQL, Power BI, análisis estadístico (chi-cuadrado)

## Autor
**Stiven Lizarazo** — Junior Data Analyst
[LinkedIn](https://www.linkedin.com/in/stiven-lizarazo-4b5177258/) · lizarazostiven36@gmail.com
