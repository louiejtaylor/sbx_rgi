#  sbx_rgi

This is an extension to the [Sunbeam pipeline](https://github.com/sunbeam-labs/sunbeam) that runs [RGI](https://card.mcmaster.ca/analyze/rgi) (Resistance Gene Identifier) to identify antibiotic resistance genes. Check out [Jia et al 2017](http://www.ncbi.nlm.nih.gov/pubmed/27789705) to learn more about RGI and CARD.

## Installing sbx_rgi

To install:

    sunbeam extend https://github.com/sunbeam-labs/sbx_coassembly/


Config options for `sbx_rgi` are automatically added on `sunbeam init`. If you're installing an extension in a project where you already have a config file, run the following to add the options for your newly added extension to your config (the `-i` flag means in-place config file modification; remove the `-i` flag to see the new config in stdout):

    sunbeam config update -i sunbeam_config.yml

As of December 2019, the latest CARD database version is automatically grabbed by the extension, so no need to worry about dbs!

See legacy install instructions below.

## Running

To run sbx_rgi, simply run Sunbeam as usual with the `all_rgi` target rule specified:

    sunbeam run --configfile=sunbeam_config.yml --use-conda all_rgi

The `--use-conda` flag is required to let Snakemake know that you want to use the conda environment(s) included with your extension.

## Contents

 - `requirements.txt` specifies the extension's dependencies
 - `config.yml` contains configuration options that can be specified by the user when running sbx_rgi
 - `sbx_rgi.rules` contains the rules (logic/commands run) of the extension

-----------

## Legacy install instructions for sunbeam <3.0

Clone the extension directory into the sunbeam/extensions/ folder:

    git clone https://github.com/louiejtaylor/sbx_rgi/ sunbeam/extensions/sbx_template

(Make sure you're in the correct Conda env, if not, run `source activate sunbeam`)

Add the new options to your existing configuration file: 

    cat sunbeam/extensions/sbx_rgi/config.yml >> sunbeam_config.yml

