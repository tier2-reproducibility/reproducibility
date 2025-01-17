# Reproducibility in Tier 2 Security Conferences
## Table of Contents
- [Data](#Data)
- [Scripts](#Scripts)
- [Steps to Reproduce](#reproduce_steps)
- [Docker](#Docker)
- [Embeddings and Clustering](#embeddings_clustering)
  
## Data
1. [***conf***](conf) folder: contains data of all four Tier 2 Security conferences (ACSAC, AsiaCCS, EuroS&P, and WiSec), with the following rows:
   1. *Conference*: The conference that the paper was accepted at
   2. *Year*: The year that the paper was published
   3. *Title*: The title of the paper
   4. *Authors*: Authors of the paper
   5. *PDF Link*: Link to the PDF version of the paper
   6. *Code*: Link to the repository for code directly associated with the paper
2. [***evaluation***](evaluation) folder: contains the data of indirect and direct study. The coding of columns used in our analyses is briefly explained below and can also be found in greater detail in our paper:
   1. *Author Affiliation:*
      - 0: Academic
      - 1: Mainly Academic
      - 2: Mainly Industry
      - 4: National Lab
      - 5: Federal Agency
      - 6: 50/50 split (1/2 Academic, 1/2 Industry)
      - 7: Independent Researcher
   2. *ReadMe:*
      - -1: N/A
      - 0: Name
      - 1: Mediocre ReadMe
      - 2: Good ReadMe
   3. *Type:*
      - 0: Tool/Package
      - 1: Repository (data AND code)
      - 2: Data (ONLY data is available)
      - 3: Demonstration (photos, videos, supplementary materials available)
      - 4: Code (ONLY code available, no data)
      - 5: No Code and No Data (empty repo)
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
      - 2: Doesn't Run (Does not compile even after edits)
      - 3: Ran and Does Not Compile (requires extra components/hardware (i.e., GPU, phone, Raspberry Pi, etc. not explicitly mentioned in repo/paper)
      - 4: Not Ran (requires extra components/hardware explicitly mentioned in paper/repo)
   8. *Output Matches:*
      - -1: Does Not Match (A tool/repo not designed/made for reproducibility)
      - 0: Output Does Not Match (Output is +/-10% difference compared to claims of paper.)
      - 1: Output Matches (Best Effort, the output is within +/-10% difference compared to claims of paper)
   9. *Hardware:*
       - Free Response, list of extra hardware required to reproduce
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
3. [***full***](full) folder: contains merged rows from data in ***evaluation*** folder for executing Coxcomb graphs.
4. [***tier1.csv:***](tier1.csv) This file contains USENIX Security (Tier 1 Security Conferences) data from previous work required to visualize Figure 6 in our paper.
5. [***emails.pickle:***](emails.pickle) Pickle file containing PDF naming schemes and associated email extensions of authors from each paper. Required to visualize Figure 9 in the paper.
   
## Scripts
Scripts used for analyses and figures are located in the ***scripts*** folder. To reproduce our figures, please run all cells in order after satisfying all dependency requirements listed below. All scripts for creating figures use ***Python 3.9.13*** and require changing the file/folder paths (Areas where file *PATH* must be changed/added are written in **bold** or commented within each script):
1. [*figures_4_and_6.ipynb:*](scripts/figures_4_and_6.ipynb) This Jupyter Notebook script contains the codes to reproduce Figure 4 (Papers with Code by Year) and Figure 6 (Code Compiles by Conference) in the paper.
   - The following packages are used to run this code:
     ```
     matplotlib==3.5.2
     numpy==1.23.5
     pandas==1.4.4
     plotly==5.9.0
     plotly_express==0.4.1
     seaborn==0.11.2
     ```
2. [*coxcombs.ipynb:*](scripts/coxcombs.ipynb) This script reproduces Figure 2 (Indirect Study) and Figure 3 (Direct Study) from the paper.
   - Packages required to run this script:
     ```
     matplotlib==3.5.2
     numpy==1.23.5
     pandas==1.4.4
     seaborn==0.11.2
     ```
3. [*figure_10.ipynb:*](scripts/figure_10.ipynb) Reproduces Figure 10 from the paper (Reproducibility by Funding Agency).
   - Packages required to run this script:
     ```
     nltk==3.7
     numpy==1.23.5
     pandas==1.4.4
     ```
   - *This figure may vary slightly for Funding Agency labels with a count <= 3, due to the number of Funding Agencies with equal counts.*
4. [*figure_9.ipynb:*](scripts/figure_9.ipynb) Reproduces Figure 9 from the paper (Code Compiles by Affiliation).
   - Packages required to run this script:
     ```
     numpy==1.23.5
     pandas==1.4.4
     ```

<a id="reproduce_steps"></a>  
## Steps to Reproduce
1. Install the requirements listed above for each script (scripts were created using ***Python 3.9.13***).
2. Download data and scripts using the command (in a terminal):
   ```
    https://github.com/tier2-reproducibility/reproducibility.git
   ```
3. Modify the *PATH* variable(s) in each script to match your own local file path.
4. Run each cell (in order) for each script by starting a Jupyter Notebook session with ```jupyter notebook``` and selecting the script you would like to run in the [***scripts***](scripts) folder (i.e., *coxcombs.ipynb*).

## Docker

<a id="embeddings_clustering"></a>
## Embeddings and Clustering
