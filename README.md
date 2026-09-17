# Malicious-HDG

Heterogeneous Dynamic Graph framework for binary classification of wordlist-DGA domains vs benign domains.

## Dataset

The raw dataset files are not included in this repository.

Expected raw files:


data_raw/zenodo/
 malware.json
 benign_umbrella.json


Dataset used for experiments:

- Total domains: 30,000
- Malicious domains: 15,000
- Benign domains: 15,000

Sources:
- Malicious: DGArchive
- Benign: Zenodo benign slice

## Graph Construction

Node types:

- Domain
- IP
- Nameserver
- Registrar
- ASN

The pipeline creates weekly heterogeneous graph snapshots.

## Reproduction

After placing the raw JSON files:

```bash
python src/scripts/01_parse_zenodo_unified.py
python src/scripts/02_build_node_tables.py
python src/scripts/03_build_edges_snapshots.py
python src/scripts/04_build_heterodata.py
