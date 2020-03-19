# Estensione non ufficiale ati JSON di COVID-19 Italia

Repository non ufficiale con estensioni calcolate sui dati JSON forniti da https://github.com/pcm-dpc/COVID-19

## Formato dei dati

Rispetto ai dati ufficiali JSON di pcm-dpc/COVID-19 sono presenti i seguenti campi per ogni giorno:

### Dati Nazionali e Dati per Regione

**File complessivi:** `json-data/dpc-covid19-ita-andamento-nazionale.csv`, `json-data/dpc-covid19-ita-regioni.csv` 


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

**File complessivo:** `json-data/dpc-covid19-ita-province.csv` 


| Nome campo                  | Descrizione                               | Description        | Formato  |
|-----------------------------|-------------------------------------------|--------------------|----------|
| **totale_nuovi_casi**       | Nuovi casi rispetto ieri                  |                    | Numero   |
| **totale_casi_ieri**        | Totale casi di ieri                       |                    | Numero   |


## Dashboard

https://heyteacher.github.io/COVID-19/ è una dashboard basata su questi dati estesi
