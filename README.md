

This project implements an end-to-end machine learning workflow for compensation prediction using a heterogeneous LinkedIn job-posting dataset. The pipeline includes schema validation, high-granularity missing-value treatment, categorical encoding, and aggressive dimensionality reduction through domain-aware feature elimination. After numerical stabilization via median imputation and removal of sparse attributes, the data is encoded using Label Encoding and partitioned into training and validation subsets. The core predictive engine is an **XGBoost Regressor**, selected due to its ability to model nonlinear compensation relationships, handle noisy high-cardinality features, and perform internal regularization via gradient-boosted decision trees. Performance is assessed using RMSE to evaluate model generalization on unseen job posts.

The dataset was ingested from the Kaggle “LinkedIn Job Postings” repository, which aggregates real-world job-advert metadata scraped from LinkedIn's public job listings. The scraping pipeline extracts multi-table relational data—including postings, skills, industries, salaries, and employer metadata—via automated crawlers and stores it in structured CSV files. These files encapsulate various pay-period formats, unnormalized salary expressions, and unstructured fields such as descriptions and skill tags, making the dataset inherently noisy and ideal for demonstrating robust preprocessing and feature-engineering techniques. The preprocessing layer in this project is explicitly designed to handle the artifact patterns introduced by large-scale scraping systems, such as sparsity, schema drift, formatting inconsistencies, and irregular timestamp encoding.




