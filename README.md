

<p align=center> 
<img src="henry logo.png" alt="alt text" width="100" style="display: block; margin: auto;"/>

  <h1 align="center">PROYECTO INDIVIDUAL Nº2</h1>
  <h1 align="center">Autor: Duniet Marrero García</h1>
  <h1 align="center">Tema: Data Analyst. Siniestros Viales en Buenos Aires.</h1>

</body>



<p align=center> 

<img src="siniestro_vial.jpeg" alt="alt text" width="500" style="display: block; margin: auto;"/>

<hr> 
<p align=center> 
¡Este readme corresponde al Proyecto Individual Nro. 2 de la Etapa de labs! para la Cohorte DATA-PT-06.
<hr>  

## **Descripción y Contexto**

El Observatorio de Movilidad y Seguridad Vial (OMSV), centro de estudios que se encuentra bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires, solicita la elaboración de un proyecto de análisis de datos, con el fin de generar información que le permita a las autoridades locales tomar medidas para disminuir la cantidad de víctimas fatales de los siniestros viales. 

El Observatorio fue creado por la Ley 4511/2013. Es un centro de estudios de alta eficiencia y nivel técnico que tiene como objetivo sistematizar y analizar información para comprender la situación actual en materia de seguridad vial en la Ciudad. Desde 2020 se amplió su campo de acción, incluyendo la elaboración de informes y reportes relativos a la Movilidad en la Ciudad.


El Observatorio de Movilidad y Seguridad Vial de la Ciudad de Buenos Aires (OMSV) toma como su principal fuente de información datos policiales, tal y como recomiendan los estándares internacionales. Las estadísticas elaboradas se realizan en base a los sumarios que instruye la Policía de la Ciudad ante dos clases de delitos que involucran la seguridad vial: lesiones culposas y homicidios culposos.

En Argentina, aproximadamente 4.000 personas fallecen cada año en accidentes de tráfico. A pesar de los esfuerzos realizados en muchas jurisdicciones para reducir la cantidad de estos incidentes, siguen siendo la principal causa de muertes violentas en el país. Según los informes del Sistema Nacional de Información Criminal (SNIC) del Ministerio de Seguridad de la Nación, entre 2018 y 2022 se registraron 19.630 muertes en siniestros viales en todo el país. Estas cifras equivalen a un promedio de 11 víctimas fatales diarias debido a accidentes de tráfico.

## **Datasets**

Los archivos para iniciar el trabajo se descargaron de la página [Buenos Aires Data](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales), son de uso público y se encuentran en formato Excel:

- ***Homicidios (XLSX):*** Información sobre homicidios en siniestros viales ocurridos en la Ciudad desde el año 2016 hasta el 2021. Los datos incluyen fecha y ubicación del hecho y tipo de transporte involucrado.

- ***Lesiones (XLSX):*** Información sobre las lesiones en siniestros viales ocurridos en la Ciudad desde el año 2019 hasta el 2021. Los datos incluyen fecha y ubicación del hecho y tipo de transporte involucrado.

Además se pueden descargar los siguientes archivos auxiliares en formato pdf:

- ***NOTAS HOMICIDIOS SINIESTRO VIAL:*** Es un documento guía relacionado que contiene información sobre Bases de Víctimas Fatales en Siniestros Viales. Notas para su uso.

- ***NOTAS LESIONES SINIESTRO VIAL:*** Es un documento guía relacionado que contiene información sobre Bases de Lesiones en Siniestros Viales. Notas para su uso.

## **Tecnologías utilizadas**

Para la realización del proyecto se utilizó Python, NumPy, Pandas, Matplotlib y Seaborn en un notebook de Google Colaboratory para desarrollar los procesos de Análisis Exploratorio de los Datos (EDA) y para la Extracción, Transformación y Carga de los mismos (ETL). La visualización de los análisis y resultados se realizó en un dashboard interactivo utilizando Power BI.

## **Análisis Exploratorio de los Datos (EDA) y Extracción, Transformación y Carga (ETL)**

Para realizar el EDA y el ETL se importaron las librerías necesarias como Pandas, NumPy, Matplotlib y Seaborn.


**Archivo: Homicidios_HECHOS**
<hr> 

Primeramente se cargó el conjunto de datos desde el archivo "homicidios.xlsx" en la pestaña 'HECHOS' y se exploró su información básica, como el tamaño del DataFrame, la presencia de datos nulos y las principales estadísticas descriptivas de las variables numéricas (Media, Desviación Estándar, Valor máximo, Valor mínimo, etc.). En este punto, se proporcionaron conclusiones sobre el dataset, como la cantidad de años cubiertos, la distribución de las víctimas por siniestro y la distribución de siniestros por año, mes, franja horaria y comuna. 

Se llegó a la conclusión que este dataset tiene 21 columnas y 696 filas. Se observa que las columnas 'Altura' y 'Cruce' son las que mas datos nulos presentan, lo cual se explorará en detalle más adelante. Los siniestros registrados en el dataframe abarcan un periodo de 6 años desde 2016 hasta 2021. Las víctimas por accidentes van desde 1 hasta 3 con una media de 1.03 víctimas por siniestro y los mismos han sido registrados en todos los años del periodo analizado, durante todos los meses, en todas las franjas horarias y en todas las comunas de la ciudad, es decir, en este sentido no hay excepciones en la ocurrencia de los mismos.

Se identificaron y manejaron los valores nulos en las columnas más relevantes, como "Altura" y "Cruce", mediante estrategias como la imputación de valores o la eliminación de columnas innecesarias. Se modificaron los tipos de variables según fue necesario y acorde al tipo de datos que representan.

Posteriormente se analizaron variables específicas, como el tipo de movilidad de las víctimas y los acusados, la frecuencia de siniestros por tipo de calle y la relación entre variables como la fecha del siniestro y la cantidad de víctimas.

Se examinaron las correlaciones entre diferentes variables, como la relación entre el día de la semana y el número de víctimas, y se presentaron las correlaciones en una matriz de calor.

<p align=center> 
<img src="matriz.png" alt="alt text" width="500" style="display: block; margin: auto;"/>

<p> 

Finalmente se realizaron ajustes en los nombres de las columnas resultantes para estandarizar los mismos y facilitar la comprensión y el análisis de los datos.

**Archivo: Homicidios_VICTIMAS**
<hr> 

Se cargaron los datos desde el mismo archivo Excel, pero en esta ocasión específicamente desde la pestaña 'VICTIMAS' para realizar la exploración del resto de la información proporcionada.

Se mostraron las primeras filas del DataFrame y se exploraron los datos nulos y los tipos de datos presentes. Se observó que este dataset tiene 10 columnas y 717 filas, y se comparó con el otro dataset relacionado con los HECHOS, evidenciando que el número de filas es mayor en el dataset de víctimas debido a la posibilidad de múltiples víctimas por hecho. Se analizaron los registros de fecha y se mencionó que hay valores duplicados de 'ID' debido a múltiples víctimas en un mismo incidente.

Se contabilizaron y verificaron los valores duplicados en el DataFrame, y se comprobó que no existían valores faltantes en la columna 'ID_hecho'. Se identificaron y corrigieron los valores nulos en la columna 'EDAD', transformando su tipo de dato a numérico y realizando una imputación de datos faltantes basada en la media de las edades por sexo.

<p align=center> 
<img src="descarga edades.png" alt="alt text" width="1000" style="display: block; margin: auto;"/>

<p> 

Las edades de entre 20 y 40 años son las que tienen la mayor frecuencia de víctimas. Se puede analizar que las personas en este rango de edad suelen estar en un período de mayor actividad social y profesional, lo que significa que pasan más tiempo en la carretera debido al trabajo, estudio, actividades recreativas, etc. Los adultos jóvenes a menudo participan en comportamientos de riesgo en la carretera.

Se graficaron además las frecuencias de los roles en el siniestro y los sexos de las víctimas, destacando las tendencias observadas y las posibles interpretaciones detrás de ellas.

Posteriormente se examinaron posibles valores atípicos en la columna 'EDAD' y 'NUMERO DE VICTIMAS' por incidente. No se encontraron valores atípicos.

<p align=center> 
<img src="descarga valores atipicos.png" alt="alt text" width="500" style="display: block; margin: auto;"/>

<p> 

En este archivo también se estandarizaron los nombres de las columnas para asegurar consistencia y claridad en el análisis.

**Unión de ambos archivos en un solo Dataset.**
<hr> 

Para unir ambos archivos, se eliminaron las columnas duplicadas entre los datasets de víctimas y hechos para facilitar la fusión de ambos conjuntos de datos y no conservar información repetida ni redundante.

Por último, se fusionaron los datasets de HECHOS y VICTIMAS en un único DataFrame llamado ['df_siniestros'](https://drive.google.com/file/d/1-3vQStmvA8VabDYbSNWOTuGKf-spPSU4/view?usp=sharing) utilizando la columna 'Id_siniestro' como clave de unión y el mismo se exportó como un archivo CSV para su posterior uso y análisis.

Este proceso de EDA y ETL proporciona una comprensión del conjunto de datos y establece una base sólida para análisis más avanzados y visualización de datos con un dataset limpio y transformado para generar informes fiables y de calidad.
</p>

El notebook fue realizado en Google Colaboratory y se puede consultar en el siguiente [enlace](https://colab.research.google.com/drive/1O0ZZ89CkxYTywOkcALzFG3pYsZboXGSK?usp=sharing).


## ** Medición de indicadores mediante KPIs**

Los KPIs (Indicadores Claves de Desempeño) evaluan el progreso hacia los objetivos de una organización, estos indicadores proporcionn una visión rápida y clara del rendimiento de una empresa en relación con sus metas estratégicas, , por lo que son cruciales para el seguimiento del desempeño y la toma de decisiones.

En el proyecto se plantearon tres objetivos (KPIs) en función de lograr la disminución de la cantidad de víctimas fatales y ocurrencia de siniestros viales, los cuales fueron propuestos luego de analizar minusiosamente los datos proporcionados.

* - Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses en comparación con la tasa de homicidios del semestre anterior*

Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Se define como Tasa de homicidios en siniestros viales al número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico, en este caso se toman 6 meses. Su fórmula es:

ú
ó
 

Como Población Total se calculó la población para el año 2021 a partir de los censos poblacionales del año 2010 y 2022.

En este caso, para el año 2021, la Tasa de homicidios en siniestros viales fue de 1.77 lo que significa que, durante los primeros 6 meses del año 2021, hubo aproximadamente 1.77 homicidios en accidentes de tránsito por cada 100,000 habitantes. Ahora, el objetivo planteado es reducir esta tasa para el siguiente semestre de 2021 en un 10%, esto es 1.60. Cuando se calcula el KPI para este período se obtiene que la Tasa de homicidios en siniestros viales fue de 1.35, lo que significa que para el segundo semestre de 2021 se cumple con el objetivo propuesto.

Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior

Como se vio en el análisis exploratorio, el 42% de las víctimas mortales se transportaban en moto al momento del hecho. Por lo que se consideró importante proponer el monitoreo de la cantidad de accidentes mortales en este tipo de conductor. Para ello se define a la Cantidad de accidentes mortales de motociclistas como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. La fórmula para medir la evolución de los accidentes mortales con víctimas en moto es:

