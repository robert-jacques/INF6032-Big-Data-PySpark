# Big Data Analytics: Distributed NLP & Pattern Matching
### MSc Data Science | Module: INF6032 | Grade: 73%

## 🎯 Project Overview
This project involved the large-scale analysis of unstructured text data from the **Wikipedia (large.csv.gz)** and **MAGPIE** datasets. The objective was to engineer a distributed PySpark pipeline to perform linguistic transformations, frequency analysis, and idiom identification across multi-million row corpora.

---

## 🛠️ Methodology & Frameworks
* **Distributed Environment:** Developed within a **Databricks** interactive cluster utilising the Spark ecosystem.
* **Dual-API Implementation:** * **DataFrame API:** Primary implementation using `NGram` transformers and `StopWordsRemover` for efficient, high-level feature engineering.
    * **RDD API:** Secondary low-level implementation to demonstrate manual distributed logic. Utilised `.map()`, `.flatMap()`, and `.reduceByKey()` for manual tokenisation and bigram counting.
* **Advanced Analytics:** * Employed `pyspark.sql.window` functions to perform partitioned frequency ranking.
    * Executed high-scale **Inner Joins** between the Wikipedia corpus and the MAGPIE unfiltered dataset to isolate idiomatic expressions.



## 🧬 Data Engineering Highlights
* **Methodological Validation:** Confirmed methodological accuracy by producing **identical results** across both DataFrame and RDD implementations (e.g., verifying "of the" as the most frequent bigram with 76,294 occurrences).
* **High-Dimensional Join Logic:** Developed a methodology to resolve matches between a large-scale text corpus and an idiom reference set, identifying **67 unique idiomatic bigrams** found in both datasets.
* **Outlier Analysis:** Identified dataset extremes, including a record-breaking sentence containing **4,571 words**, demonstrating the necessity of robust pre-processing in Big Data pipelines.

---

## 📈 Key Findings
1. **Linguistic Density:** Successfully calculated bigram density across the Wikipedia corpus, identifying an average of **18.04 bigrams** per sentence.
2. **Contextual Validation:** Verified the literal usage of recurring word pairs (e.g., "from which") by extracting original sentence contexts, moving beyond frequency counts to linguistic usage analysis.
3. **Stopword Filtering:** Quantified the impact of stopword removal on bigram frequencies, revealing significant shifts in the ranking of high-frequency linguistic patterns.

---

## 📁 Repository Structure

* **`code/inf6032-big-data-nlp.ipynb`**: Full implementation featuring both DataFrame and RDD-based bigram frequency analysis.
* **`report/inf6032-big-data-analysis.pdf`**: Technical report detailing architectural decisions, cluster setup, and comparative API analysis.
* **`data/`**: Placeholder directory containing a `README.md` with instructions for sourcing and local placement of the `large.csv.gz` and `MAGPIE_unfiltered.jsonl` datasets.

---

## 🚀 Reproducibility
1. **Environment:** This project was developed on a **Databricks Interactive Cluster** (Runtime 15.4 LTS or equivalent).
2. **Dependencies:** The analysis utilises core **PySpark** libraries (`pyspark.sql`, `pyspark.ml.feature`) pre-installed in the Databricks environment; no external `requirements.txt` is necessary.
3. **Data Ingestion:** Upload the required Wikipedia and MAGPIE datasets to the Databricks File System (DBFS) `/FileStore/tables/`.
4. **Execution:** Run the notebook sequentially to regenerate the distributed ranking tables, RDD/DataFrame comparisons, and idiomatic cross-match results.
