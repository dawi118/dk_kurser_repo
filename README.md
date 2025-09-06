# dk_kurser_repo

This repository relates to a series of .ipynb documents for extracting information from (archived) course webpages run by the University of Copenhagen & Aarhus (in progress). Information extracted includes but may not be limited to:

- Year
- Course code
- Course title
- Course instructors
- Emails of instructors: obfuscated in repository
- Content
- Learning outcomes
- Knowledge
- Skills
- Competencies
- Other information

Note, codebases are designed to handle inputs in both Danish and English, and produce output in JSON format.

**Output Quality (all study boards, all years, from dk_kurser_total_scrape.ipynb)**

See below for distribution of missing data across scraped fields for all courses across scoped academic years (Copenhagen):

<img width="1392" height="790" alt="image" src="https://github.com/user-attachments/assets/dcf7e301-efab-4565-be67-fa47616bfe4e" />

Note that:

- The code successfully scrapes course information for c. 98% of courses across all years.
- Knowledge, skills and competencies are extracted based on keyword searches from the parent 'content' field - where a keyword match fails (in Danish or English), these are marked as missing. However, NLP methods could be used downstream to extract this inforamtion from the content field.
- Course content follows an increasingly formulaic format in later years, explaining higher levels of missingness in older course information.
- Coordinator emails are intentionally left in their obfuscated format - these can be de-anonymised downstream on JSON output files.

Analysis was also undertaken to understand continuity across text fields over time:

<img width="1177" height="590" alt="image" src="https://github.com/user-attachments/assets/5b45be03-17d0-4589-834d-631b9a93db3b" />

Whilst limited, this suggests a modest increase in the average length of course descriptions over time, even when excluding missing data (more prevalent in earlier years) from the calculation.
