# RIS Vetted Applications

This page contains basic information and user-friendly guides to running RIS-vetted
application containers on compute. This is `not` an inclusive list of usable applications, by
any means, and is intended solely as a starting point for new users.

This page does not include application containers where the user does not want,
or is forbidden, to put code into a public registry.

> ### Warning:
> 
> The application containers listed on this page have been vetted to start a
> shell in an interactive job at the time of testing and were confirmed
> working at the time they were tested. The level of security with
> non-RIS-hosted images is not guaranteed and has not been tested.
> 
> As such, we recommend to use RIS-hosted Docker images when possible. Please
> visit *this page* for a list of RIS supported Docker images.

> ### Note:
> 
> To successfully run `bsub` commands on this page, you must already be logged into the Compute Service:
> 
> `> ssh ${compute_username}@compute1-client-1.ris.wustl.edu`
> 
> If you are not connected to a a Medical School network (WUSM-secure, MSVPN),
> or the Danforth VPN, you will need to perform port forwarding before
> accessing a GUI (i.e. accessing a Jupyter notebook or RStudio session).
> 
> Documentation to forward ports is found *here.*

## Applications, Packages and Environment Images

<details>
  <summary>.NET Core</summary>

  - Registry Location: [https://hub.docker.com/_/microsoft-dotnet-core-sdk/](https://hub.docker.com/_/microsoft-dotnet-core-sdk/)
  - ".NET Core is an open-source, general-purpose development platform maintained by Microsoft and the .NET community on GitHub.
  It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications."
    - Source: [https://docs.microsoft.com/en-us/dotnet/core/](https://docs.microsoft.com/en-us/dotnet/core/)
  - Run interactive job:
  ```
  bsub -G ${group_name} -Is -q general-interactive -a 'docker(mcr.microsoft.com/dotnet/core/sdk)' /bin/bash
  ```
</details>

<details>
  <summary>Anaconda</summary>

  - Registry Location:
    - Using Python 3.5: [https://hub.docker.com/r/continuumio/anaconda3](https://hub.docker.com/r/continuumio/anaconda3)
    - Using Python 2.7: [https://hub.docker.com/r/continuumio/anaconda](https://hub.docker.com/r/continuumio/anaconda)
  - "Anaconda is the leading open data science platform powered by Python. The open source version of Anaconda is
  a high performance distribution and includes over 100 of the most popular Python packages for data science.
  Additionally, it provides access to over 720 Python and R packages that can easily be installed using the conda
  dependency and environment manager, which is included in Anaconda." - Source: [https://hub.docker.com/r/continuumio/anaconda3](https://hub.docker.com/r/continuumio/anaconda3)
  - Run interactive job:
  ```
  # Using Python 3.5:
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(continuumio/anaconda3)' /bin/bash

  # Using Python 2.7:
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(continuumio/anaconda)' /bin/bash
  ```
</details>

<details>
  <summary>AnnovarR</summary>

  - Registry Location: [https://registry.hub.docker.com/r/bioinstaller/annovarr](https://registry.hub.docker.com/r/bioinstaller/annovarr)
  - "The annovarR package provides R functions as well as database resources which offer an integrated
  framework to annotate genetic variants from genome and transcriptome data. The wrapper functions of
  annovarR unified the interface of many published annotation tools, such as VEP, ANNOVAR, vcfanno and
  AnnotationDbi." - Source: https://registry.hub.docker.com/r/bioinstaller/annovarr
  - Run interactive job:
  ```
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(bioinstaller/annovarr)' R
  ```
</details>

<details>
  <summary>BamTools</summary>

  - Registry Location: [https://bioconda.github.io/recipes/bamtools/README.html](https://bioconda.github.io/recipes/bamtools/README.html)
  - "C++ API & command-line toolkit for working with BAM data" - Source: [https://bioconda.github.io/recipes/bamtools/README.html](https://bioconda.github.io/recipes/bamtools/README.html)
  - Run interactive job:
  ```
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bamtools:2.5.1--he860b03_5)' /bin/bash
  ```
</details>

<details>
  <summary>BCFtools</summary>

  - Registry Location: [https://bioconda.github.io/recipes/bcftools/README.html](https://bioconda.github.io/recipes/bcftools/README.html)
  - "BCFtools is a set of utilities that manipulate variant calls in the Variant Call Format (VCF) and its binary counterpart BCF.
  All commands work transparently with both VCFs and BCFs, both uncompressed and BGZF-compressed. Most commands accept VCF,
  bgzipped VCF and BCF with filetype detected automatically even when streaming from a pipe. Indexed VCF and BCF will work in
  all situations. Un-indexed VCF and BCF and streams will work in most, but not all situations." - Source: [https://bioconda.github.io/recipes/bcftools/README.html](https://bioconda.github.io/recipes/bcftools/README.html)
  - Run interactive job:
  ```
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bcftools:1.10.2--hd2cd319_0)' /bin/bash
  ```
</details>

<details>
  <summary>bedtools</summary>

  - Registry Location: [https://bioconda.github.io/recipes/bedtools/README.html](https://bioconda.github.io/recipes/bedtools/README.html)
  - "...fast, flexible toolset for genome arithmetic." - Source: [https://bedtools.readthedocs.io/en/latest/](https://bedtools.readthedocs.io/en/latest/)
  - Run interactive job:
  ```
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bedtools:2.29.2--hc088bd4_0)' /bin/bash
  ```
</details>

<details>
  <summary>BLAST</summary>

  - Registry Location: [https://bioconda.github.io/recipes/blast/README.html](https://bioconda.github.io/recipes/blast/README.html)
  - "Basic Local Alignment Search Tool (BLAST) is a sequence similarity search program." - Source: [https://www.ncbi.nlm.nih.gov/pubmed/18440982](https://www.ncbi.nlm.nih.gov/pubmed/18440982)
  - Run interactive job:
  ```
  > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/blast:2.2.31--pl526h3066fca_3)' /bin/bash
  ```
</details>
