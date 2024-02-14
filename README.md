![HenryLogo](https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png)

## Proyecto Indiviual 2
### Juan Carlos Mora Montenegro

Se realiza un estudio de diferentes incidentes viales sucedidos en Buenos Aires tomando en cuenta dos variantes por un lado accidentes sin victimas mortales y por el otro los accidentes cuyo descenlace termina en por lo menos un fallecido durante el hecho o que muere posteriormente como consecuencia de las heridas infringidas en el incidente.

## Análisis Exploratorio de los Datos (EDA)

<img src="../DatosProyectoIndividual2/Graficos/FaltantesLesiones.jpg" height="400"><br>

En la tabla Lesiones se determina los siguientes faltantes de información que no son eliminados de los datos base puesto que en otras columnas tienen información importante que enriquecen la estadística

|Cantidad	  |Descripción|
|--------|---------------------------|
|9|Sin identicación de franja horaria|
|10815	|Sin dirección normalizada|
|1288|	No tiene idetificación de comuna|
|11045|	No presentan tipo de calle|
|3327	|sin especificación de vehículos|
|1213	|Sin geocodificación|

Se ubica un outlier en el hecho identificado con el ID LC-2020-0244615 en los campos de latitud y longitud.

|Campo|Dato|Acción realizada para corrección
|-|-|-|
|Latitud|	-3472890716|	Se agrega signo de separación decimal
|Longitud|	-5829963273|	Se agrega signo de separación decimal

En la tabla de homicidios se observan los siguientes faltantes de información:

|Cantidad	|Descripción
|-|-
|1	|Se eliminan los hechos 2016-0174 y 2016-0151 que no proporcionan información sustancial para las estadísticas
|1	|No tiene información de hora
|4	|Sin información víctimas
|10	|No tiene las coordenadas pero se conservan puesto que tienen la información de la comuna

Se realizan todas las observaciones mediante filtros de excel y se determinan los faltantes, en la tabla de lesiones no se eliminan datos puesto que en otros campos se encuentra información relevante y representativa para la entrega de resultados.

Luego de verificada la información se hace la importación de datos desde Power BI de las tablas:

|Nombre Tabla|
|-|
|Homicidios|
|Victimas de homicidios|
|Lesiones|
|Victimas de lesiones|

## Complementos de información para definir la presentación final

Como complemento para la entrega de resultados se crean y adicionan las siguientes estructuras de información:

### Tabla

Se crea la tabla Coordenadas Comunas que contiene la información general de cada una de las 15 comunas incluyendo latitud y longitud lo que permitira clasificar cada uno de los hechos en esta división política y se podrán mostrar de una manera más clara las burbujas correspondientes a los mapas y da claridad gráfica para observación.

### Consultas

Para poder realizar estadísticas desde la tabla lesiones se creán cinco consultas a saber:

|Nombre|Descripción|
|-|-
|Hechos Auto|Muestra una línea por cada hecho en el que se involucró un automovil
|Hechos Camión|Muestra una línea por cada hecho en el que se involucró un Camión
|Hechos Moto|Muestra una línea por cada hecho en el que se involucró una motocicleta
|Hechos Transporte público|Muestra una línea por cada hecho en el que se involucró un Vehículo de transporte público
|Hechos Vehículo|Muestra una línea por cada hecho en el que se involucró una bicicleta y adicionalmente en esta consulta se hace la unión con las anteriores consultas y luego realacionar con la tabla hechos