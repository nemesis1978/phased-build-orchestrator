# Prompt pronti all'uso

## Creare una nuova app o un tool

> Applica la skill Phased Build Orchestrator. La mia idea è: [DESCRIZIONE]. Inizia dalla discovery, ponimi soltanto le domande essenziali, prepara `SPEC.md` e `BUILD_PHASES.md`, non scrivere codice prima dell'approvazione del piano. Procederemo una Build Phase alla volta con test e gate di qualità.

## Iniziare una fase già approvata

> Leggi `docs/SPEC.md`, `docs/BUILD_PHASES.md`, `docs/PROJECT_STATE.md` e l'eventuale `docs/HANDOFF.md`. Verifica il repository, poi esegui esclusivamente la prossima Build Phase pronta. Mostra i risultati dei test; non avanzare se il gate non è PASS.

## Trasferire il progetto a un altro agente

> Prepara o aggiorna `docs/HANDOFF.md` e `docs/PROJECT_STATE.md` usando le evidenze del repository e dei test. Non avviare nuove fasi. Indica esattamente la Build Phase da riprendere e i controlli da rieseguire nella nuova sessione.

## Riprendere dopo un compact o una nuova sessione

> Recupera lo stato esclusivamente dai documenti persistenti e dal repository. Verifica commit, modifiche locali e test; segnala eventuali divergenze. Riprendi dal checkpoint verificato senza ripetere lavoro completato.

## Solo la specifica, niente codice

> Applica la Fase A e C: fai le domande essenziali, poi scrivi `docs/SPEC.md` con requisiti numerati e criteri di accettazione osservabili. Non pianificare ancora le fasi e non scrivere codice.
