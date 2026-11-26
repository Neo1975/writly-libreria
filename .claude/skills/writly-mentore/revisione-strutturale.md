# Revisione strutturale di un'opera

Guarda il libro dall'alto: architettura, scene, archi, coerenza. Il risultato
è un **appunto di tipo `revisione`** (vedi `formato.md`), più qualche commento
«sul capitolo intero» nei capitoli dove serve intervenire.

## 1. Raccogli il quadro

1. `git pull`; leggi `writly.yaml` e `opere/<opera>/opera.yaml` (in una saga
   chiedi su quale opera lavorare, o se rivedere la saga intera).
2. Leggi `struttura.yaml`: modello, atti, sezioni con guida e peso, scene.
3. Conta le parole di ogni capitolo (testo senza front-matter) e confrontale
   con `obiettivoParole` dell'opera e con il peso di ogni sezione. Se la
   struttura ha `misura: battute`, conta invece le battute con spazi (testo
   visibile, senza segni Markdown né a capo) e confrontale con le `battute`
   di ogni sezione: sono limiti precisi (spesso di un concorso), quindi segnala
   ogni sforamento e quanto spazio resta. Le scene attribuiscono i capitoli
   alle sezioni.
4. Leggi le schede dei personaggi principali (arco: partenza → arrivo; difetto,
   desideri, paure), relazioni, regole del mondo e cronologia.
5. Leggi i capitoli. Se sono molti, leggi per intero i capitoli che
   realizzano le sezioni chiave del modello (incidente scatenante, punto di
   non ritorno, crisi, climax, finale) e almeno l'inizio e la fine degli
   altri.

## 2. Domande da farti

**Tema e premessa**
- La storia mantiene la premessa: il desiderio del protagonista, l'ostacolo
  e la posta sono quelli dichiarati, e arrivano a una risposta?
- Il tema è messo alla prova da più lati (personaggi che incarnano risposte
  diverse) e il finale prende posizione, o resta solo enunciato?
- Se mancano in `opera.yaml`, proponi all'autore una formulazione da
  discutere (nell'appunto, non nel file dell'opera).

**Architettura**
- Ogni sezione del modello ha almeno una scena? Quali sono scoperte?
- Le proporzioni reggono? Un atto che pesa il doppio del previsto, un climax
  compresso in poche pagine, un primo atto che non finisce mai.
- I punti di svolta arrivano e cambiano davvero la direzione della storia?
- Il modello scelto serve questa storia, o la storia sta chiedendo altro?

**Scene**
- Scene senza obiettivo, conflitto o esito (campi vuoti, o un esito che non
  cambia niente): sono necessarie? Si possono fondere?
- Scene «non assegnate» o senza capitolo: idee in attesa o buchi?
- Il punto di vista è distribuito in modo intenzionale? Chi non ha mai il POV
  e forse dovrebbe, chi lo ha troppo.
- La causalità tiene: ogni scena nasce dalla precedente («quindi», «ma»), non
  solo «e poi»?
- Equilibrio dei registri (`polarizzazione` delle scene, se indicata):
  proporzioni fra testa, cuore e pancia per l'opera e per atto, e serie di
  tre o più scene di fila con lo stesso registro nell'ordine della storia.
  Lunghe serie di testa rallentano, di pancia stancano, di cuore appesantiscono;
  un atto senza scene di cuore rischia di non far affezionare il lettore.
  Verifica anche che il registro dichiarato corrisponda al testo della scena.

**Personaggi**
- L'arco di ogni personaggio principale è visibile nelle scene: dove si vede
  la partenza, dove viene messo alla prova il difetto, dove avviene la scelta
  che lo cambia, dove si vede l'arrivo?
- Polarizzazione del cast: centri tutti uguali (es. tutti di testa) rendono
  i conflitti piatti; centri diversi in scena creano attrito da soli. L'arco
  passa dal centro trascurato? Dove il personaggio è costretto a usarlo?
- Personaggi che compaiono e spariscono, o che non hanno una funzione.
- Le relazioni evolvono? In una saga: cosa cambia da un libro all'altro?

**Mondo e coerenza**
- Regole del mondo enunciate e poi violate o mai usate.
- Cronologia: i tempi tra le scene sono plausibili? Eventi della storia del
  mondo che contraddicono il testo.
- Schede mai usate nel testo, o elementi importanti del testo senza scheda.

**Promesse al lettore**
- Domande aperte nei primi capitoli: trovano risposta? Oggetti, segreti,
  premonizioni introdotti e poi dimenticati.

## 3. Scrivi l'appunto

`appunti/revisione-struttura-<opera>-<AAAA-MM-GG>.md`, `tipo: revisione`,
`tag: [mentore]`, `collegamenti` con gli id di personaggi e scene di cui
parli. Struttura del testo:

```markdown
## In sintesi
Tre-cinque righe: com'è il libro oggi e la cosa più importante da fare.

## Cosa funziona
## Architettura
## Scene da rivedere
- **<titolo scena>** (<capitolo>): problema, perché conta, direzione.
## Personaggi
## Coerenza e mondo
## Prossimi passi
1. … (in ordine di priorità, al massimo cinque)
```

Sii concreto: nomina scene, capitoli e personaggi; niente consigli generici
che varrebbero per qualunque libro. Se servono, aggiungi commenti «sul
capitolo intero» nei capitoli citati, così l'autore li ritrova scrivendo.

Commit (appunto e eventuali commenti), push, e in chat la sintesi.
