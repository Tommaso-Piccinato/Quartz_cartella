Per tornare alla pagina iniziale: [[TPI]]

[[PROCESSI]]
Quando un programma va in esecuzione viene creato il processo, ad un processo sono associati: codice eseguibile, spazio di memoria con i dati e lo stack, PCB(process control block ) o descrittore di processo 

PCB è una struttura apposita che contiene le informazioni relative allo stato del processo. (Slide condivise su campus )

Al PCB appartengono:

- PID, process identifier, identificatore di processo, è un valore numerico che va da 1 in poi 
- Processi copie di se stessi sono detti processi figli, mentre quello originale è detto padre.
- Indirizzo descrittore del processo che l’ha generato (puntatore).
- Priorità 
- Stato di avanzamento ovvero l’immagine nel processore (contenuto dei registri, registro flags o PSW, program counter).
- Immagine della memoria cioè le informazioni sulle aree di memoria.
- Informazioni relative allo stack.

[[PROCESSI E MEMORIA]]





