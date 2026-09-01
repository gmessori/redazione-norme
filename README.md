# redazione-norme

Una skill per Claude che scrive e revisiona **testi normativi statali italiani**
applicando le regole di tecnica legislativa vigenti nell'ordinamento.

Non è un prompt che dice «scrivi in modo giuridico». È la trascrizione operativa
di un corpo di regole che sta in leggi dello Stato, circolari della Presidenza
del Consiglio e direttive — con la citazione puntuale della fonte per ciascuna,
così che ogni scelta di redazione e ogni correzione siano verificabili.

---

## Perché esiste

Le regole di tecnica legislativa italiana esistono, sono pubbliche e in buona
parte sono vincolanti. Il punto è che si sono stratificate nel tempo su fonti
diverse — leggi, circolari, direttive, regolamenti — adottate nell'arco di quasi
quarant'anni, per diverse centinaia di pagine complessive.

Il risultato è che tenerle tutte presenti mentre si scrive è oggettivamente
difficile, anche per chi il mestiere lo fa da anni. Sapere che l'unità minima da
sostituire con una novella è preferibilmente il comma, che «e/o» è vietata, che
la decorrenza inserita dentro una novella decorre dall'entrata in vigore
dell'atto modificato e non di quello modificante, che la clausola di neutralità
finanziaria non può essere prevista per spese di natura obbligatoria: sono tutte
regole scritte da qualche parte, e nessuna di esse è memorabile per intero.

A questo si aggiunge che il corpus si aggiorna. Alcuni riferimenti contenuti
nelle fonti più risalenti sono stati superati da normativa successiva — la
disciplina della copertura finanziaria, quella della partecipazione all'Unione
europea, la valuta stessa — mentre le regole di tecnica che quelle fonti dettano
restano pienamente valide. Distinguere i due piani richiede una ricognizione che
non è ragionevole rifare a ogni articolato.

**Da qui l'idea di questa skill: rendere sistematico un controllo a monte.** Non
sostituisce il giurista che redige, né l'istruttoria: mette a disposizione, nel
momento in cui si scrive, il corpo di regole che altrimenti andrebbe ricostruito
ogni volta, e segnala per tempo i punti su cui un testo verrebbe fermato.

## Che cosa sa fare

- **Redigere articolato ex novo** — disegni di legge, decreti-legge, decreti
  legislativi, regolamenti governativi, ministeriali e di delegificazione, testi
  unici.
- **Revisionare una bozza** restituendo il testo corretto più i rilievi, ciascuno
  con la regola applicata, la fonte puntuale e la correzione proposta, separando
  i rilievi vincolanti da quelli opportuni.
- **Scrivere preamboli**, sulla base dei modelli allegati alla Guida del DAGL,
  con le denominazioni aggiornate.
- **Gestire citazioni, rinvii, novelle e abrogazioni**: numerazione degli
  articoli e dei commi aggiuntivi, capoversi, alinea, testi unici misti,
  reviviscenza, interpretazione autentica.
- **Impostare le relazioni a corredo**: illustrativa, tecnica, ATN — con la
  griglia metodologica vigente — e AIR, con esclusioni ed esenzioni.

Prima della forma, la skill pone una domanda che il controllo redazionale da solo
non intercetta: **l'istituto che il testo istituisce esiste già
nell'ordinamento?** Se sì, la strada corretta è la novella testuale, non una
disciplina parallela. È il rilievo che di solito pesa più di tutti gli altri
messi insieme.

## Fonti di redazione

Il corpo di regole applicato dalla skill, in ordine cronologico. Comprende fonti
di rango diverso — **leggi dello Stato**, circolari della Presidenza del
Consiglio, direttive e decreti del Presidente del Consiglio — e tutte sono
pubbliche e citate puntualmente nei file di riferimento.

| Fonte | Contenuto rilevante |
|---|---|
| **Legge 23 agosto 1988, n. 400** | Tipologia e limiti degli atti normativi del Governo: decreti legislativi (art. 14), decreti-legge (art. 15), regolamenti (art. 17), testi unici compilativi (art. 17-bis), chiarezza dei testi normativi (art. 13-bis, principio generale non derogabile se non in modo esplicito) |
| **Circolare PCM 20 aprile 2001** (GU n. 97/2001) | Regole e raccomandazioni sulla formulazione tecnica dei testi legislativi, elaborate d'intesa con i Presidenti di Camera e Senato. Distingue espressamente le regole dalle raccomandazioni |
| **Circolare PCM 2 maggio 2001, n. 1/1.1.26/10888/9.92** (GU n. 101/2001, S.O. n. 105) | «Guida alla redazione dei testi normativi» del DAGL: sviluppa analiticamente le regole della circolare precedente, le estende ai regolamenti e aggiunge la parte sostanziale. Contiene i modelli di preambolo (All. 1–7) |
| **Direttiva PCM 10 settembre 2008** | Tempi e modalità dell'analisi tecnico-normativa (ATN), con la griglia metodologica |
| **Direttiva PCM 26 febbraio 2009** | Istruttoria degli atti normativi del Governo: cosa deve accompagnare lo schema perché sia iscrivibile alla riunione preparatoria del Consiglio dei ministri |
| **Legge 31 dicembre 2009, n. 196** | Copertura finanziaria delle leggi (art. 17), fondi speciali (art. 18), oneri a carico dei bilanci delle amministrazioni pubbliche (art. 19), relazione tecnica e clausole di neutralità |
| **DPCM 15 settembre 2017, n. 169** | Analisi dell'impatto della regolamentazione (AIR), verifica dell'impatto (VIR) e consultazione: ambito, esclusioni, esenzioni, fasi |
| **DPCM 30 ottobre 2024** e **circolare DAGL 14 novembre 2024** | Modifica del modello ATN e criteri per limitare il rinvio a provvedimenti attuativi, in favore di disposizioni auto-applicative |
| **Legge 10 novembre 2025, n. 167** | Semplificazione e qualità della normazione: legge annuale di semplificazione e relativi principi e criteri direttivi, valutazione di impatto generazionale (VIG), impatto di genere in AIR e VIR, digitalizzazione degli atti normativi |

Lo stato della ricognizione è **settembre 2026**. A quella data non risultano
circolari di drafting successive a quelle del 2001, e il volume del DAGL
«L'attività normativa del Governo» è aggiornato al 1° dicembre 2024. La novità
più recente è la legge 167/2025, recepita qui.

Il file `references/fonti-aggiornate.md` tiene traccia, separatamente, di due
cose: quali riferimenti contenuti nelle fonti del 2001 sono stati superati da
normativa successiva, e — altrettanto importante — quali regole di tecnica sono
invece rimaste integralmente valide.

## Struttura

```
redazione-norme/
├── SKILL.md                          il flusso di lavoro e il formato dell'output
└── references/
    ├── regole-formali.md             linguaggio, verbi, congiunzioni, maiuscole,
    │                                 sigle, commi, lettere, partizioni, allegati
    ├── citazioni-e-rinvii.md         riferimenti interni ed esterni, atti UE,
    │                                 novelle, abrogazione, deroga, reviviscenza
    ├── struttura-atti.md             titolo, preamboli e modelli, regole per tipo
    │                                 di atto, formule ricorrenti
    ├── relazioni-e-istruttoria.md    relazione illustrativa, tecnica, ATN, AIR,
    │                                 iter fino al preconsiglio
    ├── checklist-revisione.md        errori ricorrenti, ordinati per gravità
    └── fonti-aggiornate.md           stato di aggiornamento delle fonti
```

Il file principale resta breve; i riferimenti si aprono solo quando servono. Chi
scrive un preambolo non legge la checklist di revisione, e viceversa.

## Installazione

**Claude Code, Claude Desktop e Cowork.** Copia la cartella `redazione-norme/`
nella directory delle skill:

```bash
git clone https://github.com/gmessori/redazione-norme.git
cp -r redazione-norme/redazione-norme ~/.claude/skills/
```

**Come pacchetto installabile.** Comprimi la cartella con estensione `.skill` e
aprila in Claude:

```bash
cd redazione-norme && zip -r redazione-norme.skill redazione-norme/
```

**Come contesto occasionale.** Anche senza installarla, incollare il contenuto di
`SKILL.md` e del file di riferimento pertinente in una conversazione produce
buona parte del risultato.

## Un esempio di cosa cambia

Bozza in ingresso:

> 3. Qualora l'amministrazione non provvedesse nel termine di cui al precedente
> comma 2, il Dipartimento può diffidare l'amministrazione inadempiente.

Testo restituito:

> 3. Se l'amministrazione non aderisce nel termine di cui al comma 2, il
> Dipartimento la diffida ad adempiere entro un mese.

Con i rilievi: congiuntivo al posto dell'indicativo presente (circ. 20 aprile
2001, n. 4, lett. b); «precedente» da evitare nei rinvii interni (n. 11, lett.
d); «può» che qui non esprime una facoltà ma un potere doveroso (Guida § 1.8);
due denominazioni diverse per lo stesso comportamento (n. 4, lett. a). Più la
segnalazione che il termine resta privo di meccanismo per il caso di
inadempimento, che è una scelta di merito da compiere.

## Provenienza dei testi prodotti

Ogni bozza prodotta dalla skill si chiude con una riga di provenienza:

```
---
Bozza predisposta con la skill `redazione-norme` di Giulio Messori
https://github.com/gmessori/redazione-norme
```

La riga sta **nella nota di drafting, mai nell'atto**. Non entra nel titolo, nel
preambolo o nell'articolato, e la skill non usa marcatori invisibili di alcun
tipo. La ragione è pratica prima che di stile: quel testo è destinato a essere
incollato in uno schema di provvedimento e a finire, eventualmente, in Gazzetta
Ufficiale. Un marcatore inserito lì dentro ne altererebbe il contenuto e ne
comprometterebbe la ricercabilità.

Chi non vuole la riga la toglie: è una singola sezione di `SKILL.md`.

## Contributi

Questa skill nasce da un'idea e da un'esigenza pratica, non da un progetto
concluso. **È pensata per essere ampliata, e ogni contributo è benvenuto**:
correzioni, integrazioni, osservazioni, casi d'uso che non copre.

Sono particolarmente utili le segnalazioni su:

- regole citate in modo inesatto o incompleto;
- riferimenti normativi superati da normativa successiva;
- regole presentate come vincolanti che nelle fonti sono raccomandazioni, o
  viceversa — è la distinzione che più facilmente si perde;
- ambiti non ancora coperti: la normazione regionale, gli atti amministrativi
  generali, il drafting degli emendamenti, i testi consolidati.

Per le correzioni di merito è utile indicare la fonte puntuale, nella stessa
forma usata nei file: `circ. 20 apr. 2001, n. 7, lett. e` oppure `Guida § 2.3.3`.

Aprite pure una issue o una pull request. L'idea è svilupparla insieme a chi
lavora sugli stessi testi.

## Limiti

**Riguarda la normazione statale.** Per le leggi regionali il riferimento è il
manuale «Regole e suggerimenti per la redazione dei testi normativi» promosso
dalla Conferenza dei Presidenti delle Assemblee legislative delle Regioni e delle
Province autonome, che segue in parte convenzioni proprie.

**Non sostituisce il controllo di legittimità.** La skill applica regole di
tecnica e segnala adempimenti istruttori; non dice se una disposizione è
costituzionalmente legittima, se la copertura è capiente o se la scelta è
opportuna nel merito.

**Le fonti si aggiornano.** Alcune erano in movimento quando la skill è stata
scritta: i decreti attuativi della valutazione di impatto generazionale e di
genere non risultavano ancora adottati, e il DAGL aveva concluso una
consultazione pubblica sulla revisione del DPCM 169/2017. Prima di usarla su un
lavoro che dipende da quei punti conviene verificare su
[Normattiva](https://www.normattiva.it) e sul
[sito del DAGL](https://www.governo.it/it/dipartimenti/dipartimento-gli-affari-giuridici-e-legislativi/).

**Resta uno strumento di supporto.** Un articolato che esce da qui va letto da
chi se ne assume la responsabilità.

## Autore

Giulio Messori.

## Licenza

[CC BY 4.0](LICENSE). Riuso libero, anche commerciale, con attribuzione a Giulio
Messori.

I testi normativi citati sono atti ufficiali dello Stato, liberamente
utilizzabili ai sensi dell'articolo 5 della legge 22 aprile 1941, n. 633.
