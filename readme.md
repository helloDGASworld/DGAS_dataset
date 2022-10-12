A brief introduction to the dataset provided by DGAS.

## File List
- **desc.pkl**: The list of queries.
- **apiseq.pkl**: The list of API sequences.
- **api2doc.pkl**: The dictionary with API keys and documentation values. When an API has no documentation, the keys of the dictionary will not contain the API.

## Specification
- The query and the API sequence are matching if they share a same index in the list.
- You can load the files using the following python code.

````python
import pickle

def load_pkl(path):
    with open(path, 'rb') as f:
        data = pickle.load(f)
    return data

desc_list = load_pkl('./desc.pkl')
apiseq_list = load_pkl('./apiseq.pkl')
api2doc_dict = load_pkl('./api2doc.pkl')
````
- We highly recommend stemming the words before using this dataset. You can refer to the following python code.
````python
from nltk import PorterStemmer

stemmer = PorterStemmer()

text = ['your', 'text', ...]
text = [stemmer.stem(word) for word in text]
````