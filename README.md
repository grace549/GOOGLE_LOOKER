# 📊 EDA AdventureWorksDW (2018 - Bikes)

## 📌 Introduzione
Questa analisi esplorativa (EDA) è stata condotta sul dataset **AdventureWorksDW** caricato su MySQL e successivamente importato in **Looker Studio** tramite una vista denormalizzata (`vw_sales_flat`).  
Il dataset fornito contiene dati di vendita online relativi esclusivamente all’anno **2018** e alla categoria di prodotto **Bikes**.

L’obiettivo è comprendere:
- l’arco temporale coperto dai dati,
- le principali metriche descrittive,
- la distribuzione delle vendite nel tempo e per sottocategoria,
- l’individuazione di outlier e possibili cluster.

---

## ⏱️ Arco temporale
Il grafico a linee delle vendite mostra che i dati coprono esclusivamente **l’anno 2018**.  
Non sono quindi disponibili confronti multi-anno, ma si osservano variazioni **mensili** che evidenziano stagionalità.

---

## 📌 KPI principali
Le scorecard della dashboard mostrano:
- **Totale vendite**: `SUM(SalesAmount)`  
- **Numero ordini**: `COUNT_DISTINCT(SalesOrderNumber)`  
- **Numero prodotti venduti**: `COUNT_DISTINCT(ProductKey)`  
- **Numero sottocategorie**: 3 (Mountain, Road, Touring Bikes)  
- **Numero clienti**: `COUNT_DISTINCT(CustomerKey)`  

➡️ I valori numerici esatti sono calcolati automaticamente nella dashboard.

---

## 📊 Distribuzione delle vendite
- **Per sottocategoria**: le **Mountain Bikes** generano la maggior parte del fatturato, seguite da Road e Touring Bikes.  
- **Per mese**: le vendite non sono uniformi, con picchi nei mesi centrali (primavera/estate), segno di una forte **stagionalità**.

---

## 🔎 Outliers
Dal grafico a dispersione **OrderQuantity vs SalesAmount** emergono alcuni ordini con:
- quantità molto elevate,
- importi fuori scala rispetto alla media.

➡️ Probabilmente si tratta di clienti corporate o rivenditori.

---

## 🧩 Cluster
L’analisi evidenzia cluster naturali:
- **Temporali** → picchi stagionali durante l’anno,  
- **Per sottocategoria** → Mountain Bikes dominanti,  
- **Per cliente** → pochi clienti ad alto valore vs molti clienti con ordini piccoli (**Pareto 80/20**).  

---

## ✅ Conclusioni
- I dati riguardano solo **2018** e solo **Bikes**.  
- Le vendite mostrano chiara **stagionalità**.  
- Le **Mountain Bikes** sono la sottocategoria più rilevante.  
- Esistono **outlier** legati a ordini eccezionali.  
- I dati presentano cluster interessanti per mese, sottocategoria e tipologia di cliente.  

📌 **Limite del dataset**: assenza di più anni e di altre categorie, che riduce la possibilità di confronti storici e inter-categoria.

---

## 📎 Dashboard
Il report completo con i grafici è disponibile su Looker Studio:  
👉 (https://lookerstudio.google.com/reporting/b0dd3a7c-9ea6-48d9-a5f7-70617bf9ed90)
