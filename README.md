# 🍕 Le vendite di una pizzeria in un anno

![Pizzeria](copertina.png)

Progetto di **Francesco Autorino** – Data Analyst.

🛠️ Strumenti: **Excel · Power BI** (Python solo per scaricare e pulire i dati)

📊 Dati: **21.350 ordini**, **48.620 righe**, **49.574 pizze**, anno 2015.

⚠️ È una pizzeria **fittizia** creata da Maven Analytics per esercitarsi. Prezzi in dollari.

---

## 🧭 1. Il progetto in breve

❓ **La domanda**: come va la pizzeria e cosa si può migliorare?

Le 5 domande più piccole:

1️⃣ 💰 Quanto incassa, e come cambia nei mesi?

2️⃣ ⏰ In quali giorni e a che ora arrivano gli ordini?

3️⃣ 🍕 Quali pizze incassano di più e quali di meno?

4️⃣ 📏 Quali taglie e categorie rendono di più?

5️⃣ 🛒 Quante pizze ci sono in un ordine?

---

## 🎯 2. I risultati principali

💰 **817.860 $** in un anno. Scontrino medio **38,31 $**.

📅 Circa **60 ordini al giorno**, aperto 358 giorni.

⏰ Picchi a **pranzo (12-13)** e a **cena (17-18)**. Il **venerdì** è il giorno migliore, la domenica il più calmo.

🍕 Prima: **Thai Chicken** (43.434 $). Ultima: **Brie Carre** (11.588 $, solo 490 pizze).

📏 La taglia **L** fa il **46%** dei ricavi. La **XXL** quasi mai venduta (0,1%).

🥗 Le 4 categorie sono quasi pari: dal 24% al 27% dei ricavi ciascuna.

🛒 **2,3 pizze per ordine**. Il **38%** degli ordini ha una pizza sola.

---

## 🛠️ 3. Perché questi strumenti

📗 **Excel**: formule, mappa di calore giorno × ora, classifica del menu, controlli automatici.

📊 **Power BI**: dashboard interattiva con filtri per categoria, taglia e mese.

🐍 **Python**: solo per scaricare i 4 file e unirli in una tabella pulita.

---

## 🔄 4. Il percorso dei dati

```
GitHub (copia Maven)     01_scarica.py           02_pulizia.py             ANALISI
4 file CSV ───────────► ❌ 1GrezziNonPuliti ───► ✅ 2Puliti ──────────┬──► 📗 Excel
orders, order_details,   (4 tabelle separate)    righe, ordini, pizze  └──► 📊 Power BI
pizzas, pizza_types
```

🧹 **Cosa ho fatto durante la pulizia**

| Passo | Cosa |
|---|---|
| 1 | Controllo: 0 valori mancanti, 0 duplicati, 0 ordini o pizze inesistenti |
| 2 | `pizza_types` letto con la codifica giusta (Windows-1252), per gli accenti |
| 3 | Unione delle 4 tabelle in una sola: 48.620 righe |
| 4 | Categorie, giorni e mesi tradotti in italiano; taglie spiegate (S – Piccola …) |
| 5 | Calcolati ricavo, ora, fascia oraria, giorno della settimana, mese |
| 6 | Creata la tabella degli ordini (21.350) con pizze, totale e dimensione dell'ordine |

---

## 📁 5. Tutti i file, uno per uno

### 📄 Cartella principale

| File | A cosa serve |
|---|---|
| `README.md` | Questo file |
| `LEGGIMI.md` (in ogni cartella) | Una spiegazione corta di quella cartella |
| `.gitignore` | I file da non caricare su GitHub |

### 📂 01RaccoltaDati

| File | A cosa serve |
|---|---|
| `01_scarica.py` | 📥 Scarica i 4 file CSV |
| `02_pulizia.py` | 🧹 Controlla, unisce, traduce e crea le tabelle pulite |

### 📂 02Dati

**❌ 1GrezziNonPuliti** – i 4 file originali, in inglese

| File | Righe | Cosa contiene |
|---|---|---|
| `orders.csv` | 21.350 | Ogni ordine: data e ora |
| `order_details.csv` | 48.620 | Ogni pizza dentro un ordine, con la quantità |
| `pizzas.csv` | 96 | Ogni pizza in ogni taglia, con il prezzo |
| `pizza_types.csv` | 32 | Nome, categoria e ingredienti delle 32 pizze |

**✅ 2Puliti**

| File | Righe | Cosa contiene |
|---|---|---|
| `righe.csv` | 48.620 | Ogni pizza venduta: data, ora, giorno, mese, pizza, categoria, taglia, prezzo, quantità, ricavo |
| `ordini.csv` | 21.350 | Ogni ordine: data, ora, numero di pizze, totale, dimensione |
| `pizze.csv` | 32 | Le pizze del menu con categoria e ingredienti |
| `registro_pulizia.csv` | 6 | Il risultato di ogni passo della pulizia |

### 📂 03Excel

| File | A cosa serve |
|---|---|
| `Pizzeria_Analisi.xlsx` | 📗 Il file Excel: 1.936 formule, 0 errori |
| `crea_excel.py` | 🛠️ Lo script che lo crea |

📗 **I fogli del file Excel**

| Foglio | Cosa c'è |
|---|---|
| LEGGIMI | Guida, legenda dei colori, fonte |
| Controllo | 9 controlli automatici: devono essere tutti ✅ |
| Riepilogo | 14 numeri chiave (SUM, COUNTIF, INDEX/MATCH) |
| Orari | ⭐ Mappa di calore: ordini per giorno × ora (COUNTIFS), 2 grafici |
| Menu | Le 32 pizze: vendite, ricavi, posto in classifica, giudizio (soglia nella cella gialla) |
| Taglie_Categorie | Ricavi per taglia e categoria, matrice categoria × taglia, 2 grafici |
| Calendario | I 365 giorni: ordini, ricavi, giorni di chiusura; ricavi per mese, 2 grafici |
| Ordini, Righe | I dati, in tabelle Excel con filtri |

### 📂 04PowerBi

| File | A cosa serve |
|---|---|
| `PizzeriaDashboard/Pizzeria_Dashboard.pbip` | ⭐ **La dashboard**: doppio clic per aprirla in Power BI Desktop |
| `Pizzeria_Dashboard.pdf` | 📄 La dashboard in PDF |
| `misure_DAX.txt` | 🧮 Le 11 misure DAX |
| `tema_pizzeria.json` | 🎨 Il tema scuro pomodoro, formaggio e basilico (già applicato) |
| `Immagini/sfondo_pagina.png` | Lo sfondo con la barra laterale e la pizza, disegnato da zero |
| `Script/crea_powerbi.py` | Crea una copia della dashboard (`PizzeriaDashboardBase`) |
| `Script/crea_immagini.py` | Disegna lo sfondo |

📊 **Le 5 pagine della dashboard**

1. **Panoramica**: 5 numeri chiave, ricavi mese per mese, categorie, ordini per numero di pizze
2. **Quando**: ordini per ora, per giorno, matrice giorno × fascia oraria
3. **Il menu**: tutte le 32 pizze per ricavi, classifica, la prima e l'ultima
4. **Taglie**: ricavi e prezzo medio per taglia, categoria × taglia, quota per categoria
5. **Conclusioni**

🎛️ Nella barra a sinistra ci sono i filtri: **categoria**, **taglia** e **mese**.

---

## ▶️ 6. Come rifare tutto

```bash
pip install pandas openpyxl pillow
cd 01RaccoltaDati && python 01_scarica.py && python 02_pulizia.py
cd ../03Excel && python crea_excel.py
cd ../04PowerBi && python Script/crea_immagini.py && python Script/crea_powerbi.py
```

💡 Aprendo la dashboard la prima volta, clicca **Aggiorna adesso** sulla barra gialla.

---

## ⚠️ 7. Limiti

📌 Pizzeria fittizia creata per esercitarsi.

📌 Un solo anno (2015): non possiamo confrontare gli anni.

📌 Nessun dato su costi e margini: sappiamo cosa incassa, non cosa guadagna.

📌 Non sappiamo se gli ordini sono da asporto o al tavolo.

---

## 💡 8. Cosa farei

1. 👨‍🍳 Più personale nelle ore di punta (12-13 e 17-18) e il venerdì.

2. 🎁 Una promo per gli ordini da 2 pizze, per alzare lo scontrino.

3. ✂️ Togliere la taglia XXL: quasi nessuno la compra.

4. 🍕 Rivedere le ultime 5 pizze della classifica (es. Brie Carre).

---

## 🔗 9. Da dove arrivano i dati (link)

| Fonte | Cosa ho preso | Link |
|---|---|---|
| Maven Analytics – Data Playground | Il dataset originale "Pizza Place Sales" | https://mavenanalytics.io/data-playground |
| GitHub "Ayushi0214/Datasets" | La copia dei 4 file CSV usata da `01_scarica.py` | https://github.com/Ayushi0214/Datasets/tree/main/pizza_sales |
| File scaricati | `orders`, `order_details`, `pizzas`, `pizza_types` | https://raw.githubusercontent.com/Ayushi0214/Datasets/main/pizza_sales/orders.csv (e gli altri 3 con lo stesso indirizzo) |

📅 Dati scaricati il **26 ottobre 2026**.

---

## 🪜 10. Tutti i passaggi fatti, in ordine

1️⃣ **Scelta del progetto**: un tema semplice e concreto (un ristorante), adatto a Excel e Power BI.

2️⃣ **Domande**: ho fissato le 5 domande.

3️⃣ **Raccolta** (`01_scarica.py`): ho scaricato i 4 file CSV.

4️⃣ **Controllo**: nessun dato mancante, nessun duplicato, tutte le chiavi collegate.

5️⃣ **Pulizia** (`02_pulizia.py`): codifica corretta, unione delle 4 tabelle, traduzione, colonne nuove.

6️⃣ **Excel**: riepilogo, mappa di calore degli orari, classifica del menu, taglie, calendario e controlli; ricalcolato con 0 errori.

7️⃣ **Power BI**: dashboard di 5 pagine con tema scuro e filtri nella barra laterale, aperta e controllata in Power BI Desktop.

8️⃣ **PDF**: esportata la dashboard in `Pizzeria_Dashboard.pdf`.

9️⃣ **Conclusioni**: risposte alle domande e 4 azioni consigliate.
