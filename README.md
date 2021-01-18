# Persona-Maker
## Rule-based classification model to get persona and hierarchy of data professionals based on their job titles

**Why this project?**
B2B technology marketers need to segment the leads in their sales databases into the right personas and hierarchy (decision maker vs line of business practitioner) based on their **job titles**. They need this segmentation to feed email lists, run analyses, set targeting criteria, and so on. This helps send relevant messages to users and hence improve customer satisfaction, and prevents uninentional spam. Business analysts can use personas as filtering criteria to study important customer trends.

**Problem Statements**
1. Big data, machine learning, AI, data science professions have proliferated in recent times. Different job titles can mean very similar work responsibilities, and can be clustered. For example, 'data scientist', 'deep learning specialist', 'machine learning researcher' all focus on model building/optimization and can be classified as 'data scientists'.
2. Most commercial list providers do not have the tools to map job titles to personas or hierarchy from their databases. Those who do offer such services often have very poor accuracy.
3. Sales and marketing databases get records from many sources - manual entries by sales reps, list purchases from market intelligence firms, titles filled out by individuals when they submit forms to download whitepapers or watch webinars, and so on. Data quality is bad due to data entry errors - misspellings, incomplete job titles, inaccurate mappings.
4. Due to the above reason, there is massive sprawl, even in smaller databases. For example, an employer of mine had 500K leads in their database who had 93K distinct job titles!
5. Sales and marketing teams often hire contractors and spend hours of manual effort for data correction. This is an expensive, time consuming and error-prone approach

**Solution**
1. I built this rules-based classifier in Python using Pandas, RegEx and Lambda functions. The model was 'trained' manually and refined over 25 trials. The classification rules were validated with sales executives, sales ops professionals as well as business analysts for soundness. Due to the human validation, the quality of classification is high. 
2. It utilizes regex based matching to compensate for partial misspellings and stray characters.
3. The model is meant to be flexible. You can add more rules, switch up topics, add patterns, job titles, personas and so on.

**How it works**
1. The model reads the value in the 'Job Title' column and calls multiple lambda functions to determine the 'Persona' and 'Hierarchy' values. 
2. The model uses the following pattern matching logic (see diagram). For example, a [Job Title] containing 'Data Scien' will result in [Persona] being set to 'Data Science'. If the title contains words like 'Director' or 'Chief' then the [Hierarchy] is set to 'Decision Maker'
![Persona classification logic](https://pages.databricks.com/rs/094-YMS-629/images/Personasv3.jpg)
