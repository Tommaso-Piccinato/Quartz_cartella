Pagina iniziale: [[TPI]]

COMANDI:
- **`ls`**: Elenca i contenuti di una directory.
- **`cd`**: Cambia la directory corrente.
- **`pwd`**: Mostra il percorso della directory corrente.
- **`mkdir`**: Crea una nuova directory.
- **`rmdir`**: Rimuove una directory vuota.
- **`cp`**: Copia un file o una directory.
- **`mv`**: Sposta o rinomina un file o una directory.
- **`rm`**: Rimuove un file.
- **`touch`**: Crea un nuovo file vuoto o aggiorna la data di modifica di un file esistente.
- cat: Usato per visualizzare il contenuto di un file di testo.
- echo: Visualizza una linea di testo o variabili sullo standard output.
- less: Fornisce una capacità di paging avanzata, permettendo di visualizzare il contenuto di un file pagina per pagina.
- more: Presente sin dai primi giorni di UNIX, ha meno funzionalità rispetto a less, ma è sempre disponibile in tutte le distribuzioni Linux.
- ind: Utile per dimostrare come funziona lo Standard Error (stderr).
- sort: Usato per riordinare le righe di un file o di un input, sia in ordine alfabetico che numerico.
- head e tail: Permettono di visualizzare rispettivamente le prime o le ultime righe di un file.
- grep: Serve a filtrare le righe di un file o l'output di un altro comando che corrispondono a un determinato pattern. Per evidenziare le corrispondenze trovate, si può usare l'opzione --color, che le mostrerà in rosso.
## Standard Input, Output ed Error

- Standard Input (STDIN): Flusso di dati in ingresso, solitamente fornito dall'utente tramite la tastiera. Quando un comando richiede input, la shell permette all'utente di inserirlo come STDIN.
    
- Standard Output (STDOUT): Flusso di output generato da un comando quando viene eseguito correttamente, senza errori. Per impostazione predefinita, viene visualizzato nel terminale ed è noto anche come stream o canale #1.
    
- Standard Error (STDERR): Flusso di output che raccoglie i messaggi di errore generati dai comandi. Di default, viene visualizzato nel terminale ed è noto anche come stream o canale #2.
    
## Redirezione di File

- Per aggiungere contenuto a un file senza sovrascriverlo, si utilizzano due simboli di maggiore >>.
    
- (maggiore singolo) >: Usato per reindirizzare l'output di un comando in un file, sovrascrivendo il contenuto se il file esiste già.