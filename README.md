# Trabajo integrador Power BI

## 1. Objetivo

Generar un Dashboard dinámico en Power BI, con gráficas e indicadores que mejor representen y expliquen la información.

## 2. Instrucciones.

Se proporciona un dataset en Excel (CSV) donde está la información transaccional de ventas separada en diferentes archivos que corresponden a una dimensión de un modelo analítico.

### 1. Obtener datos en Power BI

  * Importa los datos de la carpeta y analiza la calidad del datos e identifica las columnas con valores en blanco o nulos y elimina las columnas con más de un 30% de valores nulos
### 2. Limpiar, transformar y cargar datos
  
  * verifica el formato y tipo de datos y pasa a fecha los campos que estén como fecha/hora.
  * Ordena la tabla sales por fecha decreciente (Datekey)
  * Elimina los duplicados de la dimensión Promotion

### 3. Pre-procesamiento a los datos del informe

  * Añade una columna índice a Sales ordenada por las fechas en orden decreciente.
  * Genera una columna personalizada “StoreName_limpio” donde elimines la palabra “Contoso” de la columna StoreName en la tabla Stores.

### 4. Diseñar un modelo de datos

Genera un modelo de datos con la información que se importó desde Power Query.

  * Añade las relaciones entre las tablas
  * Comprueba la cardinalidad, evitando que haya relaciones del tipo muchos a muchos
  * Comprueba la dirección de filtro e introduce a ambas direcciones en los casos que veas necesario
  * Genera la tabla calendario (Fecha)

### 5. Métricas y columnas calculadas con DAX

  * Genera la métrica “coste” que calcule la suma de los costes totales de las Ventas (TotalCost de Sales)
  * Genera la métrica “productosDistintos” que calcule el número de productos distintos en la tabla Product
  * Genera la métrica “canales” que calcule el número de filas en la tabla canales Data
  * Genera la columna calculada “Rentabilidad” que devuelva si es rentable (ReturnAmount>100) o si no es rentable (ReturnAmount>100) en la dimensión Sales
  * Genera la columna calculada “canalPersonalizado” que devuelva una concatenación de “Canal “y la columna ChannelName dentro de la tabla Channel
  * Genera la métrica “costeAsia” que calcule la suma de costes para el continente de Asia (ContinentName igual a Asia)
  * Genera la métrica “DescuentosAsia” que calcule el número de descuentos (DiscountQuantity) aplicados sobre el continente de Asia (ContinentName igual a Asia)
  * Genera una colunma calculada “DiaDeVenta” que devuelva el día en el que se ha producido la venta (DateKey)

### 6. Visualizar datos en Power BI 

Realiza tres gráficos y dos tarjetas que muestren lo siguiente:

  * Gráfico de barras de Retorno por Campaña
  * Gráfico de líneas con el promedio de Retorno por fecha
  * Gráfico donde puedas ver que categoría de producto es la más rentable (Profit) así como la evolución de sus ventas (SalesAmoount) a lo largo del tiempo (formula de profit Sales[ReturnAmount]*Sales[SalesAmount])-Sales[TotalCost])

Genera los siguientes KPIs en la parte superior.

* SalesQuantity
* ReturnQuantity
* REturnAmount
* SalesAmount
* Profit

> **_Nota:_** Crea una mediad calculada para cada operación

Segmentadores y filtros

* Tres segmentadores superiores de producto, subcategoría y promoción
* Un filtro de “Continente” a nivel de hoja, donde solo se seleccione Europa y north America
* Añade un filtro a nivel de grafica a “ventas por fecha y categoría de producto” que coja todas las categorías de producto a excepción de las que estén en blanco.

Finalmente, añade todas las mejoras y buenas prácticas indicadas a lo largo de las sesiones del curso y que consideres necesarias.
El archivo .pbix resultante debe ser cargado en el classroom hasta la fecha indicada y debe ser nombrado de la siguiente manera Nombre_Apellido_cursoPBI.pbix
