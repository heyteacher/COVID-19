# Estensione non ufficiale dati CSV e JSON di COVID-19 Italia

Repository non ufficiale con estensioni calcolate sui dati CSV e JSON forniti da https://github.com/pcm-dpc/COVID-19

## Formato dei dati

Rispetto ai dati ufficiali di pcm-dpc/COVID-19 sono presenti i seguenti campi per ogni giorno:

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


## Dashboard

https://heyteacher.github.io/COVID-19/ è una dashboard basata su questi dati estesi
