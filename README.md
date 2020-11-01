# Natural Language Processing Assignment 1 (Group 19)

## Folder Structure
#### Root folder (./)
- Jupyter notebook used for reference while writing the report
	- [medical.ipynb](medical.ipynb) - Token analysis for medical domain
	- [se.ipynb](se.ipynb) - Token analysis for Software Engineering domain
	- [sg_law.ipynb](sg_law.ipynb) - Token analysis for Law domain
	- [pair_ranker.ipynb](pair_ranker.ipynb) - Pair Ranker for 3.2
	- [for 3.3.ipynb](for%203.3.ipynb) - Application for 3.3
- Custom libraries for Token analysis for medical domain
	- [data_analysis.py](data_analysis.py)
	- [writer.py](writer.py)
- Crawled data for analysis
	- [softwareengineering.txt](softwareengineering.txt)
	- [sg_law_cleaned.txt](sg_law_cleaned.txt)
- [requirements.txt](requirements.txt) - For installation

#### Medical folder (./Medical)
- Raw data for medical

#### Outputs folder (./Outputs)
- Processed data for medical
	
#### Crawlers folder (./Crawlers)
- Crawler scripts
	- [software_engineering.py](software_engineering.py) - Crawls data for Software Engineering
	- [statues.py](statues.py) - Crawls data for Law
	- [statues2.py](statues2.py) - Cleans data for Law

## Installation Instructions

### Optional Step
You may want to initialize a python virtual environment first before installing dependencies to run this project.
```Shell
python -m venv .env
```
Next, you will need to activate this virtual environment.
For Windows:
```shell
.env\Scripts\activate
```
For Unix:
```Shell
.env\Scripts\activate.sh
```
### Install dependencies
We have included a `requirements.txt` which includes the python libraries and their respective versions that is used at this point of writing. You can install them by running:
```Shell
pip install -r requirements.txt
```
As we also uses `spaCy` we need to download its model before it is usable.
```Shell
python -m spacy download en_core_web_sm
```
## Running instruction
We developed these python scripts and Jupyter Notebook on PyCharm and Visual Studio Code. Both of which also supports Jupyter Notebook. You may run the python scripts either from your preferred IDE or from command line directly. The Jupyter Notebooks (.ipynb) files can only be opened by Jupyter Notebook from Anaconda or on IDE which supports Jupyter Notebook. 
