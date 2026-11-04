# Fase A — Discovery

Controlla prima se il progetto esiste già: repository, file, README, struttura, test, configurazioni, vincoli. Se non puoi accedere al progetto, **dichiaralo** invece di dedurlo.

## Cosa chiarire

Problema · utenti · funzioni indispensabili · input/output · piattaforme · interfaccia · dati e privacy · integrazioni · prestazioni · costi · ambienti · sicurezza · limiti · definizione di «finito».

## Come condurre l'intervista

1. Evidenzia le contraddizioni e fai **la domanda più decisiva**, poi aggiorna i requisiti.
2. Usa opzioni semplici quando aiutano a scegliere.
3. Non chiedere ciò che è già noto dal repository o dal contesto.
4. Per scelte tecniche **reversibili e secondarie** proponi un default, marcato come **ipotesi**, invece di bloccare il lavoro.
5. Per un progetto piccolo e chiaro salta il wayfinding: passa direttamente alla specifica.

## Output

`docs/project-brief.md` con: obiettivo, contesto, requisiti confermati, ipotesi, dubbi, vincoli, definizione di completamento.

Se non puoi creare file, restituisci una bozza Markdown chiaramente identificata come tale.

---

# Fase B — Wayfinding (solo quando serve)

Per progetti con numerose dipendenze e decisioni architetturali ancora incerte, crea una **mappa delle decisioni**, non una lista di compiti di programmazione.

Ogni voce contiene:

| Campo | Contenuto |
|---|---|
| Domanda | la decisione da prendere, formulata come domanda |
| Impatto | cosa cambia a seconda della risposta |
| Opzioni | le alternative reali, con il costo di ciascuna |
| Decisione | la scelta finale, o `APERTA` con il motivo |

**Dove registrarla:** `docs/decisions.md` locale. Se GitHub Issues o Linear sono realmente accessibili e autorizzati puoi usarli come tracker — ma **non presumere** che un tracker esterno sia connesso.

## Condizione di uscita

Le decisioni che impediscono una specifica implementabile sono risolte, oppure esplicitate come **rischi accettati**.

**In questa fase non si scrive codice applicativo.**
