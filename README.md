#  sbx_rgi

This is an extension to the [Sunbeam pipeline](https://github.com/sunbeam-labs/sunbeam) that runs [RGI](https://card.mcmaster.ca/analyze/rgi) (Resistance Gene Identifier) to identify antibiotic resistance genes. Check out [Jia et al 2017](http://www.ncbi.nlm.nih.gov/pubmed/27789705) to learn more.

## Installing sbx_rgi

Clone the extension directory into the sunbeam/extensions/ folder:

    git clone https://github.com/louiejtaylor/sbx_rgi/ sunbeam/extensions/sbx_template

Install the requirements through Conda:

    conda install --file sunbeam/extensions/sbx_rgi/requirements.txt

Add the new options to your existing configuration file: 

    cat sunbeam/extensions/sbx_rgi/config.yml >> sunbeam_config.yml

## Running

To run sbx_rgi, simply run Sunbeam as usual with your extension's target rule specified:

    sunbeam run --configfile=sunbeam_config.yml all_rgi

## Contents

 - `requirements.txt` specifies the extension's dependencies
 - `config.yml` contains configuration options that can be specified by the user when running sbx_rgi
 - `sbx_rgi.rules` contains the rules (logic/commands run) of the extension

