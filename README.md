# Progetto_di_fine_anno_5M

# Documento dei requisiti:

Nome progetto → Subscription Tracker	

# 1. Introduzione
## 1.1 Scopo del documento
 E’ di definire i requisiti del progetto Subscription Tracker è un’applicazione web per il monitoraggio e la gestione degli abbonamenti personali in un unico posto.

## 1.2 Contesto del progetto
Subscription Tracker gestisce dati non volatili, prevede un sistema di autenticazione completo, offre un’interfaccia ricca con dashboard e grafici, e presenta relazioni complesse tra le entità del database.

Progettazione e implementazione di un database relazionale con almeno 4 tabelle correlate tramite chiavi esterne e relazioni 1:N e N:N.
Sviluppo di un backend in Python utilizzando il framework Flask.

Implementazione di un sistema di autenticazione e autorizzazione sicuro, con gestione delle sessioni e protezione delle password.
Creazione di un’interfaccia web dinamica e responsive, in grado di adattarsi a dispositivi desktop e mobile.

Utilizzo di Git come strumento di versionamento del codice, con commit frequenti e messaggi descrittivi.

## 1.3 Descrizione del prodotto
Subscription Tracker è un’applicazione web che permette agli utenti di registrare, organizzare e monitorare tutti i propri abbonamenti, sia digitali (es: Netflix, Spotify, Adobe, cloud storage, ecc.) sia fisici (es:palestra, riviste, trasporti).

Il problema che Subscription Tracker risolve è questo: molte persone sottoscrivono numerosi servizi in abbonamento senza sapere in modo chiaro la spesa complessiva. 
Abbonamenti dimenticati, rinnovi automatici non desiderati e mancanza di controllo sulla spesa ricorrente sono problemi quotidiani, soprattutto per i giovani che utilizzano molti servizi digitali.

Subscription Tracker offre una soluzione a questo problema con le seguenti funzionalità chiave:

Catalogo abbonamenti: l’utente registra ogni abbonamento con nome del servizio, costo, frequenza di rinnovo (settimanale, mensile, annuale), data di inizio, categoria e note personali.

Calcolo automatico delle spese: il sistema calcola in tempo reale la spesa totale mensile e annuale, tenendo conto delle diverse frequenze di rinnovo.
Dashboard visuale: una pagina principale mostra grafici interattivi con la distribuzione delle spese per categoria e l’andamento nel tempo.

Sistema di notifiche: promemoria configurabili avvisano l’utente prima di ogni rinnovo, evitando addebiti indesiderati.

Gestione condivisione: per gli abbonamenti condivisi (piani famiglia, account di gruppo), il sistema traccia i partecipanti e calcola il costo a testa che ogni persona pagherà.

Storico pagamenti: ogni abbonamento mantiene uno storico dei pagamenti effettuati, utile per il controllo delle spese nel tempo.

## 1.4 Destinatari del prodotto
Subscription Tracker si rivolge principalmente a:

Studenti e giovani adulti: spesso sottoscrivono numerosi servizi digitali (streaming musicale e video, gaming, cloud, app di produttività) e hanno bisogno di tenere sotto controllo le uscite ricorrenti con un budget limitato.

Lavoratori e professionisti: gestiscono abbonamenti sia personali che professionali (software, servizi specifici, abbonamenti a riviste specializzate) e necessitano di una visione diciamo dall’alto degli abbonamenti.

Famiglie e coinquilini: condividono abbonamenti (piani famiglia di streaming) e hanno bisogno di dividere equamente i costi.

L’interfaccia semplice e intuitiva rende Subscription Tracker accessibile anche a utenti con competenze informatiche di base.


# 2. Obiettivi generali (primari)

## 1) Autenticazione e gestione utenti
Il sistema deve permettere la registrazione di nuovi utenti tramite email e password, il login sicuro con gestione delle sessioni, e il logout. Le password devono essere memorizzate in forma cifrata. 
L’utente deve poter modificare le proprie informazioni di profilo (nome, valuta preferita) e, in futuro, eliminare il proprio account.

## 2) Gestione completa degli abbonamenti (CRUD)
L’utente deve poter creare un nuovo abbonamento specificando: nome del servizio, costo, frequenza di rinnovo (settimanale, mensile, trimestrale, annuale), data di inizio, categoria e note opzionali. 
Deve inoltre poter modificare i dati di un abbonamento esistente, eliminarlo e visualizzare la lista completa dei propri abbonamenti.

## 3) Categorizzazione degli abbonamenti
Ogni abbonamento deve essere associato a una categoria predefinita (ad esempio: Streaming Video, Streaming Musica, Software, Gaming, Fitness, Trasporti, Riviste/News). 
Le categorie devono avere un’icona e un colore distintivo per facilitare la consultazione visiva. 
L’utente potrà filtrare e raggruppare i propri abbonamenti per categoria.

## 4) Dashboard con calcolo spese
La pagina principale dell’applicazione (dashboard) deve mostrare: il totale della spesa mensile calcolato automaticamente sommando tutti gli abbonamenti attivi e normalizzando le diverse frequenze; il totale della spesa annuale stimata; il numero di abbonamenti attivi. 
I calcoli devono aggiornarsi automaticamente ogni volta che un abbonamento viene aggiunto, modificato o eliminato.

## 5) Grafici e visualizzazione dati
La dashboard deve includere almeno due grafici interattivi: un grafico a torta che mostri la distribuzione delle spese per categoria, e un grafico a barre che rappresenti l’andamento delle spese mensili negli ultimi 6-12 mesi. 
I grafici devono essere responsivi e aggiornati in tempo reale.

## 6) Ricerca e filtri
L’utente deve poter cercare un abbonamento per nome e filtrare la lista per: categoria, stato (attivo, in pausa, cancellato), intervallo di costo e frequenza di rinnovo. Deve essere possibile ordinare la lista per nome, costo crescente/decrescente o data del prossimo rinnovo.

## 7) Pagina di profilo utente
L’applicazione deve fornire una pagina profilo dove l’utente può visualizzare le proprie informazioni personali, le statistiche di utilizzo (numero totale di abbonamenti, spesa totale dalla registrazione, categoria più dispendiosa, abbonamento più longevo) e le impostazioni del proprio account.


# 2.1 Obiettivi secondari
Funzionalità aggiuntive che migliorano l’esperienza per gli utenti.

## 1) Sistema di notifiche e promemoria
Il sistema dovrebbe generare automaticamente notifiche in-app per avvisare l’utente un tot di giorni prima del rinnovo di ciascun abbonamento. 
Il numero di giorni di anticipo lo configura l’utente nelle impostazioni del profilo. 

## 2) Gestione abbonamenti condivisi
L’utente deve poter segnare un abbonamento come “condiviso” e indicare il numero dei partecipanti. 
Il sistema calcola automaticamente il costo a testa tra le persone dell’abbonamento. 

## 3) Storico pagamenti
Ogni abbonamento dovrebbe mantenere uno storico dei pagamenti effettuati, con data, importo e metodo di pagamento. 
Lo storico viene visualizzato nel dettaglio dell’abbonamento in formato timeline cronologico, ed è usato per verificare la coerenza tra il costo previsto e gli importi effettivamente pagati.

## 4) Esportazione e importazione dati
L’utente dovrebbe poter esportare la lista dei propri abbonamenti in formato CSV e il report delle spese in formato PDF. 
Inoltre, dovrebbe essere possibile importare abbonamenti da un file CSV con un formato predefinito, per facilitare la migrazione dei dati.

## 5) Messa in pausa degli abbonamenti
L’utente deve poter mettere in pausa un abbonamento senza eliminarlo. Un abbonamento in pausa non viene conteggiato nel calcolo delle spese mensili e annuali, ma resta visibile nella lista con uno stato apposito. 
L’utente può riattivarlo quando vuole.
