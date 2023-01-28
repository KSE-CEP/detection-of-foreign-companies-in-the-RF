# detection-of-foreign-companies-in-the-RF

We offer a script and data for reproducing the list of foreign companies in the Russian Federation.

Source of data: One of the many services where free data is presented is the site https://egrul.itsoft.ru/. There is already a list of "Organizations where the founder is a foreign person" based on the relevant Rosstat codes. You can get it at this link in the form of csv files at the link https://egrul.itsoft.ru/csv/.

Python file in .csv format uses two files org2_foreign_founder (list of legal entities of the Russian Federation with foreign ownership) and file income_outcome2011-2020 (financial indicators). The file python runs and merges the two files and produces a file called org2_foreign_founder_with_income.csv.
