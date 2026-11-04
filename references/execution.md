# Fase E — Esecuzione di una singola Build Phase

Prendi la prima fase in stato `TODO` con dipendenze soddisfatte.

## Sequenza

1. **Leggi il contesto**: `SPEC.md`, `BUILD_PHASES.md`, `PROJECT_STATE.md`, eventuale `HANDOFF.md` e le istruzioni del repository; controlla branch e modifiche locali.
2. **Riassumi il risultato atteso** della fase e conferma solo le decisioni realmente ambigue. Non riscrivere ciò che è già approvato.
3. **Baseline**: individua i test esistenti ed eseguili **prima** delle modifiche; registra i fallimenti già presenti.
4. **Implementa solo i cambiamenti della fase**, con patch piccole e leggibili. Dove appropriato usa i test prima del codice (TDD); non creare test tautologici che confermano soltanto l'implementazione.
5. **Esegui** test unitari, di integrazione e verifiche statiche pertinenti; aggiungi prove end-to-end per i flussi rilevanti, se fattibile.
6. **Esamina** differenze, regressioni, sicurezza, edge case, accessibilità e prestazioni quando rilevanti. Nessun comando distruttivo indiscriminato.
7. **Se una verifica fallisce**: marca `FAILED` o `BLOCKED`, correggi, ritesta. Non avanzare automaticamente.
8. **Se tutte le verifiche passano** e l'obiettivo è dimostrato: marca `PASS`, aggiorna i documenti e crea un commit **solo se autorizzato e con repo disponibile**. Nessun push, merge, deploy o pubblicazione senza autorizzazione.
9. **Riepiloga**: completato, prove, file modificati, rischi residui, prossima fase.

## Gate PASS

Servono tutte e quattro le condizioni:

- criteri di accettazione della fase verificati;
- test obbligatori superati;
- nessuna regressione critica nota introdotta;
- stato e documenti aggiornati.

Un test non eseguibile è `NOT RUN`, **non** `PASS`.

## Stati ammessi

| Stato | Significato |
|---|---|
| `TODO` | non iniziata, dipendenze potenzialmente non pronte |
| `IN_PROGRESS` | in lavorazione |
| `BLOCKED` | serve una decisione, un accesso o una dipendenza esterna |
| `FAILED` | verifiche eseguite e fallite |
| `PASS` | tutte le verifiche obbligatorie superate, con evidenze |

## Regola di continuità

Procedi alla fase successiva **solo** se il gate è `PASS` **e** l'autorizzazione dell'utente copre l'avanzamento. Altrimenti fermati e chiedi una decisione concreta.
