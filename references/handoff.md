# Fase F — Handoff e gestione del contesto

Aggiorna `docs/PROJECT_STATE.md` e produci `docs/HANDOFF.md` quando:

- termina una fase significativa;
- stai per cambiare agente o sessione;
- il contesto è diventato troppo ampio.

Non affidarti alla sola memoria del modello.

## Gestione del contesto

Non esiste una soglia universale di token: la finestra utile e l'eventuale `/compact` dipendono dal modello e dalla piattaforma. Se puoi, controlla l'utilizzo reale e il limite effettivo; prepara l'handoff **prima** della saturazione, preferibilmente dopo un checkpoint verificato. Se la piattaforma non offre compact, apri una nuova sessione usando i documenti di stato.

`Handoff` non implica automaticamente l'apertura di una nuova sessione, e `compact` non sostituisce i file persistenti.

## Template `docs/HANDOFF.md`

```md
# Handoff — [nome progetto]
- Data/ora e ambiente: ...
- Scopo del progetto: ...
- Repo / branch / HEAD commit: ... (oppure: non disponibili)
- Specifica autorevole: docs/SPEC.md
- Piano autorevole: docs/BUILD_PHASES.md
- Fase attiva e stato: BP-00X — PASS / FAILED / BLOCKED / IN_PROGRESS
- Fasi completate: ...
- Modifiche principali e file coinvolti: ...
- Decisioni prese e motivi: ...
- Test eseguiti: [comando] → [risultato osservato]
- Test non eseguiti e perché: ...
- Bug, rischi, debito tecnico: ...
- Stato di Git: modifiche non committate / commit / conflitti
- Azioni vietate o da non ripetere: ...
- Prossimo passo esatto: ...
- Comando/istruzione di ripresa: "Leggi SPEC, BUILD_PHASES, PROJECT_STATE e HANDOFF; verifica repository e test; poi riprendi BP-00X rispettando i gate."
```

## Template `docs/PROJECT_STATE.md`

Stato del progetto · ambiente · branch/commit verificati · ultima fase `PASS` · fase in corso · test baseline · blocchi · decisioni pendenti · percorso dei documenti · ultima data di aggiornamento.

È la **fotografia sintetica corrente**; `HANDOFF.md` è il **messaggio di consegna** per il prossimo agente.

## Ripresa in una nuova sessione o con un nuovo agente

1. Leggi i quattro documenti (`SPEC`, `BUILD_PHASES`, `PROJECT_STATE`, `HANDOFF`).
2. Confronta l'handoff con lo stato **reale** di codice, branch, test e issue.
3. Se c'è contraddizione, **non scegliere alla cieca**: segnala il conflitto e verifica.
4. Riparti dalla fase indicata, senza rigenerare da zero la specifica e senza dichiarare concluso ciò che non è dimostrato.
