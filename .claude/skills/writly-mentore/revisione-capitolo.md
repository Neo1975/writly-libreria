# Revisione di un capitolo

## 1. Prepara il contesto

1. `git pull`.
2. Trova il capitolo: l'ordine e i titoli sono in `opere/<opera>/opera.yaml`.
   Se l'autore dice «il capitolo 3», è il terzo dell'elenco; in una saga
   chiedi quale opera, se non è chiaro.
3. Leggi il capitolo intero prima di annotare qualcosa. Leggi anche la fine
   del capitolo precedente e l'inizio del successivo, per le transizioni.
4. Rileggi `tema` e `premessa` in `opera.yaml`, se ci sono: ti dicono
   cosa il capitolo deve servire.
5. In `struttura.yaml` cerca le scene con `capitolo: <file>.md`: obiettivo,
   conflitto ed esito sono ciò che l'autore voleva ottenere. Nota la sezione
   del modello a cui appartengono (e la sua `guida`).
6. Leggi le schede dei personaggi presenti (in particolare il POV), le voci
   del mondo citate, le regole che le riguardano e il glossario.
7. Leggi i commenti già presenti: non ripetere osservazioni già fatte, e se
   l'autore ha risposto a un tuo commento precedente tienine conto.

## 2. Valuta, dal più importante al meno

**La scena funziona?** Per ogni scena del capitolo: il personaggio vuole
qualcosa di chiaro? C'è un ostacolo vero? Alla fine la situazione è cambiata
(valore che passa da positivo a negativo o viceversa)? Il capitolo realizza
obiettivo, conflitto ed esito scritti nella scheda della scena, o se ne
discosta? Se se ne discosta, è un'evoluzione da riportare nella scheda o una
scena che ha perso la strada?

**Punto di vista e focalizzazione.** Valuta la coerenza con la convenzione che
il testo ha scelto:

- **terza persona focalizzata**: narratore invisibile, punto di vista ancorato
  a un solo personaggio per scena, pensieri che filtrano nel discorso
  indiretto libero senza marcature; segnala i salti nella testa di altri
  personaggi, le informazioni che il POV non può sapere, le intrusioni
  dell'autore;
- **prima persona**: la voce deve restare credibile per età, cultura e stato
  d'animo del narratore; segnala registro e lessico che non gli
  appartengono, e il narratore che sa troppo rispetto al momento in cui
  racconta.

**Tema e premessa.** Il capitolo fa avanzare la premessa (il personaggio
si avvicina o si allontana da ciò che vuole, la posta sale)? Mette alla prova
il tema, anche di sbieco, o se ne dimentica? Segnalalo solo quando conta, con
un commento sul capitolo intero.

**Personaggi.** Agiscono e parlano secondo la scheda (valori, paure, modo di
parlare, tic, comportamento sotto stress)? Se la scheda indica la
polarizzazione, la reazione e la voce sono quelle del centro dominante,
soprattutto sotto pressione (un personaggio di pancia che si mette a
soppesare pro e contro nel momento del pericolo stona, a meno che non sia il
segno del suo cambiamento)? Se cambiano, il cambiamento è
motivato e coerente con l'arco (partenza → arrivo)? Ogni personaggio in scena
ha una ragione per esserci?

**Dialoghi.** Le battute sono distinguibili senza i nomi? Ci sono spiegazioni
mascherate da dialogo («come sai, nostro padre…»), battute che dicono tutto
invece di lasciare il sottotesto, attribuzioni ingombranti?

**Mostrare e raccontare.** Emozioni nominate invece che rese con gesti,
percezioni, scelte; ma anche il contrario: scene trascinate dove un sommario
servirebbe meglio il ritmo.

**Informazioni.** Blocchi di spiegazione (infodump) su mondo o passato che
fermano l'azione; informazioni date troppo presto o mai date quando servono.

**Ritmo.** Alternanza tra scena e sommario, lunghezza delle frasi rispetto
alla tensione, attacco e chiusura del capitolo (entra tardi, esci presto),
spinta verso il capitolo successivo.

**Continuità e mondo.** Contraddizioni con schede, regole del mondo,
cronologia o capitoli precedenti (aspetto, età, luoghi, tempi, chi sa cosa).

**Stile e frase**, per ultimi e con parsimonia: ripetizioni che stancano,
cliché, immagini confuse. Non fare correzione di bozze riga per riga: se c'è
un'abitudine ricorrente, segnalala una volta con due esempi.

## 3. Scrivi i commenti

- Da **5 a 12 commenti** per capitolo, ognuno con `citazione` precisa,
  `categoria` e un `testo` che dica: cosa succede qui, perché conta per chi
  legge, una direzione possibile. Due-sei frasi.
- **1-2 commenti «cosa funziona»**, specifici.
- **Un commento finale sul capitolo intero** (senza `citazione`): sintesi in
  poche righe, con la cosa più importante su cui lavorare.
- Formula le osservazioni come domande quando la scelta spetta all'autore
  («vuoi che il lettore sospetti di Tomas già qui?»).

Poi controlla che il file sia YAML valido, fai commit e push (vedi
`SKILL.md`) e riassumi in chat cosa hai trovato.
