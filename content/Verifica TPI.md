[[TPI]]

**==Gestione del processore==**
Troughput = numero di programmi eseguiti per unità di tempo.

**PROGRAMMA** : insieme di istruzioni ,memorizzate su memoria di massa , quindi è definito entità statica.

**PROCESSO** : istanza del programma, é eseguito dal processore quindi risiede sulla RAM ed è della entità dinamica.

L’ottimizzazione del tempo di CPU si ha con la multiprogrammazione. 

I sistemi operativi multitasking aumentano il Throughput eseguendo più processi e riducendo al minimo l’inattività della CPU.

La gestione del sistema operativo prevede:

**SCHEDULING DEI JOB**: insieme di strategie utili per la scelta dei programmi che dal disco devono essere caricati in RAM.
**SCHEDULING DELLA CPU:** insieme di strategie assegnare e sospendere l’utilizzo della CPU da parte dei vari processi.

==PROCESSI==

Ogni processo è diviso in codice e dati del programma, l’insieme dei dati di un processo viene chiamato contesto del processo.

I processi devono essere:

- Indipendenti cioè che può evolversi senza necessità di scambiare dati con altri processi.
    
- Cooperanti cioè due o più processi devono scambiarsi informazioni per evolvere.
    
- Competitori cioè due processi possono essere ostacolati per usare la stessa risorsa.
    

La situazione in cui si trova un processo rispetto alla CPU viene definita stato del processo.

I possibili stati sono: 

- New stato in cui si trova un processo appena creato.
    
- Ready se ha tutte le risorse necessarie ad eccezione della CPU.
    
- Running quando la CPU sta eseguendo le sue istruzioni.
    
- Waiting (WL)quando gli manca una risorsa per poter evolvere.
    
- Terminated quando ha termitato l’esecuzione.
    

Quando si crea un nuovo processo, gli viene assegnato un identificatore(PID) e viene inserito nell’elenco dei processi pronti(RL), quando il processo è in esecuzione può uscire per tre motivi:

- Termina l’esecuzione .
    
- Termina il suo tempo di CPU.
    
- Gli manca la disponibilità di una risorsa.
    

==GESTIONE DELLA MEMORIA==

Un programma, prima di essere caricato in memoria centrale, viene inserito in una coda di ingresso e poi trasferito in una ready List (RL). Il compilatore e il linker stabiliscono i collegamenti tra istruzioni e indirizzi logici, che diventeranno indirizzi fisici al momento del caricamento. Questo tipo di codice è definito rilocabile.

- Durante la fase di caricamento in memoria, tutti gli indirizzi del programma sono calcolati rispetto a un indirizzo base, in un processo chiamato rilocazione statica. 
    
- Durante l’esecuzione, invece, si utilizza un registro di base che contiene l’indirizzo della prima posizione di memoria centrale; gli indirizzi relativi sono quindi adattati dinamicamente sommando il valore del registro di base, in una tecnica chiamata rilocazione dinamica.
    

==MMU (MEMORY MANAGEMENT UNIT)==

È un dispositivo hardware che associa gli indirizzi virtuali a quelli fisici.

Linking e Binding

- Linking consiste nel modo di calcolare un indirizzo logico.
    
- Binding trasformare un indirizzo logico in fisico, ci sono tre modi:
    

- Indirizzamento assoluto : durante la compilazione.
    
- Rilocazione statica : nel momento del loading del programma.
    
- Rilocazione dinamica : durante l’esecuzione del programma.
    

Per caricare un programma in memoria centrale lo spazio libero deve essere :

- SUFFICIENTEMENTE GRANDE
    
- CONTIGUO
    

Oggi ci sono programmi anche più grandi della RAM del computer , quindi delle soluzioni sono:

- Scaricare i processi inattivi della RAM sul disco, detto operazione di Swapping.
    
- Caricamento dinamico, caricare in RAM alcuni moduli , solo nel momento dell’effettivo richiesta.
    
- Effettuare un frazionamento del programma, Overlay.
    
- Partizione della memoria: soluzione migliore; a ogni processo si lascia una porzione di memoria fissa di memoria per eseguire lo Swapping, riducendo la frammentazione.
    

**ALLOCAZIONE MEMORIA CON PARTIZIONAMENTO:**

==PARTIZIONE FISSA==

Quando si inizializza un sistema vengono stabilite le dimensioni delle partizioni, possono essere diverse tra loro, per ogni partizione c’è una coda che l’attesa dei job, vengono aggiunti nella coda della partizione più piccola che riesce a contenerlo.

PROBLEMI?

I problemi sono :

- Frammentazione esterna : quando un job è più grande di qualsiasi partizione ma potrebbe essere contenuto nella memoria complessiva.
    
- Frammentazione interna: quando abbiamo un job piccolo, tutte le partizioni piccole ma in grado di contenerlo hanno la coda piena, andrebbe nella coda della partizione più grande, causando uno spreco di memoria.
    

Per evitarlo ci fa uso di una singola coda d’ingresso.

- Si percorre la coda dall’inizio fino ad individuare un job che possa essere contenuto nella partizione libera.
    
- Si percorrere tutta la coda, individuando il più grande job che possa essere contenuto nella partizione libera.
    

==PARTIZIONE VARIABILE==

È possibile modificare dinamicamente sia il numero sia la dimensione delle partizioni presenti. Ci sono diverse strategie(Utilizzabili anche per partizioni fisse):

- First fit: è il metodo più veloce, il gestore della memoria scorre la tabella delle partizioni finché non ne trova una abbastanza grande per contenere il processo.
    
- Best fit:  il gestore della memoria scorre la tabella delle partizioni finché non trova la partizione più piccola che riesce a contenere il processo. È più lenta della First fit e tende a lasciare piccoli spazi di memoria liberi numeri, ,inutilizzabili.
    
- Worst fit : sceglie la zona  libera più grande.
    
- Next fit : cerca il primo spazio libero in grado di accogliere il processo partendo dallo spazio libero successivo all’ultimo processo allocato.
    

Il partizionamento dinamico è soggetto a frammentazione esterna, una possibile soluzione è quella di spostare periodicamente i processi all’interno della RAM così da ricompattare le aree di memoria libere.

==MEMORIA VIRTUALE==

- Riduzione della frammentazione della memoria 
    
- Il SO tiene in memoria centrale solo le parti del programma in uso, il resto sul disco.
    
- Caricando solo parte del programma alla volta è possibile eseguire programmi di qualsiasi grandezza.
    

==PAGINAZIONE==

Gli obbiettivi sono:

- Mantenere in memoria solo le parti necessarie
    
- Gestire piccoli porzioni di memoria
    
- Usare porzioni di memoria non contigue per lo stesso programma
    
- Non dare l’incombenza della suddivisione del programma al programmatore.
    

- La memoria fisica viene divisa in blocchi di dimensioni fissa, detti frame o pagine fisiche.
    
- Il programma è diviso in blocchi di uguali dimensioni, detti pagine o pagine logiche.
    
- Il numero di pagine logiche può essere diverso da quello delle pagine fisiche.
    
- Se il numero di pagine logiche è minore, il programma potrebbe essere caricato tutto in memoria, se quelle logiche sono di più il programma viene caricato parzialmente.
    

Il sistema operativo mantiene una tabella delle pagine dove il numero di frame è usato come indice della tabella, nella tabella sono memorizzati:

- Indirizzi fisici iniziali.
    
- Pagina occupata oppure libera.
    
- ID del processo.
    

Per ottenere un indirizzo fisico, ho bisogno di due elementi che vanno sommati(f+ d):

- Numero di pagina fisica (p), utile alla MMU che preleva l’indirizzo (f).
    
- Spiazzamento nella pagina o offset(d).
    

**PAGE FAULT** si verifica quando durante l’esecuzione di un programma viene fatto riferimento ad un’istruzione che non è presente in alcun frame. 

Swapping out di un processo vecchio e caricare la pagina logica nuova (swap in).

==PAGINAZIONE VS SEGMENTAZIONE==

- PAGINAZIONE
    

Il programma è diviso in pagine della stessa dimensione, senza tener conto della distinzione tra area del codice e area dei dati.

- SEGMENTAZIONE
    

Ogni modulo software in cui è stato suddiviso il programma svolge una funzione diversa, a ogni modulo è stata associata parte della memoria centrale di dimensione variabile.

Lo spazio degli indirizzi di un processo è diviso in segmenti logici:

- Un segmento è caricato in un frame di pari dimensione.
    
- I segmenti di un processo possono essere caricati in frame non contigui, quelli non caricati sono conservati sul disco.
    

La traduzione degli indirizzi logici in fisici avviene attraverso la tabella dei segmenti:

- Il numero di segmento è usato come indice della tabella
    

Ogni voce contiene:

- L’indirizzo base di segmento(indirizzo fisico di partenza)
    
- Limite del segmento
    

==VANTAGGI SEGMENTAZIONE==

- La gestione di strutture dati dinamiche è semplificata
    
- Viene facilitata la condivisione dei segmenti tra alcuni processi
    
- Si semplifica il Linking 
    
- Ogni segmento può avere un diverso tipo di protezione
    

==SVANTAGGI SEGMENTAZIONE==

- Frazionamento esterno della memoria.
    

**==MISTA==**
Prende le parti migliori delle due tecniche segmentazione e paginazione:

Per la paginazione:

- Identifica dei frame liberi.
    
- La scelta del frame libero in cui caricare una pagina, senza frammentazione.
    

Per la segmentazione:

- Verifica degli accessi e delle operazioni.
    
- Condivisione di porzioni di memoria.
    

La memoria centrale fisica è divisa in pagine fisiche(frame) di dimensioni fissa.

Lo spazio di indirizzamento del processo è suddiviso in segmenti logici di dimensioni diverse, ciascuno diviso in pagine logiche.