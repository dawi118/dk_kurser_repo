# dk_kurser_repo

**1. Overview**

This repository relates to two .ipynb documents for extracting information from (archived) course webpages. As of current, these are run by the University of Copenhagen & Aarhus University. Information extracted includes:

- Year
- Course code
- Course title
- Course instructors
- Emails of instructors
- Content
- Learning outcomes
- Knowledge
- Skills
- Competencies
- Other information

Codebases are designed to handle inputs in both Danish and English, and produce output in JSON format.

**2. General Progress**

Scraping has been undertaken for Copenhagen university for 2013-2024 and outputs have been approved by Professor Stephen Hansen and Mikkel Høst Gandil (see QA outputs below). Scraping for Aarhus is in progress, requiring a different approach to Copenhagen due to webpage semantics (plain html vs javascript). Details are located in dk_kurser_total_scrape_aarhus.ipynb.

**3a. Output Quality - Copenhagen**

See below for distribution of missing data across scraped fields for all courses across scoped academic years (Copenhagen):

<img width="1392" height="790" alt="image" src="https://github.com/user-attachments/assets/dcf7e301-efab-4565-be67-fa47616bfe4e" />

Note that:

- The code successfully scrapes course information for c. 98% of courses across all years.
- Knowledge, skills and competencies are extracted based on keyword searches from the parent 'content' field - where a keyword match fails (in Danish or English), these are marked as missing. However, NLP methods could be used downstream to extract this information from the content field.
- Course content follows an increasingly formulaic format in later years, explaining higher levels of missingness in 'older' course information.
- Coordinator emails have been cleaned and de-anonymised.

Analysis was also undertaken to understand continuity across text fields over time:

<img width="1177" height="590" alt="image" src="https://github.com/user-attachments/assets/5b45be03-17d0-4589-834d-631b9a93db3b" />

Whilst limited, this suggests a modest increase in the average length of course descriptions over time, even when excluding missing data (more prevalent in earlier years) from the calculation.

**3b. Output Quality - Aarhus**

In the absence of a formal quality assurance, a sampling approach suggests that a typical course for Aarhus extracts the following data: 

=== SAMPLE @ 40/61705 ===
{

"**source_url**": "https://kursuskatalog.au.dk/en/course/64882/20-ECTS-Public-Organizations-Leadership-and-Governance",

"**year**": "2016",

"**course_code**": "171152U020",

"**course_title**": "(20 ECTS) Public Organizations, Leadership and Governance",

"**credit**": "20",

"**placement**": "Autumn semester 2016",

"**contracting_department**": "Danish School of Education",

"coordinators": [

    "Not specified",
    "ECTS 20 Level Master Language of instruction Danish Type of course Ordinary Primary programme Master's Degree Programme in Educational Sociology Related programmes Master's Degree Programme in Educational Theory and Curriculum Studies (Mathematics), Master's Degree Programme in General Education Department Danish School of Education Faculty Arts Location Aarhus STADS UVA code 171152U020 Copy UVA code"
  ],

"coordinator_emails": null,

"content": "Read more",

"learning_outcomes": "Read more Not specified",

"knowledge": null,

"skills": null,

"competencies": null,

"**language**": "Danish",

"**level**": "Master",

"**web_lang**": "en"

}

**Suggestions for improvements**

The code is incorrectly/inconsistently extracting data for the following rows, which should be refined going forward:
['coordinators', 'coordinator_emails', 'content', 'learning_outcomes', 'knowledge', 'skills', 'competencies']

Additionally, this code runs infeasibly slowly (>100 hours for a complete scrape) due to the requirement to use playwright to render pages. Methods for optimising this process should be explored.
