### Caricamento dei Dati

I dati sono stati caricati dai seguenti file CSV:
- `fastfood.csv`: Contiene informazioni sui fast food, tra cui nome, stato, latitudine e longitudine.
- `pollution.csv`: Contiene dati sull'inquinamento atmosferico, inclusi i livelli medi di O3, CO, SO2, e NO2 per stato e anno.
- `US_GeoCode.csv`: Fornisce le coordinate geografiche (latitudine e longitudine) per ogni stato.
- `heart_2018.csv`: Contiene dati sui tassi di attacchi di cuore, incluso il numero di decessi per stato e anno.

### Selezione e Aggregazione dei Dati

Sono stati selezionati i subset dei dati rilevanti per l'analisi, e le abbreviazioni degli stati sono state mappate ai loro nomi completi. I dati sono stati aggregati come segue:
- **Fast Food**: Conteggio dei fast food per stato.
- **Inquinamento**: Media dei livelli di ozono (O3) per stato.
- **Attacchi di Cuore**: Tassi e numero di decessi per stato.

I dati aggregati sono stati uniti in un unico DataFrame per facilitare l'analisi successiva.

## Analisi delle Reti

### Rete dei Fast Food per Stato

#### Descrizione

- **Nodi**: Ogni nodo rappresenta un fast food (con coordinate geografiche) o uno stato.
- **Archi**: Connettono i fast food agli stati in cui sono situati.

#### Visualizzazione

- La rete è stata visualizzata su una mappa interattiva degli Stati Uniti, con i fast food rappresentati da marcatori blu.
- È stato creato anche un grafico a barre delle 20 catene di fast food più popolari per numero di stati in cui sono presenti.

### Rete dell'Inquinamento per Stato

#### Descrizione

- **Nodi**: Ogni nodo rappresenta uno stato, con un attributo aggiuntivo `ozone_mean` che indica il livello medio di ozono.
- **Archi**: Connettono stati con differenze nei livelli medi di ozono inferiori a una soglia predefinita (5).

#### Visualizzazione

- La rete è stata visualizzata utilizzando un layout a molla, con nodi colorati in base ai livelli di ozono.

### Rete degli Attacchi di Cuore per Stato

#### Descrizione

- **Nodi**: Ogni nodo rappresenta uno stato, con un attributo aggiuntivo `rate` che indica il tasso di attacchi di cuore.
- **Archi**: Connettono stati con differenze nei tassi di attacchi di cuore inferiori a una soglia predefinita (10).

#### Visualizzazione

- La rete è stata visualizzata utilizzando un layout a molla.

### Rete di Correlazione tra Attacchi di Cuore e Fast Food

#### Descrizione

- **Nodi**: Ogni nodo rappresenta uno stato, con attributi `rate` (tasso di attacchi di cuore) e `fastfood_count` (conteggio dei fast food).
- **Archi**: Connettono stati con differenze sia nei tassi di attacchi di cuore che nel numero di fast food inferiori a soglie predefinite (10 per i tassi di attacchi di cuore e 20 per il numero di fast food).

#### Visualizzazione

- La rete è stata visualizzata utilizzando un layout a molla.

### Rete di Correlazione tra Attacchi di Cuore e Inquinamento

#### Descrizione

- **Nodi**: Ogni nodo rappresenta uno stato, con attributi `rate` (tasso di attacchi di cuore) e `o3_mean` (livello medio di ozono).
- **Archi**: Connettono stati con differenze sia nei tassi di attacchi di cuore che nei livelli di ozono inferiori a soglie predefinite (10 per i tassi di attacchi di cuore e 5 per i livelli di ozono).

#### Visualizzazione

- La rete è stata visualizzata utilizzando un layout a molla.

### Rete di Correlazione tra Fast Food, Inquinamento e Attacchi di Cuore

#### Descrizione

- **Nodi**: Rappresentano fast food, stati (con dati di inquinamento e attacchi di cuore).
- **Archi**: Connettono fast food agli stati, stati ai dati di inquinamento e attacchi di cuore.

#### Visualizzazione

- La rete è stata visualizzata utilizzando un layout a molla.

## Misure di Analisi delle Reti

Sono state applicate varie misure di analisi delle reti, tra cui:
1. Centralità di Grado: Puoi utilizzare la centralità di grado per identificare i nodi più connessi nella rete. Ad esempio, potresti vedere se ci sono fast food o aree con alti livelli di inquinamento che sono particolarmente centrali nella rete.
2. Betweenness Centrality: Questa misura può rivelare i nodi che svolgono un ruolo chiave nel collegare altre parti della rete. Potresti utilizzare questa misura per identificare i nodi che si trovano lungo i percorsi tra le aree ad alto rischio di attacchi di cuore e le fonti di inquinamento o i fast food.
3. Coefficiente di Clustering: Questa misura può fornire informazioni sulla coesione locale della rete. Potresti analizzare se ci sono cluster di fast food o aree ad alto rischio di attacchi di cuore che sono particolarmente coesi all'interno della rete.
4. Analisi della Modularità: Questa analisi può aiutare a identificare gruppi distinti o comunità nella rete. Potresti cercare di individuare se esistono comunità di aree ad alto rischio di attacchi di cuore o di fast food che sono strettamente collegate tra loro.
5. Similarità Multiplex: Se hai dati multipli (ad esempio, dati sull'inquinamento e sulla presenza di fast food), potresti valutare la similarità tra questi diversi tipi di dati per esaminare se ci sono relazioni tra di essi e gli attacchi di cuore.
6. Small-Worldness: Questa misura può indicare se la rete ha una struttura simile a quella di un "mondo piccolo", dove i nodi sono collegati in modo relativamente breve e efficiente. Potresti esaminare se la tua rete ha questa caratteristica e cosa significa per la diffusione degli attacchi di cuore.
7. Censimento delle Triadi: Questa analisi può rivelare i pattern di connessione tra gruppi di tre nodi nella rete. Potresti cercare di individuare se ci sono configurazioni specifiche di triadi che sono associate ad aree con alti tassi di attacchi di cuore o con alta presenza di fast food o inquinamento.
8. Nucleo-Periferia: Questa analisi può distinguere tra nodi centrali (nucleo) e nodi periferici nella rete. Potresti cercare di identificare se ci sono aree con alti tassi di attacchi di cuore che sono più centrali rispetto alle aree con bassi tassi.


I risultati delle misure di analisi delle reti per la rete dei fast food per stato includono:
- **Centralità di Grado**: Misura quanto un nodo è connesso agli altri.
- **Centralità di Betweenness**: Indica l'importanza di un nodo nel controllo del flusso di informazioni.
- **Coefficiente di Clustering**: Indica il grado di aggregazione dei nodi.
- **Modularità**: Misura la struttura a comunità della rete.
- **Small-Worldness**: Misura l'efficienza della rete nel connettere i nodi.








