# GOV.UK Search Concepts Experiments

Experiments to extract taxonomy concepts from historical search queries performed on [GOV.UK].

## Requirements

- [Python 3]
- Google Analytics search report CSV
- Inventory CSV

## Setup

```sh
$ git clone git@github.com:alphagov/govuk-search-concepts-experiments.git
$ cd govuk-search-concepts-experiments
$ python3 -m venv .venv
$ source .venv/bin/activate
$ pip install -r requirements.txt
```

## Usage

Extract search terms applicable to the inventory:

```sh
$ ./extract_inventory_searches /path/to/inventory.csv /path/to/search-data.csv | tee /dev/tty > terms.csv
```

Cluster search terms based on [term frequency–inverse document frequency][Tf–idf]:

```sh
$ ./cluster_search_terms 100 terms.csv | tee /dev/tty > clusters.txt
```

[gov.uk]: https://www.gov.uk/
[python 3]: https://www.python.org/download/releases/3.0/
[tf–idf]: https://en.wikipedia.org/wiki/Tf%E2%80%93idf
