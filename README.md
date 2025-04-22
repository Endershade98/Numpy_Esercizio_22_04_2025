# 📊 Analisi Statistica su Dati Studenti con Python e MySQL

Questo progetto fornisce un semplice strumento per **creare**, **popolare** e **analizzare statisticamente** dati di studenti, utilizzando:

- `MySQL` per la gestione e l’archiviazione dei dati;
- `Python` per l’elaborazione;
- `NumPy` per i calcoli statistici di base.

---

## ✅ Obiettivi del progetto

- Creare un database MySQL con 3 tabelle (classi A, B, C) contenenti dati su studenti.
- Estrarre i dati numerici (`età`, `voto`) in formato `NumPy`.
- Calcolare statistiche descrittive: media, mediana, varianza, deviazione standard, correlazioni ecc.

---

## 🧱 Struttura del progetto

```bash
.
├── statistical_analysis.py              # Classe StatisticalAnalyzer per analisi dati
├── mysql_test_db.py              # Funzioni per creare e popolare il database, ed estrarre i dati
├── main.py                  # Esempio di utilizzo dell'intero sistema
├── README.md                # File di presentazione
```

## ⚙️ Setup e dipendenze
1. Requisiti Python
Assicurati di avere Python 3.9 o superiore (compatibile anche con 3.13).
2. Installazione pacchetti
Installa le dipendenze principali con:
```bash
pip install numpy mysql-connector-python
```
## 🗄️ Struttura del Database

Il database si chiama scuola e contiene 3 tabelle:

    studenti_voti_classe_a

    studenti_voti_classe_b

    studenti_voti_classe_c

Ogni tabella ha la stessa struttura:

    id: chiave primaria

    nome: nome dello studente

    corso: corso frequentato

    eta: età dello studente

    voto: voto ottenuto (float)

## 🧠 Classe: StatisticalAnalyzer

La classe StatisticalAnalyzer accetta un array NumPy 2D e offre i seguenti metodi:

    mean(axis=0|1)

    median(axis=0|1)

    std_dev(axis=0|1)

    variance(axis=0|1)

    min_value(axis=0|1)

    max_value(axis=0|1)

    correlation()

    covariance()

    summary() → dizionario riepilogativo

## 🚀 Come iniziare
1. Crea e popola il database
```bash
from db_tools import crea_tabelle_studenti
crea_tabelle_studenti()
```
2. Estrai i dati da una tabella
```bash
from db_tools import estrai_dati_numerici
dati = estrai_dati_numerici('studenti_voti_classe_a')
```
3. Analizza i dati
```bash
from analyzer import StatisticalAnalyzer

analisi = StatisticalAnalyzer(dati)
print("Media per colonna:", analisi.mean())
print("Correlazione:\n", analisi.correlation())
print("Riepilogo:\n", analisi.summary())
```
🛡️ Note di sicurezza

    Le credenziali del database sono visibili nel codice per scopi didattici. In un progetto reale, andrebbero gestite con variabili d’ambiente o un file .env.

📬 Contatti

Progetto a scopo didattico - sviluppato per esercitazione junior in analisi dati.
