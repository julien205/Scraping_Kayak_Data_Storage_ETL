# Scraping_Kayak_Data_Storage_ETL

Définir quels sont les meilleurs hotels d'une liste de villes françaises et relativiser les résultats en fonction de la météo de la semaine à venir dans ces villes.

Nous utilisons l'API openweathermap pour récupérer les données météos de villes françaises.
L'API nominatim nous permettra quand à elle d'obtenir leurs coordonnées géographiques de ces villes.
Au moyen de la librairie scrapy, nous extrairons du site booking.com toutes les données que nous jugerons nécessaires afin d'obtenir des informations sur les hotels de ces villes.

Nous stockons ensuite ces résultats dans un Datalake au moyen d'un bucket S3 d'amazon.
Afin de permettre un accès à ces données sous forme de base de données relationelles nous créons un Data Warehouse RDS d'amazon auquel nous
accèderons via PGAdmin ou directement via SQLAlchemy.

Enfin nous présenterons les résultats sous formes de cartes où apparaîtrons les 20 meilleurs hotels (moyenne pondérée du nombre d'étoiles et des notes des clients) dans les cinq régions où la météo sera la plus clémente ( moyenne pondérée de la température et des précipitations)
