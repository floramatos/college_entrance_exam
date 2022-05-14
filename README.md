# college_entrance_exam
an analysis of the scores in the Brazilian college entrance exam, ENEM, for the 2019 and 2020

Data was source from: https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados

### overview



### database
To create database, ETL process:
1. Two raw csv files (MICRODADOS_ENEM_2019.csv and MICRODADOS_ENEM_2020.csv) were loaded to a AWS S3 bucket.
2. A connection from AWS to Snowflake was created and the files were staged.
3. Two empty SQL tables were created in Snowflake (enem2019 and enem2020)
4. Data was ingested from AWS bucket to empty Snowflake SQL tables.
5. The main tables were filtered by the name of the city where the candidates' school is located (NO_MUNICIPIO_ESC = 'Aracaju') and two tables (enem_aju_2019 and enem_aju_2020) were created with the following columns: 
    - ID: unique candidate idenfification,
    - City: the city where the candidates' school is located,
    - Year: the year of the test,
    - Age: the age of the candidate,
    - Gender: the sex of the candidate,
    - Race: the race of the candidate,
    - School_Type: the type of school - private or public,
    - NaturalScience_Score: score on natural sciences subsection of the exam,
    - HumanScience_Score: score on humanities subsection of the exam,
    - Language_Score: score on language subsection of the exam,
    - Math_Score: score on math subsection of the exam,
    - Writing_Score: score on writing subsection of the exam.
6. The tables were joined to be imported and analyzed in R or Tableau.

## data analysis



