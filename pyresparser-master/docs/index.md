# Pyresparser

A simple resume parser used for extracting information from resumes

# Features

- Extract name
- Extract email
- Extract mobile numbers
- Extract skills
- Extract total experience
- Extract college name
- Extract degree
- Extract designation
- Extract company names

# Getting Started

## Installation

- You can install this package using

```bash
pip install pyresparser
```

- For NLP operations we use spacy and nltk. Install them using below commands:

```bash
# spaCy
python -m spacy download en_core_web_sm

# nltk
python -m nltk.downloader words
python -m nltk.downloader stopwords
```

## Usage

- Import it in your Python project

```python
from pyresparser import ResumeParser
data = ResumeParser('/path/to/resume/file').get_extracted_data()
```

## Result

The module would return a list of dictionary objects with result as follows:

## Supported Resume File Formats

- Parsing of PDF and DOCx files are supported on all Operating Systems
- If you want to parse DOC files you can install [textract](https://textract.readthedocs.io/en/stable/installation.html) for your OS (Linux, MacOS)
- Note: You just have to install textract (and nothing else) and doc files will get parsed easily

# Advanced Options

## Explicitly specifying skills file

Pyresparser comes with built-in skills file that defaults to many technical skills. You can find the default skills file [here](https://github.com/OmkarPathak/pyresparser/blob/master/pyresparser/skills.csv).

For extracting data against your specified skills, create a CSV file with no headers.

```python
from pyresparser import ResumeParser
data = ResumeParser('/path/to/resume/file', skills_file='/path/to/skills.csv').get_extracted_data()
```

## Explicitly providing regex to parse phone numbers

While pyresparser parses most of the phone numbers correctly, there is a possibility of new patterns being added in near future. Hence, we can explicitly provide the regex required to parse the desired phone numbers. This can be done using

```python
from pyresparser import ResumeParser
data = ResumeParser('/path/to/resume/file', custom_regex='pattern').get_extracted_data()
```