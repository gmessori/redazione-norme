# redazione-norme

Una skill per Claude che scrive e revisiona **testi normativi statali italiani**
applicando le regole di drafting della Presidenza del Consiglio dei ministri.

Non è un prompt che dice «scrivi in modo giuridico». È la trascrizione operativa
delle regole che il Dipartimento per gli affari giuridici e legislativi (DAGL)
usa come parametro per ammettere uno schema di provvedimento alla riunione
preparatoria del Consiglio dei ministri — con la citazione puntuale della fonte
per ciascuna, così che ogni correzione sia verificabile e non opinabile.

---

## Perché esiste

Le regole di tecnica legislativa italiana esistono, sono pubbliche e sono
vincolanti. Il problema è che stanno sparse in tre atti del 2001 e del 2009, per
un totale di alcune centinaia di pagine, e che una parte dei loro agganci
normativi è invecchiata male: la Guida del DAGL cita ancora le lire, la legge
468/1978, la «legge comunitaria», le «Comunità europee».

Ne discendono due modi tipici di sbagliare.

Il primo è **non conoscerle**: si scrive un articolato ragionevole che però usa
il congiuntivo, infila «e/o», chiude con la formula abrogativa innominata, mette
la decorrenza dentro una novella. Sono errori che il DAGL corregge d'ufficio, o
che fanno tornare indietro lo schema.

Il secondo è più insidioso: **applicarle alla lettera senza sapere cosa è
cambiato**. Chi copia una clausola di copertura dalla Guida del 2001 produce una
formula che rinvia a una legge abrogata dal 2010. Chi usa il modello di preambolo
dell'Allegato 7 costruisce un regolamento di semplificazione su una norma —
l'articolo 20 della legge 59/1997 — abrogata nel novembre 2025.

Questa skill prova a risolverli entrambi. Riporta le regole con il loro numero di
origine, distingue le **regole** vincolanti dalle **raccomandazioni**, e tiene un
file dedicato a ciò che nelle fonti del 2001 non è più valido — con, altrettanto
importante, l'elenco di ciò che invece lo è rimasto integralmente.

## Che cosa sa fare

- **Redigere articolato ex novo** — disegni di legge, decreti-legge, decreti
  legislativi, regolamenti governativi, ministeriali e di delegificazione, testi
  unici.
- **Revisionare una bozza** restituendo il testo corretto più i rilievi, ciascuno
  con la regola violata, la fonte puntuale e la correzione, separando i rilievi
  vincolanti da quelli opportuni.
- **Scrivere preamboli**, sulla base dei modelli ufficiali (Allegati 1–7 della
  Guida DAGL), con le denominazioni aggiornate.
- **Gestire citazioni, rinvii, novelle e abrogazioni**: numerazione degli
  articoli e dei commi aggiuntivi, capoversi, alinea, testi unici misti,
  reviviscenza, interpretazione autentica.
- **Impostare le relazioni a corredo**: illustrativa, tecnica, ATN — con la
  griglia metodologica aggiornata — e AIR, con esclusioni ed esenzioni.

Prima di correggere la forma, la skill chiede a sé stessa una cosa che il
drafting formale non intercetta: **l'istituto che il testo istituisce esiste già
nell'ordinamento?** Se sì, la strada corretta è la novella testuale, non una
disciplina parallela. È il rilievo che di solito pesa più di tutti gli altri
messi insieme.

## Fonti

Tutte pubbliche e citate puntualmente nei file di riferimento.

| Fonte | Ruolo |
|---|---|
| **Circolare PCM 20 aprile 2001** (GU n. 97/2001) | Le regole tecniche, concordate con i Presidenti di Camera e Senato. Distingue regole e raccomandazioni |
| **Circolare PCM 2 maggio 2001, n. 1/1.1.26/10888/9.92** (GU n. 101/2001, S.O. n. 105) | La «Guida alla redazione dei testi normativi» del DAGL: sviluppa le regole e le estende ai regolamenti |
| **Direttiva PCM 26 febbraio 2009** | L'istruttoria: cosa deve accompagnare lo schema perché sia iscrivibile al preconsiglio |
| **Direttiva PCM 10 settembre 2008**, come modificata dal **DPCM 30 ottobre 2024** | La griglia dell'analisi tecnico-normativa (ATN) |
| **Circolare DAGL 14 novembre 2024** | Criteri per limitare il rinvio a provvedimenti attuativi |
| **DPCM 15 settembre 2017, n. 169** | AIR, VIR e consultazione |
| **Legge 23 agosto 1988, n. 400**; **legge 31 dicembre 2009, n. 196** | Tipologia degli atti, chiarezza dei testi (art. 13-bis), copertura finanziaria |
| **Legge 10 novembre 2025, n. 167** | Semplificazione e qualità della normazione: valutazione di impatto generazionale e di genere, legge annuale di semplificazione, digitalizzazione degli atti |

Lo stato della ricognizione è **settembre 2026**. A quella data non esiste una
guida di drafting più recente: le circolari del 2001 non sono state sostituite,
e il volume DAGL «L'attività normativa del Governo» è fermo all'aggiornamento del
1° dicembre 2024. La novità sostanziale è la legge 167/2025, che il volume non
contiene ed è recepita qui.

## Struttura

```
redazione-norme/
├── SKILL.md                          il flusso di lavoro e il formato dell'output
└── references/
    ├── regole-formali.md             linguaggio, verbi, congiunzioni, maiuscole,
    │                                 sigle, commi, lettere, partizioni, allegati
    ├── citazioni-e-rinvii.md         riferimenti interni ed esterni, atti UE,
    │                                 novelle, abrogazione, deroga, reviviscenza
    ├── struttura-atti.md             titolo, preamboli e modelli All. 1–7,
    │                                 regole per tipo di atto, formule ricorrenti
    ├── relazioni-e-istruttoria.md    relazione illustrativa, tecnica, ATN, AIR,
    │                                 iter fino al preconsiglio
    ├── checklist-revisione.md        errori ricorrenti, ordinati per gravità
    └── fonti-aggiornate.md           cosa nelle fonti del 2001 non vale più —
                                      e cosa invece è rimasto valido
```

Il file principale resta breve; i riferimenti si aprono solo quando servono. Chi
scrive un preambolo non legge la checklist di revisione, e viceversa.

## Installazione

**Claude Code, Claude Desktop e Cowork.** Copia la cartella `redazione-norme/`
nella directory delle skill:

```bash
git clone https://github.com/<utente>/redazione-norme.git
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
2001, n. 4, lett. b); «precedente» vietato nei rinvii interni (n. 11, lett. d);
«può» che non è una facoltà ma un potere doveroso (Guida § 1.8); due
denominazioni per lo stesso comportamento (n. 4, lett. a). E la segnalazione che
il termine resta privo di meccanismo per il caso di inadempimento, che è una
scelta di merito da compiere.

## Limiti

**Riguarda solo la normazione statale.** Per le leggi regionali il riferimento è
il manuale «Regole e suggerimenti per la redazione dei testi normativi» promosso
dalla Conferenza dei Presidenti delle Assemblee legislative delle Regioni, che
segue in parte convenzioni diverse.

**Non sostituisce il controllo di legittimità.** La skill applica regole di
tecnica e segnala adempimenti istruttori; non dice se una disposizione è
costituzionalmente legittima, se la copertura è capiente o se la scelta politica
è opportuna.

**Le fonti cambiano.** Il file `fonti-aggiornate.md` porta in testa la data della
ricognizione. Alcune cose erano in movimento quando è stato scritto: i DPCM
attuativi della valutazione di impatto generazionale e di genere non risultavano
ancora adottati, e il DAGL aveva chiuso una consultazione pubblica sulla
revisione del DPCM 169/2017. Prima di usare la skill su un lavoro che dipende da
quei punti, conviene verificare su [Normattiva](https://www.normattiva.it) e sul
[sito del DAGL](https://www.governo.it/it/dipartimenti/dipartimento-gli-affari-giuridici-e-legislativi/).

**Resta uno strumento di supporto.** Un articolato che esce da qui va letto da
chi se ne assume la responsabilità.

## Contributi

Segnalazioni benvenute, in particolare su: regole citate in modo inesatto,
riferimenti normativi superati, e regole presentate come vincolanti che nelle
fonti sono raccomandazioni (o viceversa) — è l'errore che più facilmente si
insinua. Per le correzioni di merito è utile indicare la fonte puntuale, nella
stessa forma usata nei file: `circ. 20 apr. 2001, n. 7, lett. e` oppure
`Guida § 2.3.3`.

## Provenienza dei testi prodotti

Ogni bozza prodotta dalla skill si chiude con una riga di provenienza:

```
---
Bozza predisposta con la skill `redazione-norme` di Giulio Messori
https://github.com/<utente>/redazione-norme
```

La riga sta **nella nota di drafting, mai nell'atto**. Non entra nel titolo, nel
preambolo o nell'articolato, e la skill non usa marcatori invisibili di alcun
tipo. La ragione è pratica prima che di stile: quel testo è destinato a essere
incollato in uno schema di provvedimento e a finire, eventualmente, in Gazzetta
Ufficiale. Un marcatore inserito lì dentro — visibile o nascosto — ne altera il
contenuto e ne compromette la ricercabilità.

Chi non vuole la riga la toglie: è una singola sezione di `SKILL.md`.

## Autore

Giulio Messori.

## Licenza

[CC BY 4.0](LICENSE). Riuso libero, anche commerciale, con attribuzione a Giulio
Messori.

I testi normativi citati sono atti pubblici, liberamente utilizzabili ai sensi
dell'articolo 5 della legge 22 aprile 1941, n. 633.
