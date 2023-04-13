# VCF to GDS Conversion
### Description of VCF to GDS conversion on the UK Biobank RAP for STAAR processing

Due to the vcf file sizes on the DNAnexus platform (especially WGS), it may be necessary to reduce the amount of data contained within VCFs if wanting to merge all VCFs associated with a chromosome on a workstation for subsequent STAAR annotation and processing. Some applets are provided here that may help facilitate this process.

### Step 1: Trimming down data in the VCFs
See [here](https://github.com/drarwood/vcf_trimmer) for applet that removes fields and performs required filtering through bcftools.
This applet takes in a list of files as an input to process. This applet could be used across multiple jobs submitted on the DNAnexus platform which would require unique lists of VCFs to be split. 
#### Example: VCF file list generation for input:
You may want to process the 200K WGS data release, one chromosome at a time. This would require a list of VCFs associated with that chromosome. 
Furthermore, you may also want to submit 100 jobs whereby the list of VCFs associated with that chromosome is split into 100 unique and equally sized VCF lists.
Running the `get_vcf_file_list_by_chr_and_split.sh` bash script in this repo will produce the relevant input files for each chromosome for all 60,648 VCFs currently available.
#### Example: Running multiple jobs to trim the VCFs



### Step 2: Merging VCFs
See [here](https://github.com/drarwood/vcf_merger). Another applet wrapper for bcftools.

### Step 3: Converting VCF to GDS for subsequent annotation/analysis in the STAAR pipeline.
See [here](https://github.com/drarwood/vcf2gds). This applet comes with an R library that will be unpacked during runtime and used for data conversion.
