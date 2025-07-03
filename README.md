# dk_kurser_repo

This repository relates to a series of .ipynb documents for extracting information from (archived) course webpages run by the University of Copenhagen. Information extracted includes but may not be limited to:

- Year
- Course code
- Course title
- Course instructors
- Emails (of instructors)
- Content
- Learning outcomes
- Knowledge
- Skills
- Competencies
- Other information

Note, the codebase is designed to handle inputs in both Danish and English, and output the above details in JSON format.

Output Quality:
![image](https://github.com/user-attachments/assets/acff006e-29d4-48d4-ac81-c822ab5957f7)
* of missing data across scraped fields - note that knowledge, skills and competencies are extracted from 'content'. If these are reported missing, then it is likely that the content fails to touch on these areas.
