# Segmenting Banking Churn: Analisi Comparativa di Metodi di Clustering

Questo repository ospita il progetto finale per il corso di **Data Mining** dell'Università di Trento. L'obiettivo principale del lavoro è l'analisi del **Customer Churn** (tasso di abbandono) nel settore bancario, condotta attraverso tecniche di Machine Learning non supervisionato (Clustering).

## 📋 Descrizione del Progetto

In un mercato bancario sempre più competitivo, la fidelizzazione dei clienti esistenti (*retention*) è strategicamente più vantaggiosa rispetto all'acquisizione di nuovi. Questo progetto evolve l'approccio analitico tradizionale, passando da una visione generalista a una **segmentazione comportamentale specifica**.

Utilizzando diversi algoritmi di clustering, sono stati identificati gruppi omogenei di clienti (cluster) per isolare i profili a rischio e permettere la definizione di strategie di ritenzione mirate ("Tailored Retention Strategies").

### 📂 Contenuto del Repository

* **`Progetto_Finale.ipynb`**: Il Jupyter Notebook che contiene l'intera pipeline di analisi: caricamento dati, pre-processing, esecuzione dei modelli di clustering e visualizzazione dei risultati.
* **`REPORT.pdf`**: La relazione tecnica completa. Include le fondamenta teoriche, la metodologia di validazione adottata ("K-Validation"), l'interpretazione di business dei cluster e le implicazioni manageriali.

## 📊 Dataset

Il progetto utilizza il dataset pubblico **`Churn_Modelling.csv`**, composto da informazioni demografiche e comportamentali relative a 10.000 clienti bancari.

Le feature principali utilizzate per il modello includono: `CreditScore`, `Age`, `Tenure`, `Balance`, `NumOfProducts`, `HasCrCard`, `IsActiveMember` ed `EstimatedSalary`.

> **Nota:** Gli identificativi univoci come `RowNumber`, `CustomerId` e `Surname` sono stati rimossi in fase preliminare poiché privi di potere predittivo.

## 🛠 Metodologia

Il flusso di lavoro segue lo standard **KDD** (Knowledge Discovery in Databases):

1. **Exploratory Data Analysis (EDA):** Analisi delle distribuzioni e delle correlazioni preliminari (es. relazione tra età, saldo bancario e tasso di abbandono).
2. **Pre-processing:**
* Encoding delle variabili categoriche (es. `Gender`).
* **Standardizzazione (StandardScaler):** Passaggio fondamentale per garantire l'efficacia degli algoritmi basati sulla distanza euclidea.


3. **K-Means e Validazione Robusta:**
* Selezione del numero ottimale di cluster () tramite la triangolazione di tre metriche: **Elbow Method**, **Silhouette Score** e **Davies-Bouldin Index**.


4. **Analisi Comparativa:**
* Confronto delle performance del K-Means con algoritmi alternativi per validarne la robustezza: **Hierarchical Clustering** (metodo Ward), **DBSCAN** (Density-based) e **BIRCH**.



## 🏆 Risultati Principali

L'analisi ha isolato **4 profili strategici** di clienti, confermando il K-Means come l'algoritmo più efficace per questo business case:

*  **Cluster 3 - "Ghost Customers" (Rischio Critico):** Clienti con saldo elevato (~104k €) ma totalmente inattivi. Presentano un tasso di churn del **32%**. Richiedono azioni di ri-ingaggio proattivo immediato.
*  **Cluster 2 - "Active High-Balance" (Basso Rischio):** Clienti "Premium": alto valore e molto attivi. Strategia consigliata: mantenimento e servizi prioritari.
*  **Cluster 0 - "Integrated/Loyal" (Rischio Minimo):** Clienti radicati con un alto numero di prodotti bancari (media 2.15). Strategia consigliata: programmi fedeltà.
*  **Cluster 1 - "Standard No-Card" (Rischio Medio):** Profilo medio, caratterizzato principalmente dall'assenza di carta di credito. Strategia consigliata: campagne di Cross-selling.

## 💻 Tecnologie Utilizzate

Il progetto è sviluppato in **Python** avvalendosi delle seguenti librerie:

* **Data Manipulation:** `Pandas`, `Numpy`
* **Visualization:** `Matplotlib`, `Seaborn`
* **Machine Learning:** `Scikit-Learn` (KMeans, DBSCAN, Hierarchical, Preprocessing, Metrics)
* **Scientific Computing:** `Scipy` (Dendrogrammi)
