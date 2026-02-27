# Java Threads: Ticket Office

Progetto Java per la simulazione di un botteghino con risorse limitate gestito tramite programmazione concorrente.

## Descrizione
Il programma modella la vendita di biglietti per un evento, dove 30 potenziali compratori competono per un numero limitato di biglietti (15). Il sistema introduce un ulteriore vincolo: la capacità del botteghino di servire al massimo 3 persone contemporaneamente.



## Funzionamento dei Thread:
* **Thread Compratore**: Ogni thread tenta di acquistare un biglietto. Se i biglietti sono esauriti o se tutti i venditori sono già occupati (3/3), il thread entra in attesa.
* **Gestione Risorse**: Quando un acquirente termina la transazione, libera un venditore; se un biglietto viene restituito, la disponibilità aumenta, risvegliando i thread in coda.

Il programma utilizza i metodi `.wait()` e `.notifyAll()` per gestire la doppia condizione di attesa: la disponibilità del bene (biglietto) e la disponibilità del servizio (venditore).

## Tecnologie e Concetti
* **Java Core**: Utilizzo della classe `Thread` e gestione dinamica tramite `ArrayList`.
* **Sincronizzazione Multi-Livello**: Controllo simultaneo di più variabili di stato (`bigliettiDisponibili` e `venditoriOccupati`).
* **Inter-thread Communication**: Coordinamento dei flussi di acquisto e restituzione per evitare deadlock e garantire l'aggiornamento corretto del database locale.
