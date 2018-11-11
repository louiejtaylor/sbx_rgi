#  sbx_rgi

This is an extension to the [Sunbeam pipeline](https://github.com/sunbeam-labs/sunbeam) that runs [RGI](https://card.mcmaster.ca/analyze/rgi) (Resistance Gene Identifier) to identify antibiotic resistance genes. Check out [Jia et al 2017](http://www.ncbi.nlm.nih.gov/pubmed/27789705) to learn more about RGI and CARD.

## Installing sbx_rgi

Clone the extension directory into the sunbeam/extensions/ folder:

    git clone https://github.com/louiejtaylor/sbx_rgi/ sunbeam/extensions/sbx_template

(Make sure you're in the correct Conda env, if not, run `source activate sunbeam`)

Install the requirements through Conda:

    conda install -c bioconda --file sunbeam/extensions/sbx_rgi/requirements.txt

Add the new options to your existing configuration file: 

    cat sunbeam/extensions/sbx_rgi/config.yml >> sunbeam_config.yml

## Databases

You'll need databases for RGI to run on. These are not installed automatically with RGI, you can grab them
here: https://card.mcmaster.ca/download. (Note that as of 2018/11/11 the links on the webpage lead to .tar.gz files, but the actual format seems to be .tar.bz2)

Once you've downloaded and extracted them, just add the path to the "card.json" file into the corresponding location in your config file:

    sbx_rgi:
      card_db_path: "[your_path]"

## Running

To run sbx_rgi, simply run Sunbeam as usual with your extension's target rule specified:

    sunbeam run --configfile=sunbeam_config.yml all_rgi

## Contents

 - `requirements.txt` specifies the extension's dependencies
 - `config.yml` contains configuration options that can be specified by the user when running sbx_rgi
 - `sbx_rgi.rules` contains the rules (logic/commands run) of the extension

