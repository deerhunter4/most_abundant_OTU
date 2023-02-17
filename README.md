# most_abundant_OTU

This script produce four files, from COI zOTU table:
- **barcode.txt** that, per each library/sample, contains info about most abundant zOTU (COI barcode), taxonomy and bacteria presence
- **barcode.fasta**, containing most abundant Eucaryotic zOTU sequence (COI barcode) per each library/sample
- **euc.txt**, containing information about Eucaryotic zOTU sequences that represents at least 5% of total Eucaryotic reads per library/sample,
               additionally zOTU are marked as potential Parasitoids or Contamination (e.g. barcode from other sample, food)
- **bac.txt**, containing information about all bacterial zOTUs in dataset

**Requirements:**

Unix environment, Python 3

**Usage:**

most_abundant_OTU.py input_file.txt

**Optional arguments:**

**-upper**  minimum abundance treshold that zOTU has to have to be considered as most abundand zOTU. If non of the zOTU abundance will match this requirement then library/sample will not be represented in barcode.txt file. To prevent this situacion default minimum abundance treshold is assigned to 0.00  
**-lower**  minimum abundance treshold that zOTU has to have to be considered as significant contaminant or parasitoid of particular library/sample (default: 0.05)  
**-reads**  minimum number of reads per library/sample to be included in the output files (default: 20)

**Example of input file:**

Input file is a final table generated by Symbiosis Evolution Group recommendet [amplicon analysis workflow](https://github.com/symPiotr/amplicon_analysis_pipeline/blob/main/20201218_Wasp_COI_pipeline.txt).

[test_zotu_table_expanded.txt](https://github.com/deerhunter4/most_abundand_COI/files/6128914/test_zotu_table_expanded.txt)

OTU_ID | OTU_assignment | Taxonomy | Sequence | Total | SZF2Y9_1 | SZF2Y9_2 | SZF2Y9_3 | SZF2Y9_4
-------|----------------|----------|----------|-------|----------|----------|----------|---------
Zotu4 | otu4 | Eukaryota(1.00),Arthropoda(1.00),(...) | AATAAATAATATAAGTT(...) | 2128 | 2126 | 0 | 0 | 2	
Zotu6 | otu6 | Bacteria(1.00),Proteobacteria(1.00),(...) | TATGAATAATTTAAGTT(...) | 72 | 0 | 72 | 0 | 0	

