# Startups
Startups Analysis (2012-2021)
(ENG/PT)

Data Analysis about Startups companies around the world between 2012 and 2021.

Análise de dados sobre Startups ao redor do mundo entre 2012 e 2021.

Started uploading the collected data that was stored as CSV files to Google BigQuery, to afterwards explore, clean and prepare the data to build visuals resources throught Looker Studio.

Iniciei direcionando os dados coletados que estavam em formato CSV para o Google Bigquery, para então realizar a exploração, limpeza e preparação os dados para construir visualizações através do Looker Studio.

```SQL
SELECT 
 int64_field_0 AS id,
 company,
 valuation___b_ as valuation,
 EXTRACT (YEAR FROM date_joined) year_joined,
  CASE
    WHEN country = 'United States,' THEN 'United States'
    ELSE country
  END AS country,
  CASE
    WHEN country = 'Hong Kong' AND city IS NULL THEN 'Hong Kong'
    WHEN country = 'Singapore' AND city IS NULL THEN 'Singapore'
    ELSE city
  END AS city,
  CASE
   WHEN industry = 'Finttech' then 'Fintech'
   ELSE industry
  END AS industry, 
 select_investors as investors
FROM startup.startup
ORDER BY valuation DESC;
```

Dashboard

![imagem_2023-09-17_194356886](https://github.com/Ronan-Alencar/Dados_ANP/assets/133599706/e6e476cb-ccc3-43b7-84d5-7066ab5ac99a)

https://lookerstudio.google.com/reporting/6df29d18-e08b-4907-953b-2a90bfca004d

