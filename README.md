☕ ENGLISH BELOW

# **T1INSIGHT** 
# ***🎙️El próximo artista revelación de Eurovisión🎙️***
Por: Cibele Busnello, Isabel Garcia, Andrea Gauger, Amanda Hernandez, Diana P. Gómez

# **🎯Objetivo del Proyecto:**

Este proyecto tiene como objetivo identificar al próximo artista de Eurovisión con potencial para volverse viral o popular, incluso si no gana el concurso. 
Para ello, hemos realizado un análisis exhaustivo de las playlists de Eurovisión en Spotify, complementado con datos de Last.fm y el ranking oficial de Eurovisión.



# **📌Descripción del Proyecto:**

En este proyecto analizamos los datos musicales de los artistas más populares de las playlists de Eurovisión (2019-2024, excluyendo 2020). 
Utilizamos información obtenida de tres APIs:

- **Spotify API:** Para extraer las playlist con los temas que llegaron a la final de Eurovisión de cada año.
- **Last.fm API:** Para recopilar datos detallados sobre los artistas, incluidos oyentes, reproducciones, artistas similares, géneros y sus 3 canciones más populares.
- **Eurovisión API:** Para obtener el ranking oficial de cada año del concurso y el país que representaban los artistas.

La información recopilada la hemos almacenado en una base de datos estructurada mediante Python y MySQL, permitiendo consultas avanzadas para el análisis de tendencias musicales.

Decidimos descartar el año 2020 ya que, debido a la pandemia, aunque hubo una preselección de artistas, finalmente el festival no se celebró y no se llegó a resolver el ranking. 



##  **💻Tecnologías utilizadas:**

- **Lenguajes:** Python, SQL
- **APIs:** Spotify, Last.fm, Eurovisión
- **Librerías Python:** Pandas, Requests, SQLAlchemy
- **Bases de Datos:** MySQL
- **Entorno de Desarrollo:** Jupyter Notebook


##  **👨‍💻Metodología:**
Las playlists elegidas para el desarrollo del proyecto fueron las siguientes:
- [2019](https://open.spotify.com/playlist/3ZdQUt8Tmtt7oOU8UM2koe?si=242f628e6c8c4da3)
- [2021](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209) 
- [2022](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209)
- [2023](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209)
- [2024](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209)

El proyecto comienza con el *scrappeo* de las APIs de Eurovisión, Spotify y LastFM mediante la librería de Python `requests` y, en el caso de Spotify, con `Spotipy`. 

Con la librería `pandas` se organiza la información extraída de las APIs en DataFrames que facilitan la visualización de las extracciones. Una vez se tiene todo la información, convertimos los DF en tuplas y se da paso a la exportación de la data a csv. 

Una vez exportado en csv comienza el proceso de limpieza para descartar data irrelevante y ordenar la información de forma lógica para luego poder visualizarla en las tablas SQL.

> ❗DISCLAIMER: El proceso de limpieza de datos se hizo a continuación de la primera extracción. Ya que las APIs de Spotify y de LastFM actualizan información de oyentes y popularidad constantemente es posible que en el momento que el usuario ejecute el código la data que extraiga de las APIs sea diferente a la que encontrará en las conclusiones de este proyecto.

Una vez los csv están limpios y los datos de artistas y tracks (los Primary Keys) concuerdan entre las tablas procedemos a la creación de la base de datos y las tablas que la conforman. 

Para ello usamos Python y la librería `mysql.connector`, con la que estructuramos el esquema de la base de datos e hicimos el volcado de datos de los csv. 

La parte final, la de ejecución de queries para cruzar información relevante para nuestro proyecto, se hizo en MySQL Workbench.

## **💾Instalación**

En este repositorio encontrarás el archivo Jupiter Notbook y dos carpetas. El archivo puede ejecutarse en cualquier plataforma Jupiter Notebook, aunque recomendamos Visual Studio Code. 

El archivo Jupiter Notebook (project-execution) contiene todo el código necesario para llamar a las API de Spotify, LastFm y Eurovision, pero el usuario deberá registrarse en las páginas web de solicitud de API de [Spotify](https://developer.spotify.com/documentation/web-api) y [LastFM](https://www.last.fm/api) para obtener un API ID y un API Key.

Una vez se corra el código se crearán 4 csv con la data extraída, pero a la hora de hacer la importación a SQL el código toma los csv limpios que hay en la carpeta csv_clean. 

En la carpeta queries el usuario encontrará un script .sql con las consultas realizadas para desarrollar el proyecto. 

##  **📈Consultas y análisis:**

El proyecto incluye consultas SQL avanzadas para obtener insights como:

- Artistas con más oyentes y reproducciones en Last.fm.
- Comparación entre el ranking de Eurovisión y la popularidad en plataformas de streaming.
- Identificación de géneros musicales con mayor potencial de viralidad.

## **🚀Presentación ante cliente**

En este [Canva](https://www.canva.com/design/DAGgM8dB9g8/n4RiMeSUldtrkBY_Hf3SjA/view?utm_content=DAGgM8dB9g8&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hc66c5e939b) se puede ver la presentación ante cliente que se hizo con las conclusiones y los resultados que obtuvimos de este proeycto.  

Esperamos que este proyecto  sea de gran utilidad. Estamos abiertas a cualquier sugerencia o colaboración.

----
🇬🇧ENGLISH 
---

# **T1INSIGHT**  
# ***🎙️The Next Breakout Artist of Eurovision🎙️***
By: Cibele Busnello, Isabel Garcia, Andrea Gauger, Amanda Hernandez, Diana P. Gómez  

# **🎯Project Objective:**  

This project aims to identify the next Eurovision artist with the potential to go viral or become popular, even if they do not win the contest.  
To achieve this, we conducted a thorough analysis of Eurovision playlists on Spotify, complemented with data from Last.fm and the official Eurovision ranking.  

# **📌Project Description:**  

In this project, we analyzed the musical data of the most popular artists from Eurovision playlists (2019-2024, excluding 2020).  
We used information obtained from three APIs:  

- **Spotify API:** To extract playlists containing the songs that reached the Eurovision final each year.  
- **Last.fm API:** To collect detailed data on artists, including listeners, plays, similar artists, genres, and their three most popular songs.  
- **Eurovision API:** To obtain the official ranking of each year’s contest and the country each artist represented.  

The collected information was stored in a structured database using Python and MySQL, allowing advanced queries for musical trend analysis.  

We decided to exclude the year 2020 because, due to the pandemic, although a pre-selection of artists was made, the festival was ultimately not held, and no ranking was determined.  

##  **💻Technologies Used:**  

- **Languages:** Python, SQL  
- **APIs:** Spotify, Last.fm, Eurovision  
- **Python Libraries:** Pandas, Requests, SQLAlchemy  
- **Databases:** MySQL  
- **Development Environment:** Jupyter Notebook  

##  **👨‍💻Methodology:**  
The playlists chosen for the development of the project were the following:
- [2019](https://open.spotify.com/playlist/3ZdQUt8Tmtt7oOU8UM2koe?si=242f628e6c8c4da3)
- [2021](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209) 
- [2022](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209)
- [2023](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209)
- [2024](https://open.spotify.com/playlist/5h0sQpJnLVzgy5iOH1UNcl?si=72693c2a4b964209)

The project starts by scraping the Eurovision, Spotify, and Last.fm APIs using the Python library `requests`, and in Spotify's case, with `Spotipy`.  

With the `pandas` library, the extracted API information is organized into DataFrames, making it easier to visualize the data. Once all the information is collected, we convert the DataFrames into tuples and proceed to export the data to CSV.  

Once exported to CSV, the cleaning process begins to discard irrelevant data and logically structure the information so it can later be visualized in SQL tables.  

> ❗DISCLAIMER: The data cleaning process was carried out after the first extraction. Since the Spotify and Last.fm APIs continuously update listener and popularity data, it is possible that when the user runs the code, the extracted data may differ from the findings presented in this project.  

Once the CSV files are cleaned and the artist and track data (the Primary Keys) match across tables, we proceed with creating the database and its corresponding tables.  

For this, we use Python and the `mysql.connector` library, which helps structure the database schema and load the CSV data.  

The final part, executing queries to cross-reference relevant information for our project, was carried out in MySQL Workbench.  

## **💾Installation**  

This repository includes the Jupyter Notebook file and two folders. The Jupyter Notebook file can be executed on any Jupyter Notebook platform, though we recommend Visual Studio Code.  

The Jupyter Notebook file (project-execution) contains all the necessary code to call the Spotify, Last.fm, and Eurovision APIs, but the user must register on the API request pages of [Spotify](https://developer.spotify.com/documentation/web-api) and [LastFM](https://www.last.fm/api) to obtain an API ID and an API Key.  

Once the code runs, four CSV files with the extracted data will be created, but for SQL import, the code uses the cleaned CSV files found in the csv_clean folder.  

In the queries folder, the user will find an SQL script containing the queries used to develop the project.  

##  **📈Queries and Analysis:**  

The project includes advanced SQL queries to extract insights such as:  

- Artists with the most listeners and plays on Last.fm.  
- Comparison between the Eurovision ranking and popularity on streaming platforms.  
- Identification of musical genres with the highest viral potential.  

## **🚀Client Presentation**  

In this [Canva](https://www.canva.com/design/DAGgM8dB9g8/n4RiMeSUldtrkBY_Hf3SjA/view?utm_content=DAGgM8dB9g8&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hc66c5e939b), you can view the client presentation showcasing the conclusions and results we obtained from this project.  


We hope this project is useful. We are open to any suggestions or collaborations.  


