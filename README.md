# Project_ETL

![](https://github.com/NoeRoson/Project_ETL/blob/main/img/portada_vg.png)

## Introducción

La pretensión de este proyecto es realizar un proceso completo de **extracción, transformación y carga de archivos** a una base de datos, utilizando para ello dos métodos diferentes de extracción y tres fuentes de obtención de la información. 

El **objetivo último** es el análisis del impacto que tienen las campañas de prevención de violencia de género con respecto al número de víctimas mortales, denuncias registradas y llamadas recibidas por el teléfono de atención 016.


## Pasos seguidos

### 1. [Extracción de los datos:](https://github.com/NoeRoson/Project_ETL/blob/main/Notebooks/1_Extraccion_webscrap.ipynb)

Se escogen dos métodos de extracción de los datos:
- **Descarga de tres archivos .csv** del Portal Estadístico Delegación del Gobierno contra la Violencia de Género, los cuales recogen por provincia, mes y año (de 2007 a 2023):
    - Número de denuncias de violencia de género.
    - Número de llamadas pertinentes al 016.
    - Número de víctimas mortales por violencia de género.


- **Web scraping de dos url diferentes**:
    - Delegación del Gobierno contra la Violencia de Género: de aquí se obtienen las fechas de publicación de las diferentes campañas contra la Violencia de Género realizadas por el Ministerio de Igualdad (de 2020 a 2023). 
    - Artículo web de la revista Maldita: de aquí se obtiene la fecha de publicación de un documental que presuntamente impactó en el numero de llamadas recibidas por el 016 (2021).

Con toda esta información se crea un archivo csv que contiene las fechas de publicación y las urls de cada sitio web.


### 2. [Transformación y limpieza de los datos:](https://github.com/NoeRoson/Project_ETL/blob/main/Notebooks/2_Transformacion_datos.ipynb)

- Con los datos extraídos de los archivos .csv se procede a la limpieza de los mismos para obtener únicamente aquellos registros entre 2020 y 2023 y mantener el mes y la provincia.

- Con las fechas scrapeadas de las campañas de prevención, se crea un nuevo archivo csv con el mes, el año y la url de cada una de ellas.


### 3. [Carga de los datos en MongoDB:](https://github.com/NoeRoson/Project_ETL/blob/main/Notebooks/3_Carga_MongoDB.ipynb)

Con los cuatro archivos resultantes se crea una base de datos en MongoDB y se exportan en formato JSON para futuros análisis de datos. Se realizan consultas a la base de datos para comprobar su correcto funcionamiento.




## Recursos

- [MongoDB](https://www.mongodb.com/)
- [Delegación del Gobierno contra la Violencia de Género](https://violenciagenero.igualdad.gob.es/sensibilizacionConcienciacion/campannas/violenciaGobierno/home.htm)
- [Portal Estadístico Delegación del Gobierno contra la Violencia de Género](https://estadisticasviolenciagenero.igualdad.gob.es/)
- [Artículo incremento llamadas al 016](https://maldita.es/malditodato/20210409/llamadas-016-crecieron-marzo-documental-rocio-carrasco/)