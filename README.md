# Making_training_material
This repo has the source files to make the markdown training data from Calendar, Slides, Textbook, Lectures

## Pipeline Notebooks

This repo includes Jupyter notebooks that show how to transform raw course materials into tidy Markdown and summaries. Each notebook corresponds to a step in the pipeline.

- **`Data88E_Textbook_toMD.ipynb`**  
  Converts textbook chapters (from Jupyter Book or source notebooks) into individual Markdown files (`00-Intro.md`, `01-Demand.md`, …).  
  *Focus:* clean, numbered, standalone in markdown, in subfolders by chapter.


- **`Data88E_LectureNB.ipynb`**  
  Exports lecture notebooks into Markdown files (`lec01.md`, `lec02.md`, …).  
  *Focus:* capture worked examples and instructor explanations, in subfolders by lecture.

- **`Data88E_SlideDecks.ipynb`**  
  Converts slide decks (PPTX, Google Slides, or PDF) into Markdown files.  
  *Focus:* extract concise bullet points, key terms, and definitions.

- **`Data88E_Summary.ipynb`**  
  Generates `summary.yaml` files for each folder (lectures, textbook, slides).  
  *Focus:* lightweight metadata describing contents, to guide chunking and retrieval.

- **`Data88E_concat_to_mega_md.ipynb`**  
  Concatenates individual Markdown files into **mega files** (one per content type).  
  *Focus:* support platforms that limit the number of input files  (Claude, Gemini).

---

## Workflow Overview

1. Run `Data88E_Textbook_toMD.ipynb` → generate textbook Markdown.  
- this notebook gets the textbook chapters from a Github repo, so make sure to update the URL in the notebook if needed. ( github.com/data-88e/88e_textbook )

2. Run `Data88E_LectureNB.ipynb` → generate lecture Markdown.  
- this notebook gets the lecture notebooks from a Github repo, so make sure to update the URL in the notebook if needed. ( github.com/data-88e/fa24-materials/lec/)

3. Run `Data88E_SlideDecks.ipynb` → generate slides Markdown.  
- this notebook downloads slide decks from Google Drive, so make sure to update the folder ID in the notebook if needed. ( https://drive.google.com/drive/folders/1gk3JH2Yk1b9j1vXH3Fq7t8x9y0zA5B6C )

4. Run `Data88E_Summary.ipynb` → create summaries for each folder.  
- this notebook runs on the generated markdown files from the previous steps.

5. Run `Data88E_concat_to_mega_md.ipynb` → bundle everything into mega files.  
- this notebook runs on the generated markdown files from the previous steps.


The outputs are the source materials to the [88E Training Material repo](https://github.com/data-88e/88e_training_material).
