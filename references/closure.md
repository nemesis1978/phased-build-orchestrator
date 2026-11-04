# Fase G — Chiusura del progetto

Quando tutte le Build Phases hanno `PASS`:

- Esegui la suite finale e i test di regressione rilevanti; verifica i flussi critici reali o in un ambiente adeguato.
- Confronta il prodotto con **ogni** requisito della SPEC, registrando le eventuali deviazioni approvate.
- Aggiorna README, istruzioni d'uso, setup, manutenzione, limiti noti, sicurezza, backup/rollback quando pertinenti.
- Presenta: ciò che funziona, ciò che **non** è stato verificato, ciò che richiede intervento umano.

Non confondere «codice scritto» con «prodotto consegnato e validato».

---

# Struttura minima consigliata

```text
progetto/
├── README.md
├── AGENTS.md                     # opzionale: indica all'agente di consultare questa skill
├── docs/
│   ├── project-brief.md
│   ├── decisions.md              # progetti grandi o incerti
│   ├── SPEC.md
│   ├── BUILD_PHASES.md
│   ├── PROJECT_STATE.md
│   └── HANDOFF.md
└── [codice e test del progetto]
```

Se non puoi creare file sul filesystem, restituisci bozze Markdown con gli stessi nomi, **distinguendo** i file effettivamente creati da quelli soltanto proposti.

---

# Sicurezza e qualità

## Produzione

Chiedi approvazione specifica prima di usare credenziali, inviare messaggi, spendere denaro, modificare dati reali, pubblicare o distribuire codice, eseguire trading, cambiare infrastrutture operative.

## Segreti

Non riportare password, token o dati sensibili in log, issue, commit, SPEC o HANDOFF. Usa riferimenti a variabili d'ambiente o a un secret manager.

## Preesistente

Conserva dati e funzionalità. Per le migrazioni prepara backup, compatibilità, rollback e test.

## Esattezza

Segnala chiaramente `PASS`, `FAILED`, `BLOCKED`, `NOT RUN` e la provenienza delle evidenze. Verifica versioni, API e compatibilità correnti quando possibile; se non puoi, identifica l'incertezza.

## Autonomia

Evita domande superflue, ma non prendere decisioni irreversibili o ad alto impatto al posto dell'utente.

## Assenza di Git

Se Git non è disponibile, registra versioni e cambiamenti senza simulare commit.
