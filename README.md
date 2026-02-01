# LiveWeb-IE: A Benchmark For Online Web Information Extraction

This repository contains the official dataset for the paper: *LiveWeb-IE: A Benchmark For Online Web Information Extraction*.

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
- **Auto**: fueleconomy
- **Book**: booktoscrape
- **E-commerce**: sandboxoxlabio
- **Food**: thecocktaildb, themealdb
- **Library**: dp
- **Other**: quotestoscrape, scrapethissite
- **Sports**: thesportsdb

### Data Format

#### dataset.json
The main dataset file contains structured queries with the following fields:
- `website_id`: Unique identifier for the website
- `website`: Website domain name
- `group_id`: Group identifier for URL collections
- `group_url`: Path to the group.jsonl file
- `query_id`: Unique query identifier
- `query`: Natural language query
- `attribute`: List of attributes to extract
- `type`: Task complexity (type_1 to type_4)
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


## License and Terms of Use
The LiveWeb-IE benchmark is released strictly for **non-commercial research purposes only**. 

By downloading or using this dataset, you agree to the following terms:
1.  **Non-Commercial Use**: You may not use this dataset for any commercial purposes, including but not limited to training commercial models or enhancing commercial services.
2.  **Attribution**: Any publication or report using this dataset must cite the original paper (LiveWeb-IE: A Benchmark For Online Web Information Extraction, ICLR 2026).
3.  **No Redistribution without License**: You may not redistribute this dataset without including this license agreement.

This restriction complies with the ethical agreements made with the website providers included in this benchmark.

## Ethics & Data Usage
The construction of the LiveWeb-IE benchmark adhered to strict ethical guidelines to ensure the protection of website operators and user privacy. Our data collection process followed a multi-step approval protocol:

1.  **Policy Compliance**: We reviewed the `robots.txt` files and Terms of Use for each of the 15 websites included in the benchmark to ensure our research activities did not violate their stated policies.
2.  **Explicit Consent**: We proactively contacted the administrators of each website to explain the research purpose and formally requested permission. **We proceeded with data collection only after receiving explicit consent.**
3.  **Public Information**: The natural language queries in this benchmark are intentionally curated to extract only publicly available information.
4.  **Privacy Protection**: The data collection and annotation processes were designed to minimize any risk of exposing private data.

For further details, please refer to the "Ethics Statement" section in our paper.

## Citation
If you use this dataset in your research, please cite our paper:

```bibtex
@inproceedings{yang2026livewebie,
  title        = {LiveWeb-IE: A Benchmark For Online Web Information Extraction},
  author={Yang, Seungbin and Kim, Jihwan and Choi, Jaemin and Kim Dongjin and Yang, Soyoung and Park, ChaeHun and Choo, Jaegul},
  booktitle={The Fourteenth International Conference on Learning Representations},
  year         = {2026},
  url={https://openreview.net/forum?id=bIODmQ1TNd}
}