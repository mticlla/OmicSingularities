
# **meta16S** : a containerized environment for 16S-rRNA-gene sequencing data analysis 

Author: Monica R. Ticlla

## **Dependencies:**

- Singularity 3.4.1


```python
!singularity --version
```

    singularity version 3.4.1-1


## **Installed tools:**

- QIIME2 V2019.7
- ...


```python
!singularity inspect --list-apps meta16S.sif
```

    ==apps==
    QIIME2
    


## **Container usage:**

- Download the container from SingularityHub (strongly recommended)
```
user@local_machine:> singularity pull --name meta16S.sif shub://mticlla/OmicSingularitites:meta16S
```

- or, build the container using the Singularity definition file:
```
user@local_machine:> sudo singularity build meta16S.sif ./Singularity.meta16S
```

- To get a list of available apps in the container:
```
user@local_machine:> singularity inspect --list-apps meta16S
```

## **Help**

**Help for the container**


```python
!singularity run-help meta16S.sif
```

    This image contains software for processing of 16S-rRNA gene sequencing data.
    It was built with CentOS 7 as base OS and Python 3.6.
    
    Usage:
    - To list available Apps:
    singularity apps <CONTAINER_PATH>
    - To get help for a particular APP:
    singularity help --app <APP_NAME> <CONTAINER_PATH>
    - To run a particular APP:
    singularity run --app <APP_NAME> <CONTAINER_PATH>
    
    


**Help for an app in the container**


```python
!singularity run-help --app QIIME2 meta16S.sif
```

      From [QIIME2 website](https://qiime2.org/)
    
      QIIME 2TM is a next-generation microbiome bioinformatics platform that is
      extensible, free, open source, and community developed.
    
      USAGE:
      Once the container has been built, QIIME2 commands/subcommands/plugins (e.g
      qiime info) can be called in any of the following ways:
    
      - Option 1: from inside the container
      # you first need to run a shell within the container
      user@my_machine:> singularity shell [shell options .e.g --writable] <container>
      # Now inside the Singularity container
      Singularity my_container:> source activate qiime2-2019.7
      # call the qiime commands
      Singularity container:> qiime --help
    
      - Option 2: run it as SCIF app from outside the container
      user@my_machine:> singularity run --app QIIME2 <CONTAINER_PATH>
      or
      user@my_machine:> singularity exec --app QIIME2 <CONTAINER_PATH> qiime


## **Tutorials**

- [QIIME2](./tutorials/qiime2.ipynb)
