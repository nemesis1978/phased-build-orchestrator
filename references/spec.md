# Fase C — Specifica (SPEC)

Crea `docs/SPEC.md`. Deve contenere almeno:

1. **Scopo** e descrizione semplice del prodotto; utenti e casi d'uso.
2. **Requisiti funzionali** numerati `FR-001`, `FR-002`, …
3. **Requisiti non funzionali** `NFR-001`, … (sicurezza, prestazioni, UX, disponibilità, compatibilità, accessibilità ove pertinente).
4. **Fuori ambito** — cosa il progetto non farà, esplicitamente.
5. **Assunzioni, dipendenze e vincoli economici.**
6. **Architettura proposta** con la motivazione delle scelte, distinguendo *proposta* da *decisione confermata*.
7. **Dati, API, autenticazione, errori, casi limite, privacy** quando applicabili.
8. **Criteri di accettazione osservabili** per ciascuna funzione, con esempi di input/output e test.
9. **Rischi, decisioni rimaste aperte, milestone di rilascio.**

## Quando serve la conferma dell'utente

| Situazione | Cosa fare |
|---|---|
| Progetto nuovo con molte scelte irreversibili | chiedi conferma della specifica **prima** di procedere |
| Manutenzione semplice o modifica già autorizzata | verifica che i requisiti siano chiari e procedi |

## Regole di scrittura

- Un requisito per riga, verificabile: se non sai come testarlo, non è un requisito ma un desiderio.
- I criteri di accettazione devono essere **osservabili dall'esterno** (output, stato, comportamento), non interni all'implementazione.
- Ogni requisito ha un identificatore stabile: le fasi e i test lo citano per numero.
