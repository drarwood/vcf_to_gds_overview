# VCF to GDS Conversion
### Description of VCF to GDS conversion on the UK Biobank RAP for STAAR processing

Due to the vcf file sizes on the DNAnexus platform (especially WGS), it may be necessary to reduce the amount of data contained within VCFs if wanting to merge all VCFs associated with a chromosome on a workstation for subsequent STAAR annotation and processing. Some applets are provided here that may help facilitate this process.

### Step 1: Trimming down data in the VCFs
See [here](https://github.com/drarwood/vcf_trimmer) for applet that removes fields and performs required filtering through bcftools.
This applet takes in a list of files as an input to process. This applet could be used across multiple jobs submitted on the DNAnexus platform which would require unique lists of VCFs to be split. 
As an example, you may want to process one chromosome at a time which would require a list of VCFs associated with that chromosome which is subsequently split into 100 equally sized lists, for example.
`get_vcf_file_list_by_chr_and_split.sh` provides code that would do this for the 200K WGS VCFs available on the UK Biobank RAP.
 


### Step 2: Merging VCFs
See [here](https://github.com/drarwood/vcf_merger). Another applet wrapper for bcftools.

### Step 3: Converting VCF to GDS for subsequent annotation/analysis in the STAAR pipeline.
See [here](https://github.com/drarwood/vcf2gds). This applet comes with an R library that will be unpacked during runtime and used for data conversion.
