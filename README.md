# CB2110_Lab1


## 1. Set up 
1. [Docker](https://www.docker.com/)
2. [Nextflow](https://www.nextflow.io/) 

## 2. Links 
- [nextflow](https://www.nextflow.io/)
- [quantms](https://nf-co.re/quantms/1.3.0/) 
- [msstats](https://bioconductor.org/packages/release/bioc/html/MSstats.html) 
- [PRIDE](https://www.ebi.ac.uk/pride/archive/) 

## 3. Running 
1. Check you installation and prepare your Files. 
    - Docker: 
    ```
    docker run hello-world
    ```
    - Nextflow: 
    ```
    nextflow run hello
    ``` 
    Hint: You may need `sudo` to run the command.
2. Prepare your files.
    - Download the proteome from [Uniprot](https://www.uniprot.org/). You need to download the fasta file of the proteome in a canonical version without the isoforms.
    - Download the raw data from [PRIDE](https://www.ebi.ac.uk/pride/archive/). In this exercise we will use the raw files from the PRIDE project PXD020109. 
    - Prepare the SDRF file.
    - All of the file above should be in the same directory.

3. Run the pipeline 
    - Change your directory to the directory that contains the files.

    ```
    cd </path/to/your/directory>
    ```
    
    - Take a look at SDRF files and raw files. Are they correlated with file numbers abd file names?
    - Run the pipeline. Adjust your file names and paths accordingly within <>. 
    
    ```
    nextflow run bigbio/quantms -r dev --input '<sdrf>.tsv' --outdir 'results' --database '<Organusm Proteome>.fasta' -profile docker --root_folder <root directory of your folder> --local_input_type raw  --add_decoys --max_memory 8GB
    ```
    One can adjust the memory usage by changing the `--max_memory` parameter. It's recommended to use as much memory as possible but not all of it.
    - The pipeline will run and generate the results in the `results` folder and the intermediate file in `work`. It will take a while to run around an hour. If it crashes, you can resume the pipeline by running the same command and add `-resume`.

## 4. Publications 

- [quantms](https://www.biorxiv.org/content/10.1101/2021.08.23.457366v1)
- [msstats](https://pubmed.ncbi.nlm.nih.gov/25049305/)
- [lesSDRF](https://pubmed.ncbi.nlm.nih.gov/25049305/)

## 5. Info 
- Course: CB2110 Applied Proteomics, KTH 
- Author: Thanadol Sutantiwanichkul (thanado@kth.se)
- Latest update: 120824
- Version: 0.1.0 