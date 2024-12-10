Pagina Iniziale: [[SRI]]

Livello 2, collegamento dati.

***==FUNZIONI:==***

Framing = incapsulamento dei dati aggiungendo un’intestazione e una coda.

(Switch ha solo i primi due livelli ISO/OSI. Router ha i primi tre livelli ISO/OSI)

Incapsulamento avviene nel Pc mittente quando la PDU del livello network entra nel livello collegamento e incapsula il primo frame.

Nello switch si analizzano i Mac (intestazione del messaggio) ma non vengono decapsulati o modificati, viene letto e inoltrato il framing.

Nel router arriva il pacchetto e deve essere analizzato l’IP per poterlo inoltrare su un’altra rete, non guarda i MAC perché identificano i dispositivi locali.

Il secondo switch inoltra e poi viene decapsulato nel PC destinatario.

Indirizzamento assegnazione un indirizzo MAC hai dispositivi che viene utilizzato per il trasporto del frame.

Apertura della comunicazione: verifica che la trasmissione inizi nel momento in cui le due stazioni sono pronte, garantendo il sincronismo.

Questa fase è spesso chiamata “handshake”.
Stabilisce chi dà il clock all’altro dispositivo.
Non è sempre necessaria. 

Verifica della correttezza dei dati ricevuti e attuazione della procedura di correzione dei dati errati: questo controllo viene effettuato dalla stazione ricevente, mediante codici che il protocollo sulla stazione trasmittente inserisce nei dati.

Il CRC che sta in coda nel frame viene calcolato nel dispositivo mittente per la prima volta, quando arriva al router viene controllato che sia corretto.

Dipende dai protocolli dei router, sennò viene controllato nel PC destinatario.

Estrapolato il CRC messo a confronto con quello ricalcolato, se c’è un errore viene scartato.

==Trasparenza:== deve essere chiara la distinzione tra dati di tipo informativo, quelli del payload, e quelli di controllo. (Intestazione)

==Controllo del flusso:== il ritmo con cui i dati vengono inviati non deve superare quello con cui il ricevente è in grado di elaborarli.

==Chiusura della comunicazione:== capacità di capire quando finisce una comunicazione.

Controllo di statistiche sugli switch.

I CRC vengono utilisation per il rilevamento degli errori in più tecnologie di rete, ad esempio Eterneth e Token ring, per le reti ad anello.

Modulo 7.4.1 per vedere come si comportano gli switch, che utilizzano le tabelle degli indirizzi MAC per determinare quale porta utilizzare per inoltrare i frame.

Store-and-forward switching = riceve l’intero frame e calcola il CRC e utilizza una formula matematica per capire se ci sono errori. Se trova errori lo scarta.

Cut-through switching = inoltra il frame prima che sia completamente ricevuto.
Carattere di inizio e fine stuffing

Violazione di codifica: standard 802.3 utilizza la codifica di Manchester che associa il valore 1 a una transizione da livello alto a livello basso, e valore 0 da basso a alto. La mancanza si trasmissione è considerata violazione di codifica e può essere utilizzata per delimitare il frame.

**==Controllo degli errori==** 

**Controllo di parità** = controllo a incrociare considerando righe e colonne e il risultato viene trasmesso a destinazione insieme al frame e il destinatario rifà il calcolo e verifica con lo XOR che i bit calcolati nella coda del frame siano gli stessi 

**Controllo somma aritmetica** = checksum, somma dei bit, complemento a 1 tutto ciò che è zero diventa uno e tutto ciò che è uno diventa zero. 
Se lo XOR tra la somma e il checksum restituisce tutti 1 è corretto. 

**Controllo a ridondanza ciclica** = CRC, dati da trasmettere, calcolato il CRC nel mittente e poi viene trasmesso insieme ai dati e a destinazione viene ricevuto tutto il pacchetto, viene ricalcolato il CRC dei dati e poi confrontato con quello di prima, se sono uguali viene mandato al livello 3 network sennò viene cancellato. 

**==Protocolli comunicazione==** 

**Aprire la comunicazione:** sincronizzazione tra mittente e destinatario.
**Mantenere la comunicazione:** trasmissione dei dati.
**Chiusura comunicazione:** chiudere in modo corretto e ordinato.

Connessione punto punto, dispositivi direttamente collegati attraverso mezzo trasmissivo.

**Controllo del flusso** = insieme di procedure per gestire la velocità di trasmissione dei dati tra due nodi. Chi controlla il flusso deve avere fino al settimo livello quindi due dispositivi host. 

**Controllo utopia** = dati trasmessi in una sola direzione, il rumore è nullo quindi non ci sono disturbi che possono causare errori. Tempo di elaborazione è pari a zero, e la velocità di trasmissione è la massima possibile. 

Lo spazio di memoria per i dati ricevuti è infinito 

**Protocollo Stop and Wait** = dati trasmessi in una sola direzione, rumore nullo, spazio infinito, tempo elaborazione dei dati non è trascurabile. Bisogna aspettare la conferma del ricevente.

**Protocollo PAR** = dati trasmessi in una sola direzione, spazio di memoria per i dati ricevuti è limitato, tempo di elaborazione dati non è trascurabile, possibili disturbi nel canale di comunicazione che possono provocare errori nella trama ricevente. 

PPP (point-to-point protocol)

PPPoE

Point to point protocol over Ethernet, indica un protocollo di rete che appresenta una nuova alternativa per le connessioni Internet ad alta velocità, usato soprattutto per servizi DSL

Dial-up, connessione (rumore) dopo questo si è passati alla DSL, digital subscriber line. Linea digitale dell’abbonato 

Connessione punto punto = da un dispositivo a un altro attraverso un unico cavo. 

Dal mio dispositivo all'access point. 

Sottostato LLC fa da driver.

Il sottostrato MAC ha un’interazione con il livello fisico. 

Capitolo 6 Cisco CCNA
Topologia fisica: i dispositivi nello spazio, ad esempio nelle stanze, 
Tipologia logica: reti, 
IP PRIVATI
198.168.0.0 —> 192.168.255.255/16
172.16.0.0 —> 172.31.255.255/12
10.0.0.0 —> 10.255.255.255/8

Topologia WAN point-point 
Supporto = mezzo di trasmissione, media 

Tipologie LAN
Tipologie a stella o estese cioè collegare le stelle tra di loro, i dispositivi sono collegati a un dispositivo intermedio, switch Ethernet.

Rete scalabile: aggiungere o togliere dispositivi host 
Trouble shooting = risoluzione di guasti
Tipologie a stella una volta utilizzavano un Hub. Ora lo switch
Legacy = vecchia tecnologia ancora funzionante ma non ci sono aggiornamenti
Portante segnale continuo