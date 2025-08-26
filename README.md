# 📊 Dashboard AdventureWorks con Looker Studio

Questo progetto utilizza i dati del **database AdventureWorksDW** (porting MySQL) per creare una **dashboard interattiva** in **Looker Studio**.  

L’obiettivo è analizzare le vendite con un focus su:
- **Distribuzione geografica** (paesi, regioni, città)  
- **Categorie di prodotto** (Bikes, Clothing, Accessories, Components)  
- **Andamento temporale delle vendite**  
- **Numero di articoli venduti**  

---

## 🔧 Preparazione dati
Abbiamo creato una **vista SQL dedicata** (`vw_looker_sales_reseller`) che:
- unisce le tabelle **FactResellerSales** con le dimensioni **DimProduct / DimProductSubcategory / DimProductCategory** per recuperare le categorie di prodotto,  
- collega le vendite alle informazioni geografiche tramite **DimReseller + DimGeography** e, dove mancano, tramite **DimSalesTerritory**,  
- espone i campi puliti per Looker Studio:
  - `CountryISO2` (per la mappa geografica)  
  - `CountryName`, `Regione`, `CittaFull`  
  - `Categoria`  
  - `OrderDate`, `Anno`, `Mese`  
  - `SalesAmount`, `OrderQuantity`

---

## 📌 Visualizzazioni in Looker Studio
Nella dashboard sono stati creati i seguenti componenti:

1. **Mappa geografica interattiva**  
   - Mostra le vendite per paese.  
   - Attivando l’interazione, la mappa funge da filtro per gli altri grafici.

2. **Grafico a barre – Categorie più vendute**  
   - Dimensione: `Categoria`  
   - Metrica: `SUM(SalesAmount)` oppure `SUM(OrderQuantity)`  
   - Filtrato in tempo reale dalla mappa e dagli altri controlli.

3. **Controllo intervallo di date**  
   - Basato sul campo `OrderDate`.  
   - Permette di selezionare il periodo di analisi (predefinito = *Tutto*).

4. **Controllo intervallo di valori**  
   - Collegato a `OrderQuantity`.  
   - Slider per filtrare le vendite in base al numero di articoli venduti.

5. **Grafici aggiuntivi (opzionali)**  
   - Serie temporale delle vendite.  
   - Tabella di dettaglio per anno, categoria e paese.

---

## 🎯 Risultato
La dashboard consente di:
- esplorare le vendite **per paese e categoria**,  
- filtrare dinamicamente **per periodo e quantità vendute**,  
- ottenere una panoramica interattiva e modulare delle performance dei prodotti AdventureWorks.  

---



