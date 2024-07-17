# Reproducibility in Tier 2 Security Conferences
## Table of Contents
- [Data](#Data)
- [Scripts](#Scripts)
- [Docker](#Docker)
- [Embeddings](#Embeddings)
- [Clustering](#Clustering)
## Data
1. ***conf*** folder: contains data of all four Tier 2 Security conferences (ACSAC, Asia CCS, Euro S&P, and WiSec), with the following rows:
   1. *Conference*: The conference that the paper was accepted at
   2. *Year*: The year that the paper was published
   3. *Title*: The title of the paper
   4. *Authors*: Authors of the paper
   5. *PDF Link*: Link to the PDF version of the paper
   6. *Code*: Link to the repository for code directly associated with the paper
2. ***evaluation*** folder: contains the data of indirect and direct study. The coding of columns used in our analyses is briefly explained below and can also be found in greater detail in our paper:
   1. *Author Affiliation:*
      - 0: Academic
      - 1: Mainly Academic
      - 2: Mainly Industry
      - 4: National Lab
      - 5: Federal Agency
      - 6: 50/50 split (i.e., 1/2 Academic, 1/2 Industry)
      - 7: Independent Researcher
   2. *ReadMe:*
      - -1: N/A
      - 0: Name
      - 1: Mediocre ReadMe
      - 2: Good ReadMe
   3. *Type:*
      - 0: Tool/Package
      - 1: Repository
      - 2: Data (only data is available)
      - 3: Demonstration (photos, videos, supplementary materials available)
      - 4: Code (only code available, no data)
      - 5: No Code and No Data
   4. *Available:*
      - -1: N/A
      - 0: School Website
      - 1: Personal Website
      - 2: Open Source Repository (GitHub, Google Drive/Site, GitLab, etc.)
      - 3: Request Access
   5. *Last Modified:*
      - Date of last commit/modification (MM/DD/YYYY)
   6. *Language:*
      - Free response, the dominant language used in repo/project (Python, C, Java, etc.)
   7. *Compiles:*
      - -1: N/A
      - 0: Compiles Right Away (No need to edit/modify code to compile the repo)
      - 1: Compiles After Edits (Edits in file structure/variables to get the code to run)
      - 2: Doesn't Run (Doesn't compile even after edits)
      - 3: Ran and Does Not Compile (requires extra components/hardware (i.e., GPU, phone, Raspberry Pi, etc. not explicitly mentioned in repo/paper)
      - 4: Not Ran (requires extra components/hardware explicitly mentioned in paper/repo)
   8. *Output Matches:*
      - -1: Does Not Match (A tool/repo not designed/made for reproducibility)
      - 0: Output Does Not Match (Output is +/-10% difference compared to claims of paper.)
      - 1: Output Matches (Best Effort, the output is within +/-10% difference compared to claims of paper)
   9. *Hardware:*
       - Free Response, list of extra hardware required in order to reproduce
   10. *Made for Reproducibility:*
       - 0: For Reproducibility
       - 1: Not For Reproducibility
   11. *Funding:*
       - Free Response, lists the biggest/first agency name in the Acknowledgements section of the paper
   12. *Artifact Evaluation:*
       - -1: Not Submitted to AEC
       - 0: Artifact Evaluated Functional Badge
       - 1: Artifact Evaluated Reusable Badge
       - 2: Artifact Reproduced Badge
       - 3: Artifact Replicated Badge
       - 4: Artifact Available Badge
3. ***full*** folder: contains merged rows from data in ***evaluation*** folder for executing Coxcomb graphs.
4. ***tier1.csv:*** This file contains USENIX Security (Tier 1 Security Conferences) data from previous work required to visualize Figure 6 in our paper.
## Scripts
Scripts used for analyses and figures are located in the ***scripts*** folder. To reproduce our figures, please run all cells in order after satisfying all dependency requirements listed below. All scripts for creating figures use ***Python 3.9.13*** and require changing the file/folder paths (Areas where file *PATH* must be changed/added are written in **bold** or commented within each script):
1. *figures_4_and_6.ipynb:* This Jupyter Notebook script contains the codes to reproduce Figure 4 and Figure 6 in the paper.
   - The following packages are used to run this code:
     ```
     matplotlib==3.5.2
     numpy==1.23.5
     pandas==1.4.4
     plotly==5.9.0
     plotly_express==0.4.1
     seaborn==0.11.2
     ```
2. *coxcombs.ipynb:* This script reproduces Figure 2 and Figure 3 from the paper.
   - Packages required to run the script:
     ```
     matplotlib==3.5.2
     numpy==1.23.5
     pandas==1.4.4
     seaborn==0.11.2
     ```
## Docker

## Embeddings

## Clustering
