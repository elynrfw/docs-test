.. _`vetted-applications`:

RIS-Vetted Application Containers
=================================

This page contains basic information and user-friendly guides to running RIS-vetted
application containers on compute. This is `not` an inclusive list of usable applications, by
any means, and is intended solely as a starting point for new users.

This page does not include application containers where the user does not want,
or is forbidden, to put code into a public registry.

.. warning ::

    The application containers listed on this page have been vetted to start a
    shell in an interactive job at the time of testing and were confirmed
    working at the time they were tested. The level of security with
    non-RIS-hosted images is not guaranteed and has not been tested.

    As such, we recommend to use RIS-hosted Docker images when possible. Please
    visit this :ref:`page <supported-applications>` for a list of RIS-hosted
    Docker images.

.. attention ::

    To successfully run `bsub` commands on this page, you must already be logged into the Compute Service:

    ``> ssh ${compute_username}@compute1-client-1.ris.wustl.edu``

    If you are not connected to a a Medical School network (WUSM-secure, MSVPN),
    or the Danforth VPN, you will need to perform port forwarding before
    accessing a GUI (i.e. accessing a Jupyter notebook or RStudio session).
    Documentation to forward ports is found `here`

Applications, Packages and Environment Images
---------------------------------------------

.. collapse:: .NET Core

  - Registry Location: https://hub.docker.com/_/microsoft-dotnet-core-sdk/
  - ".NET Core is an open-source, general-purpose development platform maintained by Microsoft and the .NET community on GitHub. It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications."
        - Source: https://docs.microsoft.com/en-us/dotnet/core/
  - Run interactive job:
  .. code::

      > bsub -G ${group_name} -Is -q general-interactive -a 'docker(mcr.microsoft.com/dotnet/core/sdk)' /bin/bash

.. collapse:: Anaconda

  - Registry Location:
      - Using Python 3.5: https://hub.docker.com/r/continuumio/anaconda3
      - Using Python 2.7: https://hub.docker.com/r/continuumio/anaconda
  - "Anaconda is the leading open data science platform powered by Python. The open source version of Anaconda is a high performance distribution and includes over 100 of the most popular Python packages for data science. Additionally, it provides access to over 720 Python and R packages that can easily be installed using the conda dependency and environment manager, which is included in Anaconda." 
      - Source: https://hub.docker.com/r/continuumio/anaconda3
  - Run interactive job:
    .. code::

        # Using Python 3.5:
        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(continuumio/anaconda3)' /bin/bash

        # Using Python 2.7:
        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(continuumio/anaconda)' /bin/bash

.. collapse:: AnnovarR

  - Registry Location: https://registry.hub.docker.com/r/bioinstaller/annovarr
  - "The annovarR package provides R functions as well as database resources which offer an integrated framework to annotate genetic variants from genome and transcriptome data. The wrapper functions of annovarR unified the interface of many published annotation tools, such as VEP, ANNOVAR, vcfanno and AnnotationDbi." 
      - Source: https://registry.hub.docker.com/r/bioinstaller/annovarr
  - Run interactive job:
    .. code::

        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(bioinstaller/annovarr)' R

.. collapse:: BamTools

  - Registry Location: https://bioconda.github.io/recipes/bamtools/README.html
  - "C++ API & command-line toolkit for working with BAM data" 
      - Source: https://bioconda.github.io/recipes/bamtools/README.html
  - Run interactive job:
    .. code ::

        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bamtools:2.5.1--he860b03_5)' /bin/bash

.. collapse:: BCFtools

  - Registry Location: https://bioconda.github.io/recipes/bcftools/README.html
  - "BCFtools is a set of utilities that manipulate variant calls in the Variant Call Format (VCF) and its binary counterpart BCF. All commands work transparently with both VCFs and BCFs, both uncompressed and BGZF-compressed. Most commands accept VCF, bgzipped VCF and BCF with filetype detected automatically even when streaming from a pipe. Indexed VCF and BCF will work in all situations. Un-indexed VCF and BCF and streams will work in most, but not all situations." 
      - Source: https://bioconda.github.io/recipes/bcftools/README.html
  - Run interactive job:
    .. code::

        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bcftools:1.10.2--hd2cd319_0)' /bin/bash

.. collapse:: bedtools

  - Registry Location: https://bioconda.github.io/recipes/bedtools/README.html
  - "...fast, flexible toolset for genome arithmetic." 
      - Source: https://bedtools.readthedocs.io/en/latest/
  - Run interactive job:
    .. code::

        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bedtools:2.29.2--hc088bd4_0)' /bin/bash

.. collapse:: BLAST

  - Registry Location: https://bioconda.github.io/recipes/blast/README.html
  - "Basic Local Alignment Search Tool (BLAST) is a sequence similarity search program." 
      - Source: https://www.ncbi.nlm.nih.gov/pubmed/18440982
  - Run interactive job:
    .. code::

        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/blast:2.2.31--pl526h3066fca_3)' /bin/bash

.. collapse:: Bowtie

  - Registry Location: https://bioconda.github.io/recipes/bowtie/README.html
  - "Bowtie is anultrafast, memory-efficient short read aligner. It aligns short DNA sequences (reads) to the human genome at a rate of over 25 million 35-bp reads per hour. Bowtie indexes the genome with a Burrows-Wheeler index to keep its memory footprint small: typically about 2.2 GB for the human genome (2.9 GB for paired-end)." 
      - Source: http://bowtie-bio.sourceforge.net/index.shtml
  - Run Interactive job:
    .. code::

        > bsub -G ${group_name} -Is -q general-interactive -a 'docker(quay.io/biocontainers/bowtie:1.2.3--py37hc9558a2_0)' /bin/bash
