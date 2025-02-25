1) Creiamo nella cartella */tmp* due sottocartelle con il comando ==mkdir== e un file per ciascuna cartella con il comando ==touch==.
2) Con il comando **ls-l** troviamo i proprietari.
3) Usiamo il comando **ls - a** per trovare i file nascosti.
4) Per rendere privata la cartella priv-dir utilizziamo il comando **chmod -R 700 priv-dir**
5) Utilizziamo il comando **chmod o+w plub-dir** per rendere pubblico il permesso di scrittura "agli altri".


==Quesiti==
La notazione ottale è un metodo utilizzato per rappresentare e modificare i permessi dei file e delle directory in Linux. Questa notazione utilizza una sequenza di tre cifre in base 8 per specificare i permessi di accesso per tre categorie di utenti: proprietario, gruppo e altri.

I comandi chown e chgrp in Linux servono a gestire le proprietà dei file e delle directory, ma hanno scopi diversi. Chown cambia sia il proprietario che il gruppo (o solo uno di questi), mentre chgrp modifica solo il gruppo, lasciando invariato il proprietario. Entrambi supportano l'opzione `-R` per applicare le modifiche ricorsivamente. In generale, chown è più versatile, mentre chgrp è specifico per la modifica del gruppo.