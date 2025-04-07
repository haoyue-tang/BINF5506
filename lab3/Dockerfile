FROM continuumio/miniconda3
 
WORKDIR /code

COPY . /code

RUN apt update
 
RUN apt upgrade -y
 
RUN apt install tree -y
 
RUN apt install wget -y

RUN conda install -c bioconda entrez-direct sra-tools fastqc bwa gatk4 snpEff -y

RUN conda install -c conda-forge -c bioconda samtools -y

RUN apt-get update && apt-get install -y sra-toolkit

RUN apt-get update && apt-get install -y ca-certificates && update-ca-certificates

RUN conda install -c conda-forge -c bioconda snakemake -y

CMD ["snakemake", "--cores", "1"]