# LFQ_galaxy_p
Enable protein summarisation and quantitation in Galaxy-P

**How to use**

On commandline:

``` Rscript ./quantitation.r [moff_file] [meta_file] [only_summarisation] [CPU]``` 

[moff_file]: path to input file from moff (at least 2 samples)

[meta_file]: path to tsv formatted file with at least 2 columns
- sample: column with sample names as define d in the moff output
- condition:   the condition/treatment group the sample belongs to.
 
 OPTIONAL columns for other factors that can have an effect on the analysis (different for different samples), eg:
- lab: the lab of which the sample is from
- machine: the machine by which the the sample is processed

[only_summarisation]: Only do summarisation (1) or do sumarisation + quantification(0)
Summarisation is done through robust regression to take also the peptide effect into account
When only sample is present, calculatie median peptide intensity

[cpu]: number of cores to use; 0 = all cores available. parallelization is only used for the quantification step.

**example**

Do summarization and quantification using all available cores

```Rscript quantitation.r example/Galaxy211-\[moFF_on_data_15,_data_14,_and_others__peptide_summary\].tabular example/meta.tsv 0 0 ```

**Dependencies**
- cran:
  - tidyverse
  - furrr
  - lme4
- bioconductor:
  - MSnbase
  - MSqRob
