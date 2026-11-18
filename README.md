# PROGETTO: COME FUNZIONA IL WEB E I PROTOCOLLI TCP/IP

**Gruppo di lavoro:** Dhanoa, Macrino, Maffeo

**Link al sito pubblicato (GitHub Pages):** <https://ambipreet.github.io/come-funziona-il-web/>

**Link al repository (Codice sorgente):** <https://github.com/ambipreet/come-funziona-il-web>

## CONSEGNA 1: Documento di Analisi e Progettazione (Fase 1)

### 1. Pubblico di riferimento e obiettivi di apprendimento

* **Target:** Studenti del biennio delle scuole superiori e compagni di indirizzi non informatici, con familiarità nell'uso quotidiano del browser ma privi di basi tecniche sulle reti di calcolatori.

* **Scelte comunicative:** Linguaggio divulgativo, chiaro e visivo, arricchito da analogie pratiche (es. la rubrica telefonica per il DNS) e accompagnato da simulatori interattivi (*learning by doing*).

* **Obiettivi di apprendimento:** Al termine della navigazione sul sito, l'utente sarà in grado di:

  1. Distinguere il ruolo di **Client** e **Server** e comprendere la funzione del **Livello Applicativo** nello stack TCP/IP.

  2. Ricostruire i passaggi che avvengono dalla digitazione di un URL nel browser fino al caricamento della pagina.

  3. Riconoscere i principali protocolli del livello applicativo e la loro funzione quotidiana (navigazione, cifratura, posta elettronica).

  4. Interpretare la struttura base di richieste e risposte HTTP insieme ai codici di stato più comuni (`200`, `403`, `404`, `500`).

### 2. Protocolli scelti e motivazione

Oltre ai due protocolli obbligatori (**HTTP** e **DNS**), il gruppo ha scelto di approfondire **HTTPS (con TLS)** e **SMTP / IMAP**.

| Protocollo | Ruolo nel sistema | Motivazione della scelta | 
| ----- | ----- | ----- | 
| **DNS** *(Obbligatorio)* | Traduzione dei nomi di dominio (es. `www.esempio.it`) in indirizzi IP numerici. | È il primo passaggio invisibile di ogni connessione web; permette di capire come il browser localizza il server corretto. | 
| **HTTP** *(Obbligatorio)* | Scambio di risorse web tramite messaggi di richiesta e risposta. | Costituisce la base del World Wide Web ed è ideale per illustrare metodi (`GET`, `POST`) e codici di stato. | 
| **HTTPS (TLS)** | Versione cifrata e sicura di HTTP tramite il protocollo TLS. | Fondamentale per l'educazione digitale quotidiana: spiega il significato del "lucchetto" nel browser e la protezione dei dati sensibili. | 
| **SMTP & IMAP** | Invio (SMTP) e ricezione/sincronizzazione (IMAP) delle email. | Dimostrano che lo stack TCP/IP non gestisce soltanto il Web, ma anche altri servizi applicativi essenziali come la posta elettronica. | 

### 3. Mappa del sito e percorso di navigazione

Il sito è un'applicazione web statica (HTML5, CSS3, JavaScript) strutturata in **4 pagine** collegate da una barra di navigazione superiore fissa (*Navbar* responsive con menu a scomparsa su smartphone) e un *Footer* con i crediti:

```
[ HOME PAGE (index.html) ] (Introduzione, obiettivi e mappa del percorso)
      │
      ├──► [ 1. TEORIA (teoria.html) ]
      │       ├── 1.1 Modello Client-Server e Stack TCP/IP
      │       ├── 1.2 Anatomia di un URL e risoluzione DNS
      │       ├── 1.3 HTTP, Metodi, Status Code e HTTPS/TLS
      │       └── 1.4 Posta elettronica: SMTP e IMAP
      │
      ├──► [ 2. LABORATORIO INTERATTIVO (laboratorio.html) ]
      │       ├── Simulatore 1: Dal click alla pagina (DNS + TLS + HTTP)
      │       └── Simulatore 2: Costruttore di richieste HTTP
      │
      ├──► [ 3. AREA STUDIO (studio.html) ]
      │       ├── Flashcard girabili di ripasso
      │       ├── Quiz di autovalutazione con feedback
      │       └── Glossario rapido ricercabile
      │
      └──► [ CREDITI ] (Footer presente in tutte le pagine)
```

* **Percorso di navigazione:** È previsto sia un percorso lineare guidato tramite pulsanti *"Prossimo step"* al fondo di ogni pagina (`Home → Teoria → Laboratorio → Studio`), sia la navigazione libera tramite il menu superiore.

### 4. Descrizione delle attività interattive e degli strumenti di studio

* **Laboratorio Interattivo (`laboratorio.html`):**

  1. *Simulatore "Dal click alla pagina":* L'utente sceglie tra tre indirizzi (`https://` sicuro, `http://` non cifrato, dominio `.xyz` inesistente) e avanza passo dopo passo osservando l'attivazione dei nodi (Browser, Resolver DNS, Web Server) e la spiegazione tecnica di ogni fase (query DNS, handshake TLS, richiesta HTTP o errore `NXDOMAIN`).

  2. *Costruttore di richieste HTTP:* L'utente combina un Metodo (`GET`, `POST`, `DELETE`) e una Risorsa (`/index.html`, `/contatti`, `/area-riservata`, `/pagina-fantasma`, `/crash-server`) e osserva in tempo reale la richiesta testuale generata e la risposta del server con status code colorato (`200`, `201`, `403`, `404`, `405`, `500`) e spiegazione.

* **Area Studio (`studio.html`):**

  1. *Flashcard interattive:* 8 carte cliccabili con animazione *flip 3D* per ripassare i concetti chiave.

  2. *Quiz di autovalutazione:* 8 domande a risposta multipla con calcolo del punteggio finale e feedback esplicativo immediato per ogni domanda.

  3. *Glossario rapido:* Elenco di 13 termini tecnici filtrabile istantaneamente tramite barra di ricerca.

### 5. Wireframe delle pagine principali

Il layout adotta un approccio **Mobile-First** con griglia flessibile CSS Grid/Flexbox (colonne affiancate su desktop, impilate verticalmente su smartphone):

```
+-------------------------------------------------------------------+
|  [LOGO] NetExplained        [Home] [1.Teoria] [2.Lab] [3.Studio]  |
+-------------------------------------------------------------------+
|   HERO SECTION (Titolo pagina + Sottotitolo + Pulsante azione)    |
+---------------------------------+---------------------------------+
|  CONTENUTO / PANNELLO SINISTRO  |  CONTENUTO / PANNELLO DESTRO    |
|  (Schede teoria / Input Client) |  (Schemi / Risposta Server)     |
+---------------------------------+---------------------------------+
|  FOOTER: Realizzato da Dhanoa, Macrino, Maffeo - GitHub Pages     |
+-------------------------------------------------------------------+
```

### 6. Ripartizione dei ruoli nel gruppo

* **Dhanoa:** Responsabile contenuti tecnici, redazione della sezione *Teoria*, verifica delle fonti ufficiali (MDN Web Docs, RFC) e pubblicazione/gestione del repository su GitHub Pages.

* **Macrino:** Responsabile struttura HTML e design CSS responsive (adattamento desktop/smartphone, palette colori e accessibilità).

* **Maffeo:** Responsabile logica interattiva JavaScript (simulatori DNS/HTTP, costruttore di richieste, flashcard, quiz e glossario) e compilazione del registro dei prompt.

## CONSEGNA 2: Piano di Implementazione e Registro dei Prompt (Fasi 2 e 3)

### Parte A: Piano di implementazione e modifiche apportate dal gruppo

* **Struttura dei file:** 4 pagine HTML (`index.html`, `teoria.html`, `laboratorio.html`, `studio.html`) e un foglio di stile centralizzato (`css/style.css`).

* **Modifiche fatte dal gruppo al piano iniziale proposto dall'IA:**

  1. *Semplificazione dell'architettura:* L'IA aveva inizialmente proposto di usare framework esterni (Bootstrap) e numerosi file JavaScript separati. Il gruppo ha scelto di usare **CSS puro e JavaScript vanilla** per mantenere il progetto leggero, leggibile ed evitare problemi di percorsi su GitHub Pages.

  2. *Controllo manuale delle animazioni:* Nel simulatore DNS/HTTP l'IA aveva previsto un'animazione automatica a tempo. L'abbiamo sostituita con un avanzamento manuale tramite pulsante **"Passo successivo"** per consentire agli studenti di leggere ogni passaggio con calma.

  3. *Selezione mirata dei protocolli:* Abbiamo limitato l'approfondimento ai protocolli più significativi per il biennio (**HTTP, DNS, HTTPS/TLS, SMTP/IMAP**), evitando protocolli meno immediati per i non addetti ai lavori come FTP o SSH.

### Parte B: Registro dei prompt principali (Fase 3)

| Passo | Strumento | Sintesi del Prompt inviato | Esito | Correzioni / Note del gruppo | 
| ----- | ----- | ----- | ----- | ----- | 
| **1** | Gemini | *"Crea la struttura base HTML e il file css/style.css responsive per un sito statico di 4 pagine (Home, Teoria, Laboratorio, Studio) con navbar mobile e footer."* | Positivo | Verificata la chiusura corretta del menu hamburger su schermi smartphone. | 
| **2** | Gemini | *"Genera il contenuto di teoria.html spiegando Client-Server, stack TCP/IP, URL, DNS, HTTP/HTTPS e SMTP/IMAP a studenti del biennio."* | Parziale | Controllata e rifinita la distinzione tra livelli TCP/IP e modello ISO/OSI prima della pubblicazione. | 
| **3** | Gemini | *"Sviluppa laboratorio.html con due simulatori interattivi: viaggio passo-passo DNS+TLS+HTTP e costruttore di richieste HTTP con status code colorati."* | Positivo | Aggiunto lo scenario di errore DNS (`NXDOMAIN`) per rendere più completa la simulazione. | 
| **4** | Gemini | *"Crea studio.html con 8 flashcard girabili in CSS, un quiz di 8 domande con punteggio e spiegazione errori, e un glossario filtrabile in JS."* | Positivo | Testato il filtro di ricerca del glossario verificando che funzionasse sia con maiuscole che con minuscole. | 

## CONSEGNA 3: Link di Pubblicazione (Fase 4)

* **Sito web pubblicato su GitHub Pages:** <https://ambipreet.github.io/come-funziona-il-web/>

* **Repository GitHub con codice sorgente:** <https://github.com/ambipreet/come-funziona-il-web>

## CONSEGNA 4: Relazione di Verifica Critica (Fase 4)

### 1. Errori e imprecisioni dell'IA individuati e corretti

Durante la fase di revisione tecnica dei testi e del codice generati dall'IA, confrontando i contenuti con la documentazione ufficiale (**MDN Web Docs**, **RFC IETF**) e il libro di testo, il gruppo ha individuato e corretto le seguenti imprecisioni:

1. **Confusione tra stack TCP/IP e modello ISO/OSI:**

   * *Imprecisione dell'IA:* Nelle prime bozze teoriche l'IA tendeva a mescolare i 7 livelli del modello ISO/OSI (citando Sessione e Presentazione) all'interno dello stack TCP/IP.

   * *Correzione:* Abbiamo chiarito esplicitamente che lo stack TCP/IP si articola in 4 livelli (Applicazione, Trasporto, Internet, Accesso alla Rete) e che i protocolli web operano direttamente nel Livello Applicazione sopra TCP/UDP.

2. **Uso improprio di SSL al posto di TLS:**

   * *Imprecisione dell'IA:* In alcune spiegazioni HTTPS veniva descritto come "HTTP protetto da SSL".

   * *Correzione:* Verificando su MDN Web Docs e RFC 8446, abbiamo corretto il riferimento indicando **TLS (Transport Layer Security)** come standard attuale, poiché SSL è deprecato da anni.

3. **Distinzione tra i codici di stato HTTP 401 e 403:**

   * *Imprecisione dell'IA:* Nel simulatore HTTP occorreva distinguere con precisione il significato dei codici della famiglia `4xx`.

   * *Correzione:* Su MDN Web Docs abbiamo verificato che `403 Forbidden` indica che il server rifiuta di autorizzare la richiesta per mancanza di permessi (diversamente da `401 Unauthorized` che riguarda la mancata autenticazione), adeguando la descrizione nel simulatore.

4. **Semplificazione del funzionamento del DNS:**

   * *Imprecisione dell'IA:* Il testo iniziale lasciava intendere che esistesse un unico server DNS centrale interrogato dal browser.

   * *Correzione:* Abbiamo precisato che il DNS è un sistema gerarchico e distribuito interrogato tramite un resolver.

5. **Distinzione dei ruoli tra SMTP e IMAP nella posta elettronica:**

   * *Imprecisione dell'IA:* Nelle risposte sintetiche l'IA rischiava di sovrapporre le funzioni dei protocolli email.

   * *Correzione:* Abbiamo distinto nettamente **SMTP** (usato per l'invio e l'inoltro dei messaggi) da **IMAP** (usato per la lettura e la sincronizzazione delle cartelle sul server).

### 2. Limiti riscontrati negli strumenti di IA

* **Coerenza tra file multipli:** Lavorando su più pagine HTML separatamente, è fondamentale mantenere identici i nomi dei file, dei collegamenti nel menu di navigazione e dei percorsi dei fogli di stile (`css/style.css`), altrimenti l'IA può generare collegamenti rotti.

* **Calibrazione del livello didattico:** Senza istruzioni precise sul target (studenti del biennio), l'IA tende a produrre testi troppo tecnici o, al contrario, eccessivamente semplificati.

### 3. Cosa il gruppo rifarebbe diversamente

* Definire fin dall'inizio un template fisso per intestazione e piè di pagina prima di generare le singole pagine, in modo da evitare modifiche ripetute su tutti i file HTML.

* Dedicare più tempo alla progettazione grafica su carta dei simulatori prima di passare alla scrittura del codice.

### 4. Contributo di ciascun componente del gruppo

* **Dhanoa:** Ha curato la stesura e la revisione tecnica della sezione *Teoria* confrontando i contenuti con MDN Web Docs e il libro di testo, e ha gestito il caricamento dei file e la pubblicazione su GitHub Pages.

* **Macrino:** Ha curato l'impaginazione delle 4 pagine HTML e il foglio di stile `css/style.css`, verificando la resa grafica e la navigabilità su computer e smartphone.

* **Maffeo:** Ha curato l'implementazione e il test delle componenti interattive in JavaScript (`laboratorio.html` e `studio.html`), verificando il funzionamento dei simulatori, del quiz e del glossario e documentando i prompt utilizzati.
