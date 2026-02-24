# SirioModula – Integrazione Sirio/Modula con Business Cube ⚠️ Work in Progress

Integrazione tra il sistema **Sirio/Modula** (magazzino verticale automatico) e il gestionale ERP **Business Cube**.

## 🛠️ Tecnologie
- VB.NET
- Procedure I/E di Business Cube
- Accesso diretto a tabelle ERP (`testmag`, `movmag`, `artico`, `anagra`)

## 📋 Descrizione
L'obiettivo è importare automaticamente le righe degli ordini cliente provenienti da Sirio, valorizzarle con prezzi e sconti tramite il motore delle condizioni commerciali di Business Cube, e contestualmente generare una bolla di movimentazione interna che scarica dal magazzino Modula (magazzino 5) e carica sul magazzino Business Cube (magazzino 1).

> ⚠️ Il progetto è parzialmente completato — alcune parti sono ancora in fase di sviluppo e verifica.

## ✅ Funzionalità implementate
- Validazione articolo e cliente tramite `ValCodiceDb`
- Compilazione automatica del corpo movimento (`movmag`) con dati articolo, quantità, unità di misura
- Calcolo automatico di prezzo e sconti tramite il motore `NTSCondCommerciali`
- Gestione esenzioni IVA e contropartite contabili
- Contatore righe automatico con incremento a passi di 10 (`mm_riga`)
- Struttura per inserimento testata bolla (`testmag`)
- Logging degli errori tramite `oCleImex.WriteLog`

## 🔧 Parti ancora da completare
- Reset contatore righe al cambio documento
- Completamento e verifica sintassi INSERT su `testmag` e `movmag`
- Integrazione nel flusso eventi `BeforeInsert`
- Eventuale gestione modifica descrizione commesse

## 💡 Punti di forza
- Conoscenza approfondita del modello dati interno di Business Cube
- Utilizzo del motore nativo di calcolo condizioni commerciali
- Capacità di lavorare su integrazioni complesse tra sistemi eterogenei

## 🏢 Contesto d'uso
Ambito manifatturiero / logistica — integrazione magazzino verticale automatico Modula con ERP Business Cube.

> **Nota:** Business Cube è un gestionale ERP diffuso in ambito manifatturiero italiano.
