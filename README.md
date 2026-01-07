# Segmenting Banking Churn: Analisi Comparativa di Metodi di Clustering

Questo repository contiene il progetto finale per il corso di Data Mining dell'Università di Trento. L'obiettivo principale è l'analisi del **Customer Churn** (abbandono dei clienti) nel settore bancario attraverso tecniche di Machine Learning non supervisionato (Clustering).

## 📋 Descrizione del Progetto

Nel panorama bancario competitivo, trattenere i clienti esistenti è strategicamente più vantaggioso che acquisirne di nuovi. Questo progetto mira a spostare l'analisi da una visione generale a una **segmentazione specifica dei clienti**. Utilizzando algoritmi di clustering, abbiamo identificato gruppi omogenei di clienti per comprendere i comportamenti a rischio e proporre strategie di ritenzione mirate.

### 📂 Contenuto del Repository

* 
**`Progetto_Finale.ipynb`**: Il Jupyter Notebook contenente l'intero codice Python per l'analisi: dal caricamento dei dati, alla pre-elaborazione, fino all'esecuzione dei modelli di clustering e alla visualizzazione dei risultati.


* 
**`REPORT.pdf`**: La relazione tecnica completa che descrive le fondamenta teoriche, la metodologia di validazione "K-Validation", l'interpretazione dei cluster e le implicazioni manageriali.



## 📊 Dataset

L'analisi è stata condotta sul dataset pubblico **`Churn_Modelling.csv`**, contenente informazioni comportamentali e demografiche di 10.000 clienti bancari.
Le feature principali utilizzate dopo la pulizia includono: `CreditScore`, `Age`, `Tenure`, `Balance`, `NumOfProducts`, `HasCrCard`, `IsActiveMember`, `EstimatedSalary`.

> 
> **Nota:** Identificativi come `RowNumber`, `CustomerId` e `Surname` sono stati rimossi in quanto non predittivi.
> 
> 

## 🛠 Metodologia

Il flusso di lavoro segue un approccio strutturato KDD (Knowledge Discovery in Databases):

1. 
**Exploratory Data Analysis (EDA):** Analisi delle distribuzioni e delle correlazioni iniziali (es. correlazione tra età, saldo e tasso di abbandono).


2. **Pre-processing:**
* Encoding delle variabili categoriche (Gender).
* 
**Standardizzazione (StandardScaler):** Essenziale per algoritmi basati sulla distanza come K-Means.




3. **K-Means e Validazione Robusta:**
* Selezione del numero ottimale di cluster () tramite la triangolazione di tre metriche: **Elbow Method**, **Silhouette Score** e **Davies-Bouldin Index**.



4. **Analisi Comparativa:**


* Confronto delle performance del K-Means con altri algoritmi: **Hierarchical Clustering** (Ward), **DBSCAN** (Density-based) e **BIRCH**.





## 🏆 Risultati Principali

L'analisi ha identificato **4 profili strategici** di clienti, dimostrando che il K-Means è l'algoritmo più efficace per questo business case:

* **Cluster 3 - "Ghost Customers" (Rischio Critico):** Clienti con saldo elevato (~104k €) ma totalmente inattivi. Tasso di churn del **32%**. Richiedono un ri-ingaggio proattivo.
* **Cluster 2 - "Active High-Balance" (Basso Rischio):** Clienti di alto valore e molto attivi. Strategia: mantenimento e servizi prioritari.
* **Cluster 0 - "Integrated/Loyal" (Rischio Minimo):** Clienti con molti prodotti bancari (avg 2.15). Strategia: programmi fedeltà.
* **Cluster 1 - "Standard No-Card" (Rischio Medio):** Profilo medio, caratterizzato dall'assenza di carta di credito. Strategia: Cross-selling.

## 💻 Tecnologie Utilizzate

Il progetto è sviluppato in **Python** utilizzando le seguenti librerie:

* `Pandas` & `Numpy` (Manipolazione dati)
* `Matplotlib` & `Seaborn` (Visualizzazione dati)
* `Scikit-Learn` (KMeans, DBSCAN, Hierarchical, Preprocessing, Metrics)
* `Scipy` (Dendrogrammi)


