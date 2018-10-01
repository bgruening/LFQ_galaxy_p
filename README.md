# LFQ_galaxy_p
Enable protein summarisation and quantitation in Galaxy-P

On commandline:

``` Rscript ./quantitation.r [moff_file] [meta_file] [only_summarisation] [CPU]``` 

[moff_file]: path to input file from moff (at least 2 samples)

[meta_file]: path to tsv formatted file with at least 2 columns
                    sample: column with sample names as defined in the moff output
                    condition:   the condition/treatment group the sample belongs to.
                    OPTIONAL columns for other factors that can have affect on the samples and that are  different for different samples, eg:
                    lab: the lab of which the sample is from
                    machine: the machine by which the the sample is processed

[cpu]: number of cores to use; 0 = all cores available. 



**Dependencies**
- cran:
  - tidyverse
  - furrr
  - lme4
- bioconductor:
  - MSnbase
  - MSqRob
