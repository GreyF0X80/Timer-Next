# Timer 2.0.0 — Release Notes

Data candidata: 30 luglio 2026

## Nuova release

Timer 2.0.0 è una PWA offline-first per allenamenti a intervalli, HIIT, Tabata, forza e cardio. La release consolida il motore timer accurato e completa il pacchetto per la validazione su dispositivi reali.

## Funzioni principali

- Preparazione configurabile da 0 a 30 secondi;
- Lavoro, Recupero, Giri ed Extra periodico;
- timer basato su scadenze assolute;
- pausa, ripresa e salto tra le fasi;
- progresso della fase e progresso totale;
- residuo reale dell’allenamento;
- preset HIIT, Tabata, Strength e Cardio;
- libreria workout locale;
- controlli touch con pressione prolungata;
- regolazione di Lavoro, Recupero e Durata Extra con incrementi precisi di 1 secondo;
- suoni, avvisi finali, countdown, tick e vibrazione;
- Wake Lock automatico quando supportato;
- temi Standard, KrioPlanet e Personalizzato;
- logo personale salvato in IndexedDB;
- English, Italiano e rilevazione automatica;
- installazione e utilizzo offline.

## Miglioramenti di pubblicazione

- aggiunto l’asset ufficiale `Logo-Blu.svg`;
- precache obbligatoria degli asset essenziali;
- rimozione controllata delle cache Timer obsolete;
- README di distribuzione riscritto;
- aggiunte privacy policy e guida supporto;
- completata la traduzione inglese di opzioni, messaggi e accessibilità;
- aggiunta gestione del focus per pannelli e libreria;
- impediti annunci screen reader continui del residuo;
- rimosso il blocco portrait dal manifest.

## Landscape

La schermata principale dispone ora di un layout landscape reale:

- timer e fase a sinistra;
- timeline, prossima fase, riepiloghi e controlli a destra;
- nessun riavvio del timer durante il ridimensionamento o la rotazione;
- layout compatto per telefoni e più ampio per tablet/desktop.

## Workout Builder desktop

Il layout delle card doppie usa la larghezza effettiva del drawer. I pulsanti `−` e `+` restano contenuti e il builder passa automaticamente a una colonna quando lo spazio non è sufficiente.

## Privacy

La PWA non richiede account e non invia workout, preferenze, branding o logo personale a un server Timer. I dati restano nel browser del dispositivo. I dettagli sono disponibili in `PRIVACY_POLICY.md`.

## Validazione richiesta

Il candidato deve ancora completare la matrice su iPhone, iPad, Android, tablet e desktop reali, con particolare attenzione a installazione, offline, safe area, background, audio, vibrazione, Bluetooth e Wake Lock.
