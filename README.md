## Extracting African Plant Species' Traits Project

Data sources: 
- [World Flora Online](https://www.worldfloraonline.org/)
- Natural History Museum
- [TRY](https://www.try-db.org/TryWeb/dp.php)

### Process

1. Scraping (scrape_wfo.ipynb)
 - Scrapes all WFO descriptions and citations for every plant in the input file by IPNI id 
 - Builds citation lookup dictionary
2. Initial analysis (initial-analysis.ipynb)
 - Extracts these descriptions only
 -- Diagnostic Description
 -- General Information
 -- Habit
 -- Morphology
 ** Geographic distribution & ecology could be a good follow up
 - Analyses initial data available by class/order/family
3. Cleansing (cleansing.ipynb)
 - Fixes encoding errors 
 - Uses lingua-py to detect the language of each description 
 -- English
 -- French
 -- Portuguese
 -- German
4. Trait extraction
 - Run Quinex LLM to extract trait data for each plant
5. Enrichment & Validation
 - Merges with TRY trait data 
 - Track disgreements in data
6. Analysis
 - Which plants have traits?
 - Which traits are most represented?
 - Which taxonomies are best described?
 - Which are missing?
 - Where does WFO and TRY diverge?
7. Imputation
 - Run imputation to fill in missing traits 
8. Visualization
 - Generate charts
