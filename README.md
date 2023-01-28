# detection-of-foreign-companies-in-the-RF

We offer a script and data for reproducing the list of foreign companies in the Russian Federation.

Source of data: One of the many services where free data is presented is the site https://egrul.itsoft.ru/. There is already a list of "Organizations where the founder is a foreign person" based on the relevant Rosstat codes. You can get it at this link in the form of csv files at the link https://egrul.itsoft.ru/csv/.

Python file in .csv format uses two files org2_foreign_founder (list of legal entities of the Russian Federation with foreign ownership) and file income_outcome2011-2020 (financial indicators). The file python runs and merges the two files and produces a file called org2_foreign_founder_with_income.csv.

Next, the data needs manual cleaning (see more detailed instructions). For comparison, you can use the database created by KSE (the file is called clean_data_by_KSE.tsv).

The KSE Institute used the following algorithm:

1. We took a list of foreign companies and sorted it by revenue in 2021 with a revenue of more than $5 million (threshold 1) and that the share of the foreign owner is not less than 50% (threshold 2) - ORBIS generated about 8,600 of such companies.
2. The first few thousand records were reviewed manually. If the company is actually Russian, it was removed from the list, if it belongs to a real foreign owner - the correct name of the owner was added (usually from Wikipedia). So we created a list of approximately 1,200 legal entities in the Russian Federation that are owned by foreigners.
3. Next, we developed an algorithm that automatically traverses the list using Google and Wikipedia APIs, and was able to further expand the list to 1,700 foreign-owned legal entities.
4. We stopped the expansion of the database at the level of companies in the Russian Federation with revenue of 5 million US dollars and below. Further expansion did not have a significant impact on the total revenue of all foreign-owned companies in the Russian Federation (in total, these 1,300 companies have a revenue of approximately $295 billion in the Russian Federation, or ~17% of Russia's nominal GDP, and the number of personnel - 1.4 million people). In the manual mode based on open data we identified data on revenue for another ~100 companies (in some cases dated with 2020).

A foreign company can be owned by several legal entities (for example, Baker Hughes has 9 LLCs). Therefore, our database contains approximately 1,300 unique foreign companies, which are owned by approximately 1,700 local legal entities.
