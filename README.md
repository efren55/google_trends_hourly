# General Summary
Exploratory analysis of one week of data from the public Google Trends dataset (hourly) in BigQuery, focusing on three U.S. states: California, Florida, and New York (covering 31 DMAs in total). The objective was to identify the most-searched terms, categorize them by topic, and compare search behavior across the states.
Technical stack: BigQuery, Python, pandas, matplotlib, Hugging Face Transformers (zero-shot classification using MoritzLaurer/DeBERTa-v3-base-mnli-fever-anli), lingua.

# Insights
1. The data does not distinguish by region. Trends are identical across all 31 DMAs. Counts by state (California > New York > Florida) merely reflect the number of DMAs in each state (12, 10, and 9, respectively), rather than indicating higher search interest.
2. Dominant categories: "Sports" leads, followed by "People," "Entertainment," "Organizations," "Locations," "Technology," and "Business." In terms of growth (*percent_gain*), "Weather," "Locations," and "Business" stand out.
3. Persistent terms: *hebeos.com*, *zimbio.com*, and *Woodlands Inn* appear throughout the week, with their *percent_gain* increasing on weekends. Their constant presence suggests they may be "noise" or artifacts within the dataset rather than genuine trends.
4. Bilingual presence: English terms predominate, but there is a notable presence of Spanish terms (for example, *tiempo de mañana* appears with the same frequency as its English equivalent, *weather tomorrow*).
5. Temporal pattern: The dataset records only four snapshots per day (at 00:00, 06:00, 12:00, and 18:00), with the highest activity occurring at 18:00. By day of the week, Thursday has the highest count, though the differences between days are minimal.
6. Educational pattern: Terms such as *blooket join*, *gimkit*, *wayground*, *unblocked games*, and *ixl* suggest usage associated with educational platforms.

# CONCLUSION
The analysis showed that, for the week studied, the dataset contains no regional variation; therefore, it is not possible to compare states or attribute behavioral differences to specific populations. The project’s most valuable finding is methodological: validating the data structure before interpreting the results prevented false conclusions. Nevertheless, the dataset made it possible to characterize dominant themes, temporal dynamics, and the persistence of terms.

Next steps: repeat the verification process for other weeks and tables within the dataset to determine whether the absence of regional variation is a general pattern, and filter out persistent terms suspected of being noise.
