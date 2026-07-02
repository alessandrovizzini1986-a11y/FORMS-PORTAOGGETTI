# FORMS-PORTAOGGETTI

Scheda di rilevazione flotta (single-file, mobile-first, vanilla JS, tema scuro).

## Scopo

Raccolta a supporto del **RSPP** (Servizio Prevenzione e Protezione): documenta la
reale possibilità di tenere **refrigerate** le borracce degli autisti durante i turni
estivi. È la base documentale per la valutazione del **rischio caldo**.

Per ogni modello di veicolo di ciascuna DS il responsabile indica: vano porta oggetti
refrigerato (Sì/No), quante bottiglie da 0,5 L entrano (0-3) e una foto obbligatoria.
All'invio i dati vengono inviati a un endpoint Google Apps Script che salva riga + foto
su Google Sheet/Drive. Fallback: WhatsApp e download riepilogo `.txt`.

## Persistenza locale (compilazione multi-sessione)

Il form salva automaticamente una **bozza per DS** in IndexedDB (nome, DS e, per ogni
modello, refrigerazione/bottiglie/foto già ridimensionata). Si può quindi compilare in
più riprese senza perdere il lavoro; la bozza viene ripristinata all'apertura e
cancellata dopo un invio riuscito. Se il browser non consente il salvataggio locale
(es. Safari in navigazione privata) viene mostrato un avviso rosso.
