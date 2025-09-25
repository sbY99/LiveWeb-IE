# LiveWeb-IE: A Benchmark For Online Web Information Extraction

This repository contains the official implementation for the paper: *LiveWeb-IE: A Benchmark For Online Web Information Extraction*.

## Dataset Structure

The LiveWeb-IE benchmark consists of 15 websites across 8 diverse domains, designed for evaluating web information extraction systems on live websites. The dataset is organized as follows:

### Directory Structure

```
LiveWeb_IE/
├── dataset.json              # Main dataset file with queries and metadata
├── groundtruth/              # Ground truth annotations organized by domain
│   ├── academic/             # Academic websites (arxiv, huggingface, iclr, etc.)
│   ├── auto/                 # Automotive websites
│   ├── book/                 # Book-related websites
│   ├── ecommerce/            # E-commerce platforms
│   ├── food/                 # Food and recipe websites
│   ├── library/              # Digital library websites
│   ├── other/                # Other miscellaneous websites
│   └── sports/               # Sports-related websites
└── [website_name]/           # Individual website directories
    └── group/
        └── group.jsonl       # URL groups
```

### Website Domains

The benchmark includes websites from the following domains:

- **Academic**: arxiv, huggingface, iclr, icml, neurips, marinespecies
- **E-commerce**: booktoscrape, quotestoscrape, scrapethissite
- **Food & Beverages**: thecocktaildb, themealdb
- **Sports**: thesportsdb
- **Automotive**: fueleconomy
- **Development**: sandboxoxlabio
- **Productivity**: dp

### Data Format

#### dataset.json
The main dataset file contains structured queries with the following fields:
- `website_id`: Unique identifier for the website
- `website`: Website domain name
- `group_id`: Group identifier for URL collections
- `group_url`: Path to the group.jsonl file
- `query_id`: Unique query identifier
- `query`: Natural language extraction query
- `attribute`: List of attributes to extract
- `type`: Task complexity type (type_1 to type_4)
- `label`: Paths to ground truth files
- `sample_id`: Unique sample identifier

#### group.jsonl
Each website's group.jsonl file contains:
- `group_url`: List of URLs for evaluation

#### Ground Truth Files
Ground truth annotations are stored as text files in the `groundtruth/` directory, organized by domain and named with the format: `{website}-{group_id}-{attribute}.txt`

### Task Complexity Types

The benchmark organizes extraction tasks into four complexity levels:
- **Type I**: Single attribute, single value
- **Type II**: Single attribute, multiple values
- **Type III**: Multiple attributes, single value each
- **Type IV**: Multiple attributes, multiple values each

This benchmark enables comprehensive evaluation of web information extraction systems under realistic, live web conditions.