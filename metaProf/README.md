
# **MetaProf: a containerized/singularized environment for taxonomic and functional profiling of metagenomic shotgun data**

Author: Monica R. Ticlla

## **Dependencies:**

- Singularity 3.4.1

## **Installation:**

- Download the container from SingularityHub (strongly recommended)

    ```
    user@local_machine:> singularity pull --name meta16S.sif shub://mticlla/OmicSingularitites:MetaProf
    ```

- or, build the container using the singularity definition file:

    ```
    user@local_machine:> wget https://github.com/mticlla/OmicSingularities/blob/master/metaProf/Singularity.MetaProf
    user@local_machine:> sudo singularity build metaProf.sif ./Singularity.MetaProf
    ```

## **Installed tools:**


```bash
%%bash
# With Singularity v2
# singularity apps metaProf
# With Singularity v3
singularity inspect --list-apps metaProf.sif
```

    ==apps==
    BreadCrumbs
    GraPhlAn
    HUMAnN2
    MetaPhlAn2
    PanPhlAn
    StrainPhlAn
    


## **Basic usage:**


```bash
%%bash
singularity run-help metaProf.sif
```

    This image contains software for taxonomic and functional profiling of microbial 
    communities from metagenomic shotgun sequencing data.
    It was built with CentOS 7 as base OS and Python 3.7.4
    
    Usage:
    - To list available Apps:
      singularity apps <CONTAINER_PATH> #For Singularity 2
      singularity inspect --list-apps <CONTAINER_PATH> #For Singularity 3
    - To get help for a particular APP:
      singularity help --app <APP_NAME> <CONTAINER_PATH> #For Singularity 2
      singularity run-help --app <APP_NAME> <CONTAINER_PATH> #For Singularity 3
    - To run a particular APP:
      singularity run --app <APP_NAME> <CONTAINER_PATH>
    - To execute a bash command within a particular APP environment:
      singularity exec --app <APP_NAME> <CONTAINER_PATH> <CMD>
    
    


## **Advanced usage:**

**MetaPhlAn2:**


```bash
%%bash
singularity run --app MetaPhlAn2 metaProf.sif
```

    
        MetaPhlAn2 is a tool for profiling the composition of microbial communities from 
        metagenomic shotgun sequencing data.
        
        For help, run:
            $ singularity exec --app MetaPhlAn2 <CONTAINER_PATH> metaphlan2.py --help
        or
            $ singularity run --app MetaPhlAn2 <CONTAINER_PATH> metaphlan2.py --help
        
        If you use MetaPhlAn2, please cite:
        
        For more information on the technical aspects of MetaPhlAn2, or to cite MetaPhlAn2 
        in your work, please refer to:
        MetaPhlAn2 for enhanced metagenomic taxonomic profiling. Duy Tin Truong, Eric A Franzosa, 
        Timothy L Tickle, Matthias Scholz, George Weingart, Edoardo Pasolli, Adrian Tett, 
        Curtis Huttenhower & Nicola Segata. Nature Methods 12, 902-903 (2015)
        


**GraPhlAn:**


```bash
%%bash
singularity run --app GraPhlAn metaProf.sif
```

    
        GraPhlAn has two main scripts: graphlan_annotate.py, graphlan.py.
        
        For help, run:
            $ singularity exec --app GraPhlAn <CONTAINER_PATH> graphlan.py --help
        or
            $ singularity run --app GraPhlAn <CONTAINER_PATH> graphlan.py --help
        



```bash
%%bash
singularity exec metaProf.sif bash -c 'source activate py27graphlan && graphlan.py --help | head -n8'
```

    usage: graphlan.py [-h] [--format ['output_image_format']]
                       [--warnings WARNINGS] [--positions POSITIONS]
                       [--dpi image_dpi] [--size image_size] [--pad pad_in]
                       [--external_legends] [--avoid_reordering] [-v]
                       input_tree output_image
    
    GraPhlAn 1.1.3 (5 June 2018) AUTHORS: Nicola Segata (nsegata@hsph.harvard.edu)
    


**StrainPhlAn**


```bash
%%bash
singularity run --app StrainPhlAn metaProf.sif
```

    
        StrainPhlAn is a tool for strain-level resolution of species across large sample sets, 
        based on single nucleotide polymorphisms (SNPs) within conserved and unique species marker genes.
        
        For help, run:
            $ singularity exec --app StrainPhlAn <CONTAINER_PATH> strainphlan.py --help
        or
            $ singularity run --app StrainPhlAn <CONTAINER_PATH> strainphlan.py --help
        
        For more information on the technical aspects of StrainPhlAn, or to cite StrainPhlAn 
        in your work, please refer to:
        Microbial strain-level population structure and genetic diversity from metagenomes. 
        Duy Tin Truong, Adrian Tett, Edoardo Pasolli, Curtis Huttenhower, & Nicola Segata. 
        Genome Research 27:626-638 (2017)
        



```bash
%%bash
singularity exec metaProf.sif bash -c 'source activate py27strphlan && strainphlan.py --help | head -n5'
```

    usage: strainphlan.py [-h] [--ifn_samples IFN_SAMPLES [IFN_SAMPLES ...]]
                          [--ifn_second_samples IFN_SECOND_SAMPLES [IFN_SECOND_SAMPLES ...]]
                          [--ifn_representative_sample IFN_REPRESENTATIVE_SAMPLE]
                          [-x INDEX] [--mpa_pkl MPA_PKL] --output_dir OUTPUT_DIR
                          [--ifn_markers IFN_MARKERS] [--nprocs_main NPROCS_MAIN]


**PanPhlAn**


```bash
%%bash
singularity run --app PanPhlAn metaProf.sif
```

    
        Pangenome-based Phylogenomic Analysis (PanPhlAn) is a strain-level metagenomic 
        profiling tool for identifying the gene composition and in-vivo transcriptional 
        activity of individual strains in metagenomic samples.
        
        PanPhlAn has three main scripts: panphlan_pangenome_generation.py, panphlan_map.py, 
        and panphlan_profile.py.
        
        For help, run:
            $ singularity exec --app PanPhlAn <CONTAINER_PATH> panphlan_map.py --help
        or
            $ singularity run --app PanPhlAn <CONTAINER_PATH> panphlan_map.py --help
        
        For more information on the technical aspects of PanPhlAn, or to cite PanPhlAn in your work, 
        please refer to:
        Matthias Scholz, Doyle V. Ward, Edoardo Pasolli, Thomas Tolio, Moreno Zolfo, Francesco Asnicar, 
        Duy Tin Truong, Adrian Tett, Ardythe L. Morrow and Nicola Segata. 
        Strain-level microbial epidemiology and population genomics from shotgun metagenomics. 
        Nature Methods 13, 435–438, 2016.
        



```bash
%%bash
singularity exec metaProf.sif bash -c 'source activate py36panphlan && panphlan_map.py --help | head -n5'
```

    usage: panphlan_map.py [-h] [-i INPUT_FILE]
                           [--i_bowtie2_indexes INPUT_BOWTIE2_INDEXES]
                           [--fastx FASTX_FORMAT] -c CLADE_NAME [-o OUTPUT_FILE]
                           [-b OUTPUT_BAM_FILE] [-p NUMOF_PROCESSORS]
                           [-m MEMORY_GIGABTES_FOR_SAMTOOLS]


**HUMAnN2**


```bash
%%bash
singularity run --app HUMAnN2 metaProf.sif
```

    
        HUMAnN (HMP Unified Metabolic Analysis Network 2) is a pipeline for efficiently and 
        accurately profiling the presence/absence and abundance of microbial pathways in 
        a community from metagenomic or metatranscriptomic sequencing data (typically millions 
        of short DNA/RNA reads).
        
        For help, run:
            $ singularity exec --app HUMAnN2 <CONTAINER_PATH> humann2 --help
        or
            $ singularity run --app HUMAnN2 <CONTAINER_PATH> humann2 --help
        
        For more information on the technical aspects of HUMAnN2, or to cite HUMAnN2 in your work, 
        please refer to:
        Franzosa EA*, McIver LJ*, Rahnavard G, Thompson LR, Schirmer M, Weingart G, Schwarzberg Lipson K, 
        Knight R, Caporaso JG, Segata N, Huttenhower C. Species-level functional profiling of metagenomes 
        and metatranscriptomes. Nat Methods 15: 962-968 (2018). 
        



```bash
%%bash
singularity exec metaProf.sif bash -c 'source activate humann2 && humann2 --help | head -n5'
```

    usage: humann2 [-h] [--version] [-v] [-r] [--bypass-prescreen]
                   [--bypass-nucleotide-index] [--bypass-translated-search]
                   [--bypass-nucleotide-search] -i <input.fastq> -o <output>
                   [--nucleotide-database <nucleotide_database>]
                   [--annotation-gene-index <8>]


**BreadCrumbs**


```bash
%%bash
singularity run --app BreadCrumbs metaProf.sif
```

    
        BreadCrumbs is an unofficial collection of scripts and code intended to consolidate 
        functions for tool development and contain scripts for command line access to commonly 
        used functions. Breadcrumbs tends to include functionality associated with metagenomics 
        analysis but you never know what you will find!
        
        A quick description of the scripts include:
        - Hclust.py Flexible script to create a visualization of hierarchical clustering of abundance 
          tables (or other matrices).
        - scriptBiplotTSV.R Allows one to plot a tsv file as a biplot using nonmetric multidimensional scaling.
        - scriptPlotFeature.py Allows one to plot a histogram, boxplot, or scatter plot of a bug or metadata in 
          an abundance table. Will work on any row in a matrix.
        - scriptManipulateTable.py Allows one to perform common functions on an abundance table including, 
          summing, normalizing, filtering, stratifying tables.
        - scriptPcoa.py Allows one to plot a principle covariance analysis (PCoA) plot of an abundance table.
        - scriptConvertBetweenBIOMAndPCL.py Allows one to convert between BIOM and PCL file formats.
        - strainphlan_ggtree.R Allows one to plot dendrograms from StrainPhlAn outputs.
        - strainphlan_ordination.R Allows one to plot an ordination from StrainPhlAn outputs.
    
        For help, run:
            $ singularity run --app BreadCrumbs <CONTAINER_PATH> <SCRIPT> --help
        
        Examples:
            $ singularity exec --app BreadCrumbs <CONTAINER_PATH> Hclust.py --help
            or
            $ singularity run --app BreadCrumbs <CONTAINER_PATH> Hclust.py --help
        
        For more information on the technical aspects of BreadCrumbs, please refer to:
        https://bitbucket.org/biobakery/breadcrumbs/src/default/
        


or alternatively:


```bash
%%bash
singularity exec metaProf.sif bash -c 'source activate py27breadcrumbs && strainphlan_ggtree.R --help'
```

    Usage: strainphlan_ggtree.R RAxML_bestTree.species.tree metadata.txt species.fasta output_tree_1.png output_tree_2.png
    
    
    This script generates dendrograms from StrainPhlAn output files.
    
    The following positional arguments are required:
    
    RAxML_bestTree.species.tree (Input file): This tree is generated by StrainPhlAn
    metadata.txt (Input file): This is the metadata file for the tree
    species.fasta (Input file): This fasta file is generated by StrainPhlAn
    output_tree_1.png (Output file): This is the first dendrogram image written
    output_tree_2.png (Output file): This is the second dendrogram image written
    
    Options:
    	-h, --help
    		Show this help message and exit
    
    

