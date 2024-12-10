Pagina iniziale: [[TPI]]

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

