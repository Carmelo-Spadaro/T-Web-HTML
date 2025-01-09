# T-Web-HTML

# Compito IUM-TWEB per il 2024-2025 / 26.11.2024

1. Introduzione
Questo compito riguarda principalmente l'applicazione delle idee presentate nel modulo sui metodi per accedere al Web e dare un senso al suo contenuto. Nel fornire una soluzione, ti viene richiesto di utilizzare i metodi e le tecniche insegnati nel modulo.
Ti viene fornito un set di dati sui film nel corso degli anni.
I dati vengono forniti come un set di file CSV.
Ti viene richiesto di creare un sistema in grado di supportare l'accesso e l'analisi da parte di fan e giornalisti (esperti).

2. Requisiti
Ecco lo schema dell'architettura richiesta. Nota che a seconda del modulo che stai seguendo (IUM-TWEB 12 crediti, IUM-TWEB 6 crediti o IUM 6 crediti) è richiesta un'architettura diversa.
L'architettura è composta da un certo numero di server, alcuni dei quali saranno scritti in Javascript (Express), alcuni in Java Spring Boot e alcuni in Python (Flask). Interagiscono con due tipi di database: MongoDB e Postgres in cui devono essere archiviati i dati Transfermarkt.

Funzionalità:
L'obiettivo del lavoro è di offrire ai fan e ai giornalisti la possibilità di accedere ai dati sui film. Devi progettare un servizio con le seguenti caratteristiche:
Una pagina HTML+Javascript+CSS+Handlebars consente di interrogare ed esplorare i dati.
I server:
IUM-TWEB (6 e 12 crediti):
Le query vengono inviate a un server centrale implementato in Express che comunicherà con altri server per l'accesso al database, almeno uno scritto in Express e uno in Java Spring Boot. Il server centrale deve essere veloce e in grado di servire migliaia di utenti, quindi non deve svolgere compiti pesanti.

I dati dovranno essere divisi in due sottoinsiemi:
i dati dinamici con una velocità di modifica ragionevolmente rapida, ad esempio le recensioni, gli incassi, ecc.
Dovrebbero essere archiviati in un MongoDB. i dati più statici, come i dati sugli attori e i loro film, i vincitori dell'Oscar, ecc. Questi dovrebbero essere archiviati
in un database PostGres (IUM-TWEB - 6 e 12 crediti)
un database MongoDB o SQL a scelta (IUM 6 crediti)
Per IUM-TWEB (6 e 12 crediti), la soluzione dovrebbe anche implementare un sistema di chat tra fan ed esperti per discutere argomenti in stanze specifiche basate su argomenti (ad esempio un film o un attore, ecc.). Questo dovrebbe essere implementato utilizzando socket.io.

3. I dati forniti
Ti vengono forniti i seguenti file di dati:
File di dati principali:
movies.csv: oltre 940.000 voci. colonne: 'id' (ID del film - chiave esterna per le altre relazioni) 'name' (titolo del film) 'date' (data di uscita) 'tagline' (lo slogan sul poster) 'description' (un breve riassunto del racconto) 'minute' (durata in minuti) 'rating'
countries.csv: oltre 693.000 voci: colonne: 'id' (ID del film) 'country' (uno dei paesi di origine - potrebbero essercene più di uno per film)
actors.csv; oltre 5,7 milioni di voci. Colonne: 'id' (ID del film) 'name' (nome dell'attore) 'role' (personaggio interpretato)
crew.csv: oltre 4,7 milioni di voci. Colonne: 'id' (ID del film) 'ruolo' (ad esempio regista) 'nome' (nome della persona)
posters.csv: oltre 940.000 voci: colonne 'id' (ID del film) 'link' (link ai poster originali del film)
releases.csv: oltre 13 milioni di voci. Colonne: 'id' (ID del film) 'paese' (paese di uscita) 'data' 'tipo' (cinematografico/digitale…) 'classificazione' (classificazione ricevuta in questo paese, ad esempio PG, ecc.)
Dati aggiuntivi (questi dati provengono da un set di dati diverso, quindi non includono l'ID del film)
The_oscar_awards.csv: oltre 10.000 voci sui candidati agli Oscar. Colonne: 'year_film' (anno di uscita del film) 'year_ceremony' (anno della cerimonia) 'category' (ad esempio attore) 'name' (nome della persona) 'film' (titolo del film) 'winner' (se ha vinto o meno)
rotten_tomatoes_reviews.csv: oltre 1,1 milioni di recensioni da Rotten Tomatoes: colonne: ['rotten_tomatoes_link' *URL della pagina di Rotten Tomatoes (aggiungi 'https://www.rottentomatoes.com/' davanti) 'movie_title' 'critic_name' 'top_critic' 'publisher_name' (dove è stata pubblicata la recensione) 'review_type' 'review_score' 'review_date' 'review_content' (il testo della recensione effettiva)

4. Analisi di dati su larga scala tramite Jupyter Notebook
Se stai seguendo IUM (6 crediti) o IUM-TWEB (12 crediti), ti verrà richiesto anche di sviluppare uno o più Jupyter Notebook che consentano l'analisi dei dati.
Jupyter Notebook dovrebbe consentire all'utente di interrogare il database per identificare un sottoinsieme di dati (ad esempio statistiche su un film specifico o un attore specifico, ecc.). È necessario utilizzare un'ampia varietà di visualizzazioni (ad esempio non solo un tipo di grafici come i grafici a barre, ma deve includere anche alcune visualizzazioni geografiche).
Non è necessario che Jupyter Notebook sia connesso a nessuno dei server (Flask, Express, ecc.) in alcun modo.
Jupyter Notebook deve essere fornito in un formato eseguito, ovvero mostrare tutti i grafici e le tabelle, non dovremmo essere tenuti a eseguirli durante la correzione.

5. Gruppi
L'incarico deve essere svolto in gruppo. L'esperienza ha dimostrato che non è realmente possibile per una persona svolgere tutto il lavoro per l'incarico, a meno che non sia un programmatore eccezionalmente competente con una precedente conoscenza della programmazione Web. Pertanto, l'incarico è organizzato sulla base del fatto che le persone debbano lavorare in gruppo. I gruppi devono essere composti da
un massimo di 3 membri
Agli studenti è anche consentito svolgere l'incarico in coppia o da soli.

Un'osservazione importante
L'incarico in sé è aperto. Potresti passare un anno a creare un fantastico sito web o a produrre analisi e visualizzazioni di dati, esaminando diverse sfumature dei dati o delle attività.
Questo non è sicuramente il punto dell'incarico. Il punto dell'incarico è verificare se padroneggi le tecnologie e le metodologie introdotte dal modulo. Pertanto assicurati di controllare i moduli di autovalutazione che ti dicono in dettaglio su cosa verrai valutato.
Inoltre, se stai seguendo il modulo da 12 crediti, assicurati di bilanciare lo sforzo
L'IUM-TWEB vale 6 crediti, ovvero ⅔ degli sforzi
La parte IUM vale 3 crediti, ovvero ⅓ dello sforzo
Assicurati che la tua parte IUM valga la metà della parte IUM-TWEB. In passato alcuni studenti si sono concentrati principalmente sulla parte IUM-TWEB, sviluppando in gran parte in modo insufficiente la parte IUM.

6. Materiale consentito - Plagio
È possibile utilizzare liberamente gli appunti delle lezioni, gli esempi delle lezioni di laboratorio e tutti i materiali utilizzati durante il modulo.
Non è possibile utilizzare codice di terze parti nell'assegnazione, ad eccezione di quanto esplicitamente fornito nelle lezioni o nelle lezioni di laboratorio. Ad esempio, è consentito utilizzare del codice fornito nelle diapositive della lezione, ma non è consentito scaricare alcun codice dal Web o utilizzare qualsiasi altro software che eseguirà una parte considerevole dell'assegnazione. Il riutilizzo non autorizzato di software di terze parti sarà considerato plagio. In caso di dubbio, chiedere il permesso al docente prima di utilizzare qualsiasi codice di terze parti. Le librerie consentite, nonostante non siano menzionate negli appunti delle lezioni, sono librerie css/js/html per migliorare l'aspetto e la sensazione di qualsiasi interfaccia (ad esempio Angular, Bootstrap, Vue, React). Tuttavia, si noti che l'uso di queste librerie deve essere limitato all'aspetto e alla sensazione dell'interfaccia, ovvero come sostituzione del codice HTML/CSS.
Non devi usare alcun supporto per l'implementazione del server o per la comunicazione con i server Express o Spring Boot. Ad esempio, non puoi usare alcuna funzione che sostituisca una chiamata Axios.
Per altre librerie, chiedi al docente prima di usarle.
L'uso di strumenti di intelligenza artificiale generativa è consentito, anzi incoraggiato. Tuttavia, sei tenuto a spiegare nel tuo report come li hai usati. Assicurati anche di comprendere appieno cosa usi perché l'esame orale metterà alla prova la tua comprensione

7. Schema di valutazione
Ogni parte dell'incarico avrà un punteggio suddiviso come segue:
25% per la documentazione nel report di progetto.
50% per l'implementazione della tua soluzione (qualità del codice e analisi dei dati). Consulta l'appendice A per ulteriori dettagli sullo schema di valutazione specifico.
25% per la correttezza dei risultati.

8. Consegna
La tua soluzione deve essere consegnata almeno una settimana prima della data dell'esame in una cartella autonoma denominata con il nome del gruppo (<MainDirectory> di seguito).

La directory deve contenere:
Il codice della soluzione (si prega di notare che ispezioneremo ed eseguiremo il codice).
L'interfaccia e la comunicazione con il server devono essere sviluppate in HTML/CSS/Javascript. Il server deve essere sviluppato in Javascript e Java SpringBoot (IUM-TWEB - 6 e 12 crediti) e/o Python (IUM - 6 crediti - e IUM-TWEB 12 crediti). Dobbiamo essere in grado di eseguire la tua soluzione senza problemi su un computer standard. Non dovrebbe essere necessario installare applicazioni, codice o librerie per eseguirla. Usa npm o pip o Gradle per assicurarti che il sistema sappia quali librerie caricare automaticamente.
Tutto il codice deve essere nella directory <MainDirectory>/solution. Si prega di notare che la qualità del codice comporta una parte rilevante del punteggio, quindi assicuratevi di scriverlo correttamente.
Un report che documenta il tuo lavoro. Il report deve essere contenuto nella directory <MainDirectory>/report/. Uno schema e un set di requisiti per il report sono forniti nell'Appendice A.
La documentazione all'interno dei file di codice (Javascript/HTML/Java/Python) deve essere di altissima qualità, sia in termini di Javadoc (o equivalente) sia in termini di documentazione Swagger per i server. Si prega di notare che questa documentazione contiene una parte rilevante di marchi, quindi assicurarsi di scriverla correttamente. Per ulteriori informazioni sulle linee guida per questo tipo di documentazione, vedere http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html
Alcuni screenshot di almeno 3 risultati di query devono essere archiviati in <MainDirectory>/queryexamples. Questi vengono utilizzati per verificare quando eseguiamo la tua soluzione che i risultati siano quelli che ti aspetteresti.
Il modulo di autovalutazione compilato. I moduli di autovalutazione sono disponibili a questi link:
IUM-TWEB
IUM
Il modulo di autovalutazione deve essere inviato anche all'interno del repository github condiviso con il docente.

8.1. Divisione del lavoro
È necessario che ogni membro del gruppo lavori su tutte le parti della soluzione. Ad esempio, è necessario che
Tutti i membri lavorino sia sulla parte IUM che su quella IUM-TWEB.
Tutti i membri lavorino sia sulla parte Express che su quella SpringBoot.

8.2. Repository Github/Gitlab privato
La soluzione deve essere fornita tramite un collegamento a un repository Gitlab o Github almeno una settimana prima della data dell'esame (ad esempio, se l'esame inizia il 27 settembre, la scadenza è alle 23:59 del 20 settembre). Qualsiasi soluzione inviata per qualsiasi motivo dopo la scadenza verrà rifiutata. Il repository deve essere utilizzato regolarmente durante lo sviluppo del progetto da tutti i membri del gruppo. Il repository verrà utilizzato durante la fase di esame per:
verificare che il progetto sia stato effettivamente sviluppato dal gruppo
fornire chiare indicazioni del contributo di ciascun membro del gruppo
Per questo motivo, ciascun membro del gruppo dovrà caricare (commit) personalmente tutte le modifiche al repository, idealmente per ogni giorno di lavoro sul progetto. Vale a dire, (i) il gruppo non deve delegare il compito di effettuare commit a un singolo membro e (ii) i commit non devono essere effettuati solo quando il codice (o una parte del codice) è completamente completato. Dovremmo vedere il lavoro intermedio, idealmente in rami separati.
Il nome dei membri del gruppo deve essere chiaramente identificabile con nome e cognome (ad esempio Giovanna Rossi invece di xyzaa). Fai molta attenzione quando hai più di un utente, ad esempio su Github, a non inviare con più identità anonime.
Puoi usare più repository github/gitlab, ognuno per una parte diversa del progetto, ad esempio un repository per ciascuno dei server, ecc.
Nota bene: se il gruppo non fornisce una registrazione soddisfacente dei commit per dimostrare l'effettivo progresso del progetto, il progetto verrà rifiutato e l'assegnazione verrà rifatta da zero.

I repository devono essere condivisi con
IUM-TWEB:
fabcira e aamshaegar e ??? su Github
Ciravegna e https://gitlab2.educ.di.unito.it/sp213763 e ??? su University Gitlab.
Solo IUM:
fabcira e ??? su Github
Ciravegna e ??? sul Gitlab dell'Università.

9. Appendice A: Schema del report e schema di valutazione
È importante che tu produca un report di alta qualità. Assicurati di non abbandonare il report all'ultimo minuto. È importante che tu non ignori le tecniche e gli esempi forniti durante le lezioni e le lezioni di laboratorio. Riferirti a loro durante le fasi di pianificazione/implementazione ti fornirà la base da cui iniziare, nonché un punto di confronto/discussione in cui le tue idee differiscono da quanto ti è già stato presentato (ad esempio, non reinventare la ruota: se è già stato fatto, riutilizzala e completala dove non è funzionale). Puoi utilizzare diagrammi per facilitare la tua spiegazione in queste sezioni, ma tieni presente che un diagramma da solo non è accettabile e deve essere accompagnato da una spiegazione/discussione.
Il tuo report deve essere organizzato secondo lo schema seguente, che è progettato per aiutarti a garantire che tutte le informazioni richieste siano fornite.
Lunghezza: massimo 5 pagine per IUM-TWEB, 4 pagine per IUM. Eventuali pagine aggiuntive saranno ignorate.

Tabella indice
[Nessun voto - FACOLTATIVO] - Puoi o meno includere una tabella indice nel tuo report. Dipende completamente da te. Non conta nel limite di pagine.

Introduzione
[Nessun voto] - Questo dovrebbe dare al correttore una guida su cosa aspettarsi dal tuo report. Rendi più semplice il lavoro del correttore essendo onesto.

Per ogni attività tecnica:
Crea una sottosezione nel tuo report per ciascuno dei requisiti tecnici. È molto importante che siano documentati individualmente seguendo esplicitamente l'organizzazione di seguito.
Soluzione:
Progettazione e motivazioni: spiega come funziona la tua soluzione e spiega perché hai scelto di progettarla in questo modo particolare. Ha vantaggi/svantaggi rispetto ad altre scelte di progettazione?
Problemi
Introduci l'attività a cui si riferisce questa sezione e le sfide che hai dovuto affrontare.
Requisiti:
In che modo questa progettazione è conforme ai requisiti specificati nel foglio di assegnazione originale? Stai soddisfacendo tutti i requisiti?
Limitazioni:
Hai pensato a situazioni eccezionali che potrebbero limitare la tua soluzione? La tua soluzione è estensibile? Può essere facilmente adattata ad altri requisiti? Ricorda che nessuna progettazione è impeccabile e va bene così!

Inoltre dovresti aggiungere:
Conclusioni
[nessun voto] - Dovresti includere qui tutte le conclusioni rilevanti a cui sei giunto collettivamente in merito al processo di progettazione della soluzione per questa parte dell'incarico, nonché tutte le lezioni apprese.
Divisione del lavoro
[Nessun voto - OBBLIGATORIO] - Tutti i membri del gruppo hanno condiviso il carico di lavoro in modo equilibrato? In che modo? Ad esempio, cosa ha fornito ogni membro? Sii preciso!
Informazioni extra
[Nessun voto - OBBLIGATORIO] - Questa sezione dovrebbe includere tutti i dettagli extra necessari per eseguire il tuo codice. Se non è necessaria alcuna configurazione extra, indicalo esplicitamente in questa sezione.
Bibliografia
[nessun voto] - Non dimenticare di citare tutte le fonti e di fare riferimento a queste nel testo, ove appropriato (ad esempio, "(...) abbiamo utilizzato le tecniche come da [1]."). Assicurati di utilizzare uno stile di formato standard. Non c'è bisogno di citare gli appunti delle lezioni o le lezioni di laboratorio.
 
Programma:
PARTE 1B - VISUALIZZAZIONE DI GRANDI QUANTITÀ DI DATI
Il linguaggio Python: introduzione al linguaggio 
Data Preparation and organisation in Python and Pandas
Data visualisation in Python (MatplotLib, Seaborn)
PARTE 2 - APPLICAZIONI WEB E TECNOLOGIE DI SUPPORTO
Architetture delle applicazioni Web: Web browser e Web server
Il Pattern MVC  per le applicazioni Web - Progettazione e sviluppo di applicazioni Web a 3 livelli basate su MVC:
Il primo livello (client dell'applicazione): HTML5, CSS, scripting lato client (JavaScript e AJAX/Axios/Fetch). Raccolta dati con HTML form
Il secondo livello: il Controller (in MVC)
Il terzo livello (logica applicativa): NodeJS, Java SpringBoot
Il quarto livello (livello del modello dei dati): accesso a database relazionali via JPA o tecniche similari e/o non relazionali (es. Mongoose). Rappresentazione e gestione di informazioni con JSON
Framework le applicazioni web (per esempio React o Flutter)
Per quanto riguarda la verifica di LABORATORIO questa si articola in:
un' applicazione web a quattro livelli composta dal backend server e da un client web possibilmente realizzato come Single Page Application; l’applicazione include una pagina web separata, realizzata secondo le linee guida di accessibilità presentate nell’insegnamento;
Un Jupyter Notebook  che permette la visualizzazione di una grande quantità di dati.




PARTE 1B:
Python: http://www.python.it/doc/newbie/
Jupyter Notebooks: https://jupyter.org/ 
Pandas: https://pandas.pydata.org/
MatplotLib: https://matplotlib.org/ 
Seaborn: https://seaborn.pydata.org/ 
PARTE 1C:
NodeJS: https://nodejs.org/ 
Express: https://expressjs.com/ 
MongoDB: https://www.mongodb.com/ 
Lezione 27: Assignment
Data aggregation service: servizio che prende dati da diverse sorgenti e le fornisce per ium tweb per un web site che permette di accedere a questi dati. Da una parte ci sono dei dati che vengono da .. dove ci sono dei critici che commentano questi film, e le persone che commentano sui film, quindi ci sono due tipi di analisi dei film. pandas è un unico data base, gli altri erano più database.
Your Assigment ium-tweb: creare un servizio che fornisce accesso informazioni sui film, attori, fan, giornalisti, o semplicemente qualcuno che vuole scegliere un film da guardare. Dovete creare un cluster di servers, avete un client sul browser, che deve essere fatto in html, javascript, css e handlebars (quindi dovete usare un template in engine)  e quello che dovete fare è un cluster di servers in cui il server principale è NodeJs che deve essere velocissimo, molto efficiente, non fate nessuna computazione sopra, e poi dei server di appoggio, da una parte può essere un Node Js che accede a Mongo e dall’altra uno SpringBoost che accede a Postgres e poi dovete fare una chat. le chat possono essere relative a un film, per esempio, o un particolare attore, che le persone creano online. Schema (disegno, mi sembra che riguarda solo ium).
Caratteristica: a lui della grafica del sito interessa poco, a lui interessa il back end e il front end come tecnologie. C’è il documento (quello che ho tradotto) che spiega le cose, lui vuole un lavoro professionale, con lo sviluppo del codice, ogni pezzo di codice commentato. Dovete dividere i dati in due subsets, i dati dinamici che vanno in Mongo e quelli dinamici che vanno in Postgres. 1730
