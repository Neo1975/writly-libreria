# Formato del progetto Writly

## Dove sono le cose

```
writly.yaml                          titolo, tipo (racconto | romanzo | saga), lingua, opere in ordine di lettura
opere/<opera>/opera.yaml             titolo, tema, premessa, obiettivoParole, capitoli in ordine (file + titolo)
opere/<opera>/capitoli/<file>.md     front-matter (id, stato) + testo in Markdown
opere/<opera>/struttura.yaml         modello narrativo dell'opera (atti → sezioni) e scene
opere/<opera>/commenti/<file>.yaml   commenti al capitolo <file>.md   ← ci scrivi tu
personaggi/<slug>.md                 scheda personaggio (front-matter) + biografia
relazioni.yaml                       relazioni tra personaggi (da, a, tipo, nota, libri)
mondo/categorie.yaml                 categorie del mondo e i loro campi
mondo/<categoria>/<slug>.md          voce del mondo (luogo, cultura, oggetto…) + descrizione
mondo/regole.yaml                    regole del mondo (testo + voci a cui si applicano)
mondo/cronologia.yaml                calendario ed eventi della storia del mondo
glossario.yaml                       termini inventati del progetto
appunti/<slug>.md                    appunti dell'autore                 ← ci scrivi tu (tipo: revisione)
dizionario.txt                       parole accettate dal controllo ortografico
```

Il **tema** (di cosa parla davvero la storia, sotto la trama) e la
**premessa** (l'idea da cui parte: chi, cosa vuole, cosa glielo impedisce,
cosa rischia) sono in `opera.yaml`, facoltativi: sono la bussola
dell'autore, usali come metro in ogni revisione.

Il **titolo di un capitolo** sta solo in `opera.yaml`; nel file del capitolo il
front-matter ha `id` e `stato` (bozza, in-stesura, scritto, revisionato).

Gli **id** collegano i file: una scena ha `pov`, `luogo` e `personaggi` con gli
id delle schede (il campo `id` nel front-matter di personaggi e voci), e
`capitolo` con il nome del file del capitolo (es. `capitolo-3.md`). Un id che
non corrisponde a nessuna scheda è un riferimento a qualcosa che è stato
eliminato.

### Scene (`struttura.yaml`)

```yaml
modello: { id: viaggio-eroe, nome: Viaggio dell'eroe }
misura: battute                   # facoltativo: senza, le sezioni si misurano in percentuale (peso)
atti:
  - id: atto-1
    nome: Partenza
    sezioni:
      - { id: mondo-ordinario, nome: Mondo ordinario, guida: "…", peso: 10, battute: 1500 }
        # peso = % indicativa del libro; con «misura: battute» vale invece «battute»,
        # la lunghezza esatta della sezione in battute con spazi (un vincolo, non una stima)
scene:
  - id: s1
    titolo: L'arrivo al molo
    sezione: mondo-ordinario      # null = non ancora assegnata
    capitolo: capitolo-1.md       # null = non ancora scritta
    stato: scritta                # idea | pianificata | in-stesura | scritta | revisionata
    sinossi: "…"
    obiettivo: "cosa vuole il personaggio POV nella scena"
    conflitto: "cosa glielo impedisce"
    esito: "come cambia la situazione"
    pov: iris                     # id del personaggio
    luogo: molo-vecchio           # id della voce del mondo
    quando: "la notte dopo il naufragio"
    personaggi: [iris, tomas]
```

### Schede personaggio (`personaggi/<slug>.md`)

Front-matter: `id`, `nome`, `alias` (altri nomi con cui compare nel testo),
`ruolo`, `eta`, e i gruppi `fisico` (aspetto, tratti, abbigliamento), `morale`
(valori, paure, desideri, difetto, segreto), `comportamento` (parlare, tic,
abitudini, stress), `arco` (partenza, arrivo). Dopo il front-matter, la
biografia.

## Scrivere commenti: `opere/<opera>/commenti/<capitolo>.yaml`

Il file ha il nome del capitolo con `.yaml` al posto di `.md`. Se non esiste,
crealo. Aggiungi i tuoi commenti **in fondo** all'elenco, senza toccare gli
altri.

```yaml
# Commenti al capitolo (Writly). Ogni commento cita il passaggio a cui si riferisce.
commenti:
  - id: c4k9x2m                      # «c» + 6-7 lettere minuscole o cifre, unico nel file
    tipo: mentore                     # sempre «mentore» per i tuoi
    autore: Claude
    creato: 2026-11-18T10:30:00Z      # data e ora UTC
    categoria: punto di vista         # vedi l'elenco sotto
    citazione: "Iris sapeva che Tomas mentiva, e lo sapeva anche lui"
    prima: "Il vento portava sale."   # 5-8 parole subito prima, per distinguere le ripetizioni
    dopo: "Poi la lanterna si spense." # 5-8 parole subito dopo
    testo: |
      Qui entriamo nella testa di Tomas («lo sapeva anche lui») in una scena
      con POV di Iris: il lettore perde per un attimo il punto d'appoggio.
      Se vuoi che resti ambiguo, puoi farlo trapelare da un gesto di Tomas
      che Iris nota.
    risolto: false
```

**La citazione è ciò che ancora il commento al testo**, quindi:

- copia il testo **come si legge**, senza i segni Markdown: niente `*`, `_`,
  `**`, `#`, `>` e niente barre rovesciate di escape. Spazi e a capo non
  contano, apostrofi e virgolette tipografiche nemmeno;
- scegli un passaggio breve e preciso: da qualche parola a una frase o due,
  al massimo un paio di paragrafi;
- se il passaggio compare più volte nel capitolo, `prima` e `dopo` dicono
  quale; altrimenti puoi ometterli;
- per un'osservazione sul capitolo intero ometti `citazione` (e `prima`,
  `dopo`): l'app la mostra come «sul capitolo intero».

Se l'autore riscrive il passaggio, l'app mostra il commento come «passaggio non
più nel testo»: è normale, non serve aggiornarlo.

Per rispondere a un commento dell'autore aggiungi in quel commento:

```yaml
    risposte:
      - { tipo: mentore, autore: Claude, creato: 2026-11-18T10:40:00Z, testo: "…" }
```

**Categorie** (una per commento, facoltativa): `struttura`, `scena`,
`punto di vista`, `personaggio`, `dialogo`, `ritmo`, `mostrare e raccontare`,
`informazioni`, `continuità`, `mondo`, `stile`, `cosa funziona`.

Controlla che il file sia YAML valido prima del commit (per esempio
rileggendolo con un parser YAML): un file illeggibile blocca i commenti
nell'app finché non viene corretto.

## Scrivere un appunto di revisione: `appunti/<slug>.md`

```markdown
---
id: revisione-struttura-il-molo-2026-11-18
titolo: "Revisione strutturale: Il molo (18 novembre 2026)"
tipo: revisione
tag: [mentore]
creato: 2026-11-18
collegamenti: [iris, s4]              # id di personaggi, voci del mondo o scene di cui parla
---

Testo in Markdown. Per rimandare a un altro appunto: [[Titolo dell'appunto]].
```

`id` e nome del file coincidono (minuscole, cifre e trattini), unici nella
cartella `appunti/`.
