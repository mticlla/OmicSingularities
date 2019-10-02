# Pre-processing QC (preQC)

This image contains software for quality control and preprocessing of sequencing data. It was built with CentOS 7 as base OS and Python 3.6. Although this is a companion container of the MetagenomicSnake workflow, it can also be used separately.

---
## Installed Tools
- FastQC v0.11.8
- fastp v0.20.0
- multiqc v1.8.dev0
- cutadapt v2.3
- BBTools v38.39

---
## Usage:
- To list available Apps:
singularity apps <CONTAINER_PATH>
- To get help for a particular APP:
singularity help --app <APP_NAME> <CONTAINER_PATH>
- To run a particular APP:
singularity run --app <APP_NAME> <CONTAINER_PATH>
