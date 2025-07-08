<div align="center">
  
# 🧩 Information Linking Queries
It performs API calls to Wikipedia, Wikidata, DBpedia, and ORCID to retrieve and integrate structured information from multiple open knowledge sources.

[![PyPi Version](https://img.shields.io/badge/PyPI-3776AB?logo=pypi&logoColor=white)](https://pypi.org/project/information-linking-queries/)

</div>

## Main dependencies
- python>=3.11
- SPARQLWrapper==2.0.0
- requests
  
## 🛠️ Instalation
```cmd
pip install linking-information-queries
```

## 🚀 Quickstart
```python
from information_linking_queries.information_linking_orcid import information_linking_orcid
from information_linking_queries.information_linking_apis import information_linking

orcid = information_linking_orcid(first_name="Julie", last_name="Costopoulos")
print(orcid)

info = information_linking(wikipedia_url="https://en.wikipedia.org/wiki?curid=18630637")
print(info)
```

```json
{"orcid-id": "0000-0001-9912-3171", "given-names": "Julie", "family-names": "Costopoulos", "credit-name": "Julie Costopoulos", "other-name": ["Julie S. Costopoulos", "Julie S. Gross", "Julie Gross"], "email": [], "institution-name": ["Florida Institute of Technology", "Florida State University", "New York University", "University of Florida"]}

{"description": "Translation is the communication of the meaning of a source-language text by means of an equivalent target-language text. The English language draws a terminological distinction (which does not exist in every language) between translating (a written text) and interpreting (oral or signed communication between users of different languages); under this distinction, translation can begin only after the appearance of writing within a language community.", "label": "Translation", "wikidata": "https://www.wikidata.org/wiki/Q7553", "aliases": ["translate", "translating"], "dbpedia": "http://dbpedia.org/resource/Translation"}
```

## 📊 Parameters for `information_linking_orcid`
* **`first_name`**: The first name of the author. **(Required)**  
* **`last_name`**: The last name of the author. **(Required)**  

## 📊 Parameters for `information_linking`
* **`wikipedia_url`**: The URL of a wikipedia entry (It has to be with with a curid such as 'https://en.wikipedia.org/wiki?curid=18630637'). **(Required)**  
* **`description`**: The first 2 sentences of a wikipedia entry, *(deafult=True)*, *(Values: True, False)*. *(Optional)*  
* **`label`**: The wikipedia title of a wikipedia entry, *(deafult=True)*, *(Values: True, False)*. *(Optional)*
* **`wikidata`**: The wikidata url of a wikipedia entry, *(deafult=True)*, *(Values: True, False)*. *(Optional)*
* **`aliases`**: The english wikidata aliases, *(deafult=True)*, *(Values: True, False)*. *(Optional)*
* **`dbpedia`**: The dbpedia url of a wikipedia entry, *(deafult=True)*, *(Values: True, False)*. *(Optional)*
