Più programmi possono essere eseguiti sul processore anche contemporaneamente.
Sistemi operativi multi-utente (più processi e più utenti).
Sistemi operativi monoutente e multitasking.
Esempio: sistemi operativi multi-utente sia Windows che Linux.
Server può avere applicazioni che permettono a più utenti di utilizzare questi servizi.
Multitasking = programmi diversi con processi diversi contemporaneamente.
Programma in esecuzione viene chiamato processo.
Task del sistema operativo: controllo della RAM, in background 
Intero sistema è un insieme di processi che possono essere eseguiti in parallelo sui processori alternandone l’esecuzione.

Programma è una lista di istruzioni da svolgere in sequenza. In [informatica](https://it.wikipedia.org/wiki/Informatica), un programma è una sequenza di istruzioni [codificate](https://it.wikipedia.org/wiki/Codifica) in un [linguaggio](https://it.wikipedia.org/wiki/Linguaggio_di_programmazione) interpretabile da un [elaboratore](https://it.wikipedia.org/wiki/Elaboratore),

==Processo vs programma==

Un programma è costituito dalle sue istruzioni e memorizzato su una memoria di massa, non cambia nel tempo e non modifica lo stato della memoria centrale ed è un’entità statica

Un processo è un’istanza di un programma in evoluzione, cioè che è eseguito dal processore 

Quando un processo viene interrotto devo registrare il punto dove ero arrivato con i registri per poi poterla ripristinare, è un’entità dinamica.

==PROCESSI==

Lo stato di esecuzione è determinato dai valori assunti dal Program Counter (PC), dai registri di stato e utente, dalla memoria e dallo stack.

Il processo possiede una traccia di esecuzione ovvero la sequenza di stati assunti dal processore durante l’esecuzione del processo, ad un processo sono associati il suo codice, area dati e altre risorse come CPU memoria e file.

È costituito da un codice eseguibile e il suo stato, ovvero l’insieme di tutti i dati e le risorse ad esso associati.

Un programma può generare più processi, ma ogni processo è associato ad un solo programma

Processo utente è un processo generato da un programma scritto dall’utente.

Processo supervisore è un processo generato da un programma del Sistema Operativo, questi hanno una priorità e un importanza maggiore dei processi utente.

[[STRUTTURA PER GESTIRE I PROCESSI]]

PROCESSI E MEMORIA

Un processo per essere eseguito deve essere collocato in memoria centrale.

I sistemi operativi di oggi lavorano in multi programmazione cioè che ci sono più programmi in esecuzione contemporaneamente. E c’è una memoria condivisa da più processi.

È necessario gestire l’allocazione dei processi in memoria e la loro protezione in modo efficiente quindi aumentare il grado di multi programmazione e diminuire la probabilità di bloccare i processi.

Un processo può essere rimosso dalla memoria e trasferito sul disco, swap out, viceversa swap in. 

Quando il sistema operativo lo riporta in memoria lo può mettere dove era prima oppure da un’altra parte.

Lo spostamento in memoria di un processo prende il nome di ri-locazione del processo e la sua esecuzione richiede di modificare gli indirizzi del codice.

Perché se lo ricollochiamo da un’altra parte l’indirizzo è diverso.

Rilocazione può essere effettuata in diversi modi a seconda di come è stato prodotto il codice.

Bisogna esaminare la catena di programmazione ovvero le trasformazioni da programma sorgente, scritto in linguaggio macchina, a programma in esecuzione.

Compilazione 

Primo passo della catena di programmazione è la compilazione del programma, ovvero la traduzione da programma sorgente a linguaggio macchina.

Processi a singolo thread e multithread.

Il compilatore traduce il programma principale e le due procedure in tre moduli oggetto separati. Gli indirizzi all’interno di ogni modulo partono da 0.

Codice Main. Codice EstraiDati. Codice StampaDati. Questi sono i moduli oggetto.

Riferimenti esterni 

A causa delle compilazioni separate la traduzione del programma in codice macchina non può essere effettuata completamente.

Ad esempio la procedura EstraiDati nel main viene tradotta nella corretta istruzione macchina di salto a sottoprogramma, ma in essa non può essere specificato l’indirizzo di ingresso di EstraiDati.

La compilazione produce un modulo oggetto Main in cui la destinazione del salto è indicata simbolicamente: JSB EstraiDati.

In nome del simbolo usato in estrai dati è specificato in una tabella di riferimenti esterni posta nel codice oggetto del modulo main.

*==Linking==* 

Il passo successivo attuato dal link editor consiste nel collegare tra loro i diversi moduli per generare una versione completa dell’applicazione, con i moduli che la compongono collegati in sequenza e gli indirizzi in memoria modificati per tener conto del corretto punto di inizio di ogni modulo.
Il link editor è in grado di risolvere le referenze esterne per te ha visione di tutti i moduli e ne conosce le dimensioni.  
Deve anche modificare il codice dei moduli oggetto in modo da adattare gli indirizzi all’attuale collocazione in memoria. 
Il linker per costruire il modulo pronto deve eseguire due operazioni: collegamento dei moduli (mappatura) e la modifica (editing) del codice macchina. 
Comando tlink.

*==Loading==* 
Attraverso il loader si può caricare in memoria un programma pronto per l’esecuzione.
Trasforma un programma nell’immagine di un processo.
Il loader deve adeguare gli indirizzi del modulo generato dal link editor all’effettivo posizionamento in memoria del processo, deve effettuare la rilocazione del codice generato dal link editor.
Tale situazione è quella di un modulo di caricamenti rilocabile.
La fase di loading prevede il caricamento del processo in memoria.
Il link editor produce un modulo di caricamento assoluto, questa strategia vincola la posizione del processo in memoria. 
Mentre il modulo di caricamento rilocabile lo si può ricollocare di volta in volta su una porzione di memoria diversa. 

La rilocazione effettuata prima dell’esecuzione (in fase di caricamento) si chiama rilocazione statica. 
Rilocazione dinamica effettuata in fase di running.
In un ambiente multi programmato, in cui un processo può essere sospeso e rimosso dalla memoria per far spazio ad altri processi, la rilocazione statica comporta una delle due scelte:

Il processo sospeso viene riportato in memoria nella posizione originaria. Uso inefficiente della memoria.

Il processo sospeso collocato in una posizione diversa ma prima di collocarlo in memoria occorre adeguare gli indirizzi alla nuova posizione. 

Rilocazione dinamica 

Rimanda il calcolo dell’indirizzo effettivo al momento dell’esecuzione.

Il calcolo è realizzato a livello hardware.

Binding = passaggio dall’indirizzo logico a indirizzo fisico e può essere fatto durante il loading con la rilocazione statica, oppure durante l’esecuzione con la rilocazione dinamica.

Questo passaggio si definisce anche address binding. 

MMU = memory management unit, dispositivo hardware che attua il mapping, cioè associazione tra indirizzo logico e fisico. 

La memoria è parzialmente occupata dal sistema operativo e lo spazio restante è disponibile per i processi utente. 

Contenxt switching serve per ridurre i tempi. 

Allocazione contigua 

Memoria a partizioni fisse, i processi sono in coda. 

Allocazione contigua = partizioni fisse o variabili

Allocazione non contigua: segmentazione, paginazione, mista

Chiamate di sistema = agiscono sull’hardware 

Processo = codice, dati, stato della macchina, riferimenti a risorse la quale si può accedere.

Segmentation fault = calcolo indirizzo fisico va fuori dal segmento, questo interrompe l’esecuzione. 

Segmentation fault = se un indirizzo fisico calcolato punta ad un segmento che non è quello in uso 

Swap out = sia per paginazione che segmentazione, copiato dalla ram su disco fisso.

Mmu = unità gestione di memoria 

Loading, linking, link editor, MMU

Context switching = quando c’è il cambio contesto cambiano anche i registri della CPU, program counter aggiornato con il nuovo processo, lo stato del processo deve essere memorizzato sullo stack prima di essere spostato.

Page fault = durante l’esecuzione di un programma viene fatto riferimento a un’istruzione che non è presente in alcun frame