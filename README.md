
# Estensione non ufficiale dati CSV e JSON di COVID-19 Italia + AWS Forecast

[![Liberpay](http://img.shields.io/liberapay/receives/heyteacher.svg?logo=liberapay)](https://liberapay.com/heyteacher/donate)
[![GitHub license](https://img.shields.io/badge/License-Creative%20Commons%20Attribution%204.0%20International-blue)](https://github.com/heyteacher/COVID-19/blob/master/LICENSE)
[![GitHub commit](https://img.shields.io/github/last-commit/heyteacher/COVID-19)](https://github.com/heyteacher/COVID-19/commits/master)

Il Repository contiene: 

* estensioni calcolate sui dati CSV e JSON ufficiali forniti da https://github.com/pcm-dpc/COVID-19 
* generazione di __forecast__ su __nuovi casi__ sulla _time series regionale_ tramite https://aws.amazon.com/forecast/ (_Perform AutoML_, _Quantile Loss_: 50% ).
* __forecast__ nazionale calcolato come aggregazione del __forecast__ di __nuovi_casi__ regionale

I dati JSON di questo repository sono utilizzati per la realizzazione della dashboard COVID-19 Italia 
https://heyteacher.github.io/COVID-19/ un progetto Angular 9 i cui sorgenti sono disponibili qui: https://github.com/heyteacher/ng-covid-19-ita-charts 

Lo scopo della denormalizzazione introdotta da questo repository consiste nell'agevolare l' accesso di dati senza doverli ricalcolare. 

## Formato dei dati

### Dati Nazionali e Dati per Regione

Di seguito la definizione dei nuovi valori calcolati rispetto ai dataset ufficiali https://github.com/pcm-dpc/COVID-19

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

| Nome campo                  | Descrizione                               | Description                     | Formato  |
|-----------------------------|-------------------------------------------|---------------------------------|----------|
| **totale_nuovi_casi**       | Totale nuovi casi                         | New amount positive cases       | Number   |
| **totale_casi_ieri**        | Totale casi di ieri                       | Yesterday amount positive cases | Number   |
| **nuovi_dimessi_guariti**   | Nuovi dimessi guariti rispetto ieri       | New amount recovered            | Number   |
| **dimessi_guariti_ieri**    | Totale dimessi guariti di ieri            | Yesterday amount recovered      | Number   |
| **nuovi_deceduti**          | Nuovi deceduti rispetto ieri              | New amount deaths               | Number   |
| **deceduti_ieri**           | Totale decetuti di ieri                   | Yesterday amount deaths         | Number   |
| **nuovi_terapia_intensiva** | Nuovi in terapia insensiva rispetto ieri  | New amount intensive cares      | Number   |
| **terapia_intensiva_ieri**  | Totale in terapia intensiva ieri          | Yesterday intensive cares       | Number   |
| **nuovi_tamponi**           | Nuovi tamponi rispetto ieri               | New amount test (swab)          | Number   |
| **tamponi_ieri**            | Totale tamponi ieri                       | Yesterday amount test (swab)    | Number   |

__NOTA__: a partire del 01/04/2020 il repository ufficiale ha introdotto `nuovi_positivi` che corrisponde a `totale_nuovi_casi` di questo dataset

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

| Nome campo                  | Descrizione                               | Description                     | Formato  |
|-----------------------------|-------------------------------------------|---------------------------------|----------|
| **totale_nuovi_casi**       | Totale nuovi casi                         | New amount positive cases       | Number   |
| **totale_casi_ieri**        | Totale casi di ieri                       | Yesterday amount positive cases | Number   |


### Dati Forecast Nazionale

**File complessivo JSON:** 
* `dati-json-forecast/covid19-ita-andamento-nazionale-forecast.json` 

| Nome campo                  | Descrizione                               | Description                 | Formato     |
|-----------------------------|-------------------------------------------|-----------------------------|-------------|
| **date**                    | Giorno della rilevazione                  | Date of notification        | Timestamp   |
| **p50**                     | previsione nuovi casi (quantile loss 50%) | Forecast new positive cases | Float       |

### Dati Forecast Regionale

**File complessivo JSON:** 
* `dati-json-forecast/covid19-ita-andamento-nazionale-forecast.json` 

| Nome campo                  | Descrizione                               | Description        | Formato     |
|-----------------------------|-------------------------------------------|--------------------|-------------|
| **item_id**                 | Denominazio Regione                       |                    | Timestamp   |
| **date**                    | Nuovi casi rispetto ieri                  |                    | Timestamp   |
| **p10**                     | previsione nuovi casi (quantile loss 10%) |                    | Float       |
| **p50**                     | previsione nuovi casi (quantile loss 50%) |                    | Float       |
| **p90**                     | previsione nuovi casi  (quantile loss 90%)|                    | Float       |
