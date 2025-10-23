# Test BI – Looker Core & Looker Studio
Prueba técnica para candidatos de BI enfocada en Looker Core y Looker Studio.

## Objetivo
Evaluar los conocimientos teóricos y prácticos de candidatos a una vacante enfocada a las herramientas de **Looker Core** y **Looker Studio**.  

---

## Parte 1: Teórica
Responde las siguientes preguntas de opción múltiple.  
Las preguntas están divididas en **nivel básico, intermedio y avanzado** para cada herramienta.  

### Looker Core

#### Nivel Básico
1. En Looker Core, una *dimension* se utiliza principalmente para:  
- a) Calcular agregaciones como SUM o AVG  
- b) Mostrar atributos descriptivos como fechas o nombres
- c) Controlar permisos de usuario  
- d) Generar parámetros de persistencia  

2. ¿Qué es un *Explore* en Looker Core?  
- a) Un archivo que define medidas y dimensiones en LookML  
- b) Una visualización dentro de un dashboard  
- c) Una interfaz para consultar y combinar vistas de datos 
- d) Un tipo de conexión a base de datos  

3. ¿Qué diferencia principal hay entre una *measure* y una *dimension*?  
- a) La measure sirve para filtrar y la dimension para sumar  
- b) La measure hace cálculos agregados, la dimension describe atributos
- c) La measure controla permisos, la dimension define joins  
- d) Son sinónimos  

#### Nivel Intermedio
4. ¿Cuál es la diferencia entre `sql:` y `derived_table:` en LookML?  
- a) `sql:` define expresiones de campo, `derived_table:` crea una subconsulta completa  
- b) `sql:` se usa solo en dashboards, `derived_table:` solo en Explores  
- c) `sql:` es exclusivo para joins, `derived_table:` para dimensiones  
- d) Son sinónimos  

5. ¿Qué sucede si no defines `primary_key: yes` en una dimension usada en un join?  
- a) Looker no permite ejecutar el Explore  
- b) Puede haber duplicados en los resultados 
- c) El join se convierte en un cross join automáticamente  
- d) No afecta en nada  

6. ¿Qué hace el parámetro `drill_fields` en LookML?  
- a) Define la creación de una nueva dimension  
- b) Permite al usuario ver detalles adicionales al hacer clic
- c) Crea un join entre tablas  
- d) Cambia la base de datos usada  

#### Nivel Avanzado
7. ¿Qué función cumple `persist_for:` en un `derived_table`?  
- a) Mantener en caché la consulta en el PDT por un tiempo definido  
- b) Forzar que el Explore se ejecute sin joins  
- c) Evitar duplicación de medidas  
- d) Garantizar seguridad a nivel de fila  

8. ¿Cuál es la ventaja de usar `liquid parameters` en LookML?  
- a) Hacer que los dashboards tengan colores dinámicos  
- b) Permitir cambiar dinámicamente SQL o filtros en base a selecciones del usuario
- c) Evitar errores de sintaxis en SQL  
- d) Reducir el tiempo de ejecución en BigQuery  

9. ¿Qué estrategia es más eficiente para optimizar un Explore con tablas grandes en BigQuery?  
- a) Usar `derived_table` sin persistencia  
- b) Crear persistentes (PDTs) o usar tablas materializadas  
- c) Duplicar todas las dimensiones en un solo Explore  
- d) Evitar siempre los joins  

---

### Looker Studio

#### Nivel Básico
1. En Looker Studio, un *filtro a nivel de gráfico* afecta:  
- a) Todo el reporte  
- b) Solo a la página activa  
- c) Solo al gráfico donde se aplica 
- d) A todos los gráficos con la misma dimensión  

2. ¿Qué tipo de fuente de datos NO se puede conectar directamente a Looker Studio?  
- a) Google Sheets  
- b) BigQuery  
- c) Archivos CSV subidos  
- d) Bases de datos locales sin conector

3. ¿Qué permite hacer un *control de rango de fechas* en Looker Studio?  
- a) Cambiar el formato de visualización  
- b) Filtrar los datos del reporte según un periodo seleccionado 
- c) Crear un join automático  
- d) Guardar filtros personalizados  

#### Nivel Intermedio
4. ¿Cómo crearías un KPI de margen (%) si en tu dataset solo tienes ingresos y costos?  
- a) `AVG(costo/ingreso)`  
- b) `(ingresos - costos) / ingresos` 
- c) Usando un parámetro de fecha  
- d) No es posible en Looker Studio  

5. ¿Cuál es la diferencia entre un *control de rango de fechas* y un *filtro por dimensión* en Looker Studio?  
- a) El rango de fechas aplica a toda la fuente, el filtro solo al gráfico seleccionado
- b) Ambos hacen lo mismo  
- c) El rango de fechas solo funciona con BigQuery  
- d) El filtro por dimensión nunca puede aplicarse a todo el reporte  

6. ¿Qué opción en Looker Studio permite reutilizar un cálculo creado en varios gráficos?  
- a) Dimensiones de sistema  
- b) Campos calculados a nivel de fuente  
- c) Filtros compartidos  
- d) Parámetros de usuario  

#### Nivel Avanzado
7. ¿Cuál es la principal limitación de Looker Studio comparado con Looker Core?  
- a) No se pueden crear gráficos de series temporales  
- b) No se pueden hacer joins complejos o modelado semántico avanzado
- c) No se pueden compartir dashboards  
- d) No es posible conectarse a BigQuery  

8. Si un dashboard en Looker Studio tarda demasiado en cargar, ¿cuál NO es una acción recomendable?  
- a) Usar extractos de datos en vez de conexiones en vivo  
- b) Reducir el número de gráficos por página  
- c) Aplicar filtros más específicos  
- d) Aumentar el número de fuentes de datos en paralelo

9. ¿Qué ventaja ofrece usar *parámetros* en Looker Studio?  
- a) Crear cálculos persistentes en BigQuery  
- b) Permitir que el usuario interactúe y cambie valores dinámicamente 
- c) Mejorar la seguridad a nivel de fila  
- d) Hacer joins entre múltiples fuentes  

---

## Parte 2: Práctica

### Dataset
Se proporcionará un dataset con información de **ventas** que incluye:  
- Fecha de transacción  
- Producto  
- Región  
- Cliente  
- Canal de venta  
- Ingresos y costos

Enlace a dataset: https://docs.google.com/spreadsheets/d/12UQGro3dvy0mVCbDoYV4vYUSylsDcdGOwK0TwRcc77M/edit?gid=846895889#gid=846895889  

### Ejercicio en Looker Core
1. Con base en el dataset, modelar una **view** y un **Explore** en LookML con dimensiones y medidas relevantes. 
3. Incluir al menos:  
   - Medidas de ventas, costos y margen (%)  
   - Dimensiones de fecha, producto y región  
   - Uso de `value_format`, `labels` y `group_labels`, entre otros.
     
**Nota:** El desarrollo de LookML se puede realizar en un archivo .docx o en el editor de código de tu preferencia.

### Ejercicio en Looker Studio
1. Con base en el dataset, construir un **dashboard interactivo** con al menos:  
   - KPI de ventas y margen (%)  
   - Tendencia mensual de ventas  
   - Top 5 productos más vendidos  
   - Filtros por fecha, región y canal  
2. Explicar brevemente en un documento cómo seleccionaste los KPIs y por qué. 

---

## Entregables
1. **Parte Teórica:** Documento con respuestas seleccionadas.  
2. **Looker Core:**  
   - Archivos LookML (views y explores) en un repositorio.  
   - Breve explicación de las decisiones de modelado.  
3. **Looker Studio:**  
   - Link al dashboard publicado con acceso de visualización.  
   - Capturas de pantalla en PDF como respaldo.  

---

## Instrucciones de Entrega
- Crea un repositorio en GitHub con tu solución.  
- Incluye un archivo `README.md` explicando:  
  - Tu enfoque de resolución.  
  - Retos encontrados y cómo los resolviste.  
- Envía el link del repositorio y del dashboard para su evaluación.  
