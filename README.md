# Disease Intelligence: A Novel Computational Framework for High-Quality Gene-Disease Association Discovery

[![Paper](https://img.shields.io/badge/Paper-IEEE_Xplore-blue)](https://ieeexplore.ieee.org/document/11318798)

This repository contains the official implementation of the paper:
**"A Novel Computational Framework for High-Quality Gene-Disease Association Discovery"** by Jatin Kansal, Satwinder Singh, and Parneet Kaur.

📝 **Read the full paper on IEEE Xplore**: [https://ieeexplore.ieee.org/document/11318798](https://ieeexplore.ieee.org/document/11318798)

## Abstract
The identification of disease-gene associations is at the centre of precision medicine and drug development progress. However, current computational approaches have serious issues with data quality and poor protein identifier mapping success rates. This framework presents an enhanced multi-database integration pipeline that addresses these critical issues by incorporating intelligent pattern-based filtering and a novel three-stage UniProt mapping strategy. The framework consolidates data from five biomedical databases (OpenTargets, OMIM, KEGG, CTD, ClinVar) by applying advanced filtering algorithms that remove HTML artefacts, numeric IDs, and random alphanumeric codes while retaining valid gene symbols and their UniProt IDs. Experimental validations performed on five benchmark diseases (Diabetes, Cardiovascular Disease, Cancer, Alzheimer’s Disease, and Asthma) demonstrate remarkable results: 90% gene quality and 620% UniProt mapping success rate improvement. Processing times have also been reduced by 53%.

## 🚀 Major Improvements

### ✅ **Enhanced Gene Quality (90% improvement)**
- **Intelligent junk filtering**: Removes HTML artifacts, numeric IDs, random codes
- **Pattern-based validation**: Validates legitimate gene symbols (2-15 chars, proper format)
- **Database-specific cleaning**: Custom filters for OMIM, KEGG, and other sources

### ✅ **Superior UniProt Mapping (620% improvement)**
- **Multi-stage mapping**: Primary Batch Mapping → Individual Retry → Synonym Mapping
- **Synonym lookup**: 50+ alternative gene names for better matching
- **Enhanced retry logic**: Multiple query formats with exponential backoff
- **Batch optimization**: Improved batch sizes and timeout handling

### ✅ **Comprehensive Database Integration**
- **OpenTargets**: Increased to 200 targets per disease with GraphQL query optimization.
- **KEGG**: Converts numeric IDs to actual gene symbols via API.
- **OMIM**: Aggressive filtering with string length and composition validation.
- **CTD**: Improved error handling with fallback text parsing.
- **ClinVar**: Enhanced NCBI E-utilities integration.

## File Structure

```text
disease_gene_mapper/
├── main_disease.py         # Main entry point for the pipeline
├── disease_normalizer.py   # Disease name standardization (EBI OLS, NCBI MeSH)
├── database_searchers.py   # Advanced database search with pattern filtering
├── uniprot_mapper.py       # Three-stage UniProt mapping strategy
├── excel_writer_disease.py # Results integration and validation
├── requirements.txt        # Python dependencies
└── README.md               # This documentation
```

## Performance Comparison

Experimental validations performed on five benchmark diseases (Diabetes, Cardiovascular Disease, Cancer, Alzheimer’s Disease, and Asthma) demonstrate remarkable results against baseline traditional approaches.

| Metric | Baseline | Enhanced | Improvement |
|--------|----------|----------|-------------|
| **Gene Quality** | 50.0% | 100.0% | 🎯 **+50%** |
| **UniProt Success** | 5.9% | 42.7% | 🚀 **+620%** |
| **Critical Gene Mapping** | 0/10 | 8/10 | ✅ **+800%** |
| **Processing Time** | 150s | 70s | ⚡ **-53%** |
| **Database Coverage** | 3 | 5 | 📈 **+167%** |
| **Artifact Removal** | 0% | 56% | 🧹 **+56%** |

## Critical Gene Mapping Analysis

The improved pipeline successfully maps these essential genes computationally for the first time:

| Gene | Description | Baseline | Enhanced | Importance |
|------|-------------|----------|----------|------------|
| **INS** | Insulin | ❌ | ✅ | High |
| **INSR** | Insulin receptor | ❌ | ✅ | High |
| **GCK** | Glucokinase | ❌ | ✅ | High |
| **HNF1A** | Hepatocyte nuclear factor 1A | ❌ | ✅ | High |
| **PPARG** | PPAR gamma | ❌ | ✅ | High |
| **TCF7L2** | Transcription factor 7-like 2 | ❌ | ✅ | High |

## Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Jatink1210/disease-intelligence.git
   cd disease-intelligence
   ```
2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the enhanced pipeline**:
   ```bash
   python main_disease.py "diabetes"
   ```

## Citation
If you use this framework in your research, please cite our paper:
```bibtex
@article{kansal2024novel,
  title={A Novel Computational Framework for High-Quality Gene-Disease Association Discovery},
  author={Kansal, Jatin and Singh, Satwinder and Kaur, Parneet},
  journal={IEEE Xplore},
  year={2024},
  url={https://ieeexplore.ieee.org/document/11318798}
}
```

## License
This project is licensed under the **Academic and Non-Commercial Use License**. 
It is free to use, modify, and distribute for academic, educational, and non-commercial research purposes. Any commercial use, including integration into proprietary software or use by a commercial entity, is strictly prohibited without prior written permission from the author. See the [LICENSE](LICENSE) file for more details.