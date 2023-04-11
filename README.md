# VCF to GDS Conversion
### Description of VCF to GDS conversion on the UK Biobank RAP for STAAR processing

Due to the vcf file sizes on the DNAnexus platform (espeically WGS), it may be necessary to reduce the amount of data contained within VCFs if wanting to merge all VCFs assocaited with a chromosome on a workstation. Some applets have been provided that may help facilitate this process

### Step 1: Trimming down data in the VCFs
See [here](https://github.com/drarwood/vcf_trimmer) for applet that removes fields and performs required filtering through bcftools.

### Step 2: Merging VCFs
See [here](https://github.com/drarwood/vcf_merger). Another applet wrapper for bcftools.

### Step 3: Converting VCF to GDS for subsequent annotation/analysis in the STAAR pipeline.
See [here](https://github.com/drarwood/vcf2gds). This applet comes with an R library that will be unpacked during runtime and used for data conversion.
