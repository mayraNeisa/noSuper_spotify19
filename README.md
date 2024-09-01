# Exploración de géneros y recomendación musical basada en Aprendizaje No Supervisado a partir de canciones de Spotify

## Acerca de:

En la era digital, la música se ha convertido en un elemento omnipresente, con plataformas como Spotify que ofrecen acceso a millones de canciones. Sin embargo, la vastedad de opciones puede dificultar la personalización de la experiencia del usuario. Este proyecto propone un enfoque basado en Aprendizaje No Supervisado para analizar una base de datos de 30.000 canciones de Spotify, utilizando características como energía, locuacidad, acústica e instrumentalidad. Mediante el uso de Análisis de Componentes Principales (PCA), se reducirá la dimensionalidad del conjunto de datos, permitiendo la identificación de patrones subyacentes. Posteriormente, se aplicarán técnicas de clustering para agrupar las canciones según géneros emergentes y patrones de popularidad. Finalmente, se diseñará un sistema de recomendación a partir de filtrado colaborativo que aprovechará los resultados obtenidos del análisis no supervisado para ofrecer sugerencias musicales personalizadas. Este proyecto busca no solo descubrir nuevas tendencias musicales, sino también mejorar la experiencia de usuario mediante recomendaciones más precisas y adaptadas a los gustos individuales. 

## Fuente de datos 

El dataset utilizado para este proyecto, corresponde a ’30.000 Spotify Songs’ un dataset de Kaggle creado por Joakim Arvidsson que puede ser consultado a través de la siguiente URL: [enlace](https://www.kaggle.com/datasets/joebeachcapital/30000-spotify-songs/data?select=spotify_songs.csv). En este dataset se encuentran casi 30.000 canciones recuperadas desde la API de Spotify, y 23 columnas o variables que las describen. 

## Descripción de variables 

En el dataset podemos encontrar columnas identificadoras tales como el ID y nombre de la canción, el nombre del artista, el ID y nombre del álbum, y el ID y nombre de la playlist. De igual forma, encontramos la fecha en que fue lanzado el álbum, y variables categóricas como el género y el subgénero al que pertenece la playlist. 

En cuanto a las variables de contenido de tipo numéricas, tenemos las siguientes: 

### Track popularity: 

Popularidad de la canción entre 0 y 100, donde entre más grande el número, mayor es la popularidad. 

### Danceability:

Describe cuán adecuada es la pista para bailar basada en una combinación de elementos musicales que incluyen tempo, estabilidad de ritmo, fuerza de ritmo y regularidad general. Un valor de 0.0 es menos bailable y 1.0 es el más bailable. 

### Energy:

La energía es una medida de 0.0 a 1.0 y representa una medida perceptiva de intensidad y actividad. Por lo general, las pistas enérgicas se sienten rápidas, fuertes y ruidosas. Por ejemplo, el death metal tiene alta energía, mientras que un preludio de Bach obtiene un puntaje bajo en la escala. Las características perceptivas que contribuyen a este atributo incluyen el rango dinámico, el volumen percibido, el timbre, la tasa de inicio y la entropía general. 

### Key: 

La clave general estimada de la pista. Se asignan enteros a lanzamientos utilizando notación de clase de tono estándar. P.ej. 0 = C, 1 = C♯/D ♭, 2 = D, y así sucesivamente. Si no se detectó ninguna clave, el valor es -1. 

### Loudness: 

El volumen general de una pista en Decibels (DB). Los valores de volumen se promedian en toda la pista y son útiles para comparar el volumen relativo de las pistas. El volumen es la calidad de un sonido que es el correlato psicológico primario de la fuerza física (amplitud). Los valores rango típico se encuentran entre -60 y 0 dB. 

### Mode: 

El modo indica la modalidad (mayor o menor) de una pista, el tipo de escala de la que se deriva su contenido melódico. Mayor está representado por 1 y menor es 0. 

### Speechiness: 

El habla detecta la presencia de palabras habladas en una pista. Cuanto más exclusivamente segmera la grabación (por ejemplo, programa de entrevistas, audiolibro, poesía), más cerca de 1.0 el valor del atributo. Los valores superiores a 0.66 describen pistas que probablemente se hagan completamente de palabras habladas. Los valores entre 0.33 y 0.66 describen pistas que pueden contener música y habla, ya sea en secciones o en capas, incluidos casos como la música rap. Los valores por debajo de 0.33 probablemente representan la música y otras pistas sin voz. 

### Acousticness:

Una medida de confianza de 0.0 a 1.0 de si la pista es acústica. 1.0 representa una alta confianza, la pista es acústica. 

### Instrumentalness: 

Predice si una pista no contiene voces. Los sonidos "OOH" y "AAH" se tratan como instrumentales en este contexto. Las pistas de rap o palabras habladas son claramente "vocales". Cuanto más cerca sea el valor de instrumentalidad a 1.0, mayor es la probabilidad de que la pista no contenga contenido vocal. Los valores superiores a 0.5 están destinados a representar pistas instrumentales, pero la confianza es mayor a medida que el valor se acerca a 1.0. 

### Liveness: 

Detecta la presencia de una audiencia en la grabación. Los valores de liveness más altos representan una mayor probabilidad de que la pista se haya realizado en vivo. Un valor superior a 0.8 proporciona una fuerte probabilidad de que la pista esté en vivo. 

### Valence: 

Una medida de 0.0 a 1.0 que describe la positividad musical transmitida por una pista. Las pistas con alta valencia suenan más positivas (por ejemplo, felices, alegres, eufóricas), mientras que las pistas con baja valencia suenan más negativas (por ejemplo, triste, deprimida, enojada). 

### Tempo: 

El tempo estimado general de una pista en ritmos por minuto (BPM). En la terminología musical, el tempo es la velocidad o el ritmo de una pieza dada y se deriva directamente de la duración promedio del latido. 

### Duration: 

Duración de la canción en milisegundos. 


## Estructura de carpetas:

* data: carpeta con los datos descargados de kaggle
* scripts: carpeta con los códigos implementados
* docs: carpeta con los documentos y entregas
