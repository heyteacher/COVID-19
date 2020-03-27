
# Estensione non ufficiale dati CSV e JSON di COVID-19 Italia + AWS Forecast

[![Liberpay](http://img.shields.io/liberapay/receives/heyteacher.svg?logo=liberapay)](https://liberapay.com/heyteacher/donate)
[![GitHub license](https://img.shields.io/badge/License-Creative%20Commons%20Attribution%204.0%20International-blue)](https://github.com/heyteacher/COVID-19/blob/master/LICENSE)
[![GitHub commit](https://img.shields.io/github/last-commit/heyteacher/COVID-19)](https://github.com/heyteacher/COVID-19/commits/master)

Il Repository contiene: 

* estensioni calcolate sui dati CSV e JSON forniti da https://github.com/pcm-dpc/COVID-19 
* generazione di __forecast__ su __nuovi casi__ sulla _time series regionale_ tramite https://aws.amazon.com/forecast/ (_Perform AutoML_).
* __forecast__ nazionale calcolato come aggregazione del __forecast__ di __nuovi_casi__ regionale

I dati JSON di questo repository sono utilizzati per la realizzazione della dashboard COVID-19 Italia 
https://heyteacher.github.io/COVID-19/ 


## Formato dei dati

### Dati Nazionali e Dati per Regione

**File complessivi CSV:** 
* `dati-andamento-nazionale/dpc-covid19-ita-andamento-nazionale.csv` 
* `dati-regioni/dpc-covid19-ita-regioni.csv`

**File complessivi JSON:** 
* `json-data/dpc-covid19-ita-andamento-nazionale.json`
* `json-data/dpc-covid19-ita-regioni.json` 

**File giornalieri CSV:** 
* `dati-andamento-nazionale/dpc-covid19-ita-andamento-nazionale-{YYYYMMDD}.csv` 
* `dati-regioni/dpc-covid19-ita-regioni-{YYYYMMDD}.csv`
* `dati-andamento-nazionale/dpc-covid19-ita-andamento-nazionale-latest.csv` 
* `dati-regioni/dpc-covid19-ita-regioni-latest.csv`

**File giornalieri JSON:** 
* `json-data/dpc-covid19-ita-andamento-nazionale-latest.json`
* `json-data/dpc-covid19-ita-regioni-json.json` 

| Nome campo                  | Descrizione                               | Description        | Formato  |
|-----------------------------|-------------------------------------------|--------------------|----------|
| **totale_nuovi_casi**       | Nuovi casi rispetto ieri                  |                    | Numero   |
| **totale_casi_ieri**        | Totale casi di ieri                       |                    | Numero   |
| **nuovi_dimessi_guariti**   | Nuovi dimessi guariti rispetto ieri       |                    | Numero   |
| **dimessi_guariti_ieri**    | Totale dimessi guariti di ieri            |                    | Numero   |
| **nuovi_deceduti**          | Nuovi deceduti rispetto ieri              |                    | Numero   |
| **deceduti_ieri**           | Totale decetuti di ieri                   |                    | Numero   |
| **nuovi_terapia_intensiva** | Nuovi in terapia insensiva rispetto ieri  |                    | Numero   |
| **terapia_intensiva_ieri**  | Totale in terapia intensiva ieri          |                    | Numero   |


### Dati per Provincia

**File complessivo CSV:** 
* `dati-province/dpc-covid19-ita-province.csv` 

**File complessivo JSON:** 
* `json-data/dpc-covid19-ita-province.json` 

**File giornalieri CSV:** 
* `dati-province/dpc-covid19-ita-province-{YYYYMMDD}.csv` 
* `dati-province/dpc-covid19-ita-province-latest.csv` 

**File giornaliero JSON:** 
* `json-data/dpc-covid19-ita-province-latest.json` 

| Nome campo                  | Descrizione                               | Description        | Formato  |
|-----------------------------|-------------------------------------------|--------------------|----------|
| **totale_nuovi_casi**       | Nuovi casi rispetto ieri                  |                    | Numero   |
| **totale_casi_ieri**        | Totale casi di ieri                       |                    | Numero   |


### Dati Forecast Nazionale

**File complessivo JSON:** 
* `dati-json-forecast/covid19-ita-andamento-nazionale-forecast.json` 

| Nome campo                  | Descrizione                               | Description        | Formato     |
|-----------------------------|-------------------------------------------|--------------------|-------------|
| **date**                    | Nuovi casi rispetto ieri                  |                    | Timestamp   |
| **p90**                     | previsione nuovi casi(quantile loss 90%)  |                    | Float       |

### Dati Forecast Regionale

**File complessivo JSON:** 
* `dati-json-forecast/covid19-ita-andamento-nazionale-forecast.json` 

| Nome campo                  | Descrizione                               | Description        | Formato     |
|-----------------------------|-------------------------------------------|--------------------|-------------|
| **item_id**                 | Denominazio Regione                       |                    | Timestamp   |
| **date**                    | Nuovi casi rispetto ieri                  |                    | Timestamp   |
| **p90**                     | previsione nuovi casi  (quantile loss 90%)|                    | Float       |
