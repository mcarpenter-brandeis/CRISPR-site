# CRISPR

#Author: Meredith Carpenter

#Goals: Overall goal is to identify crispr sites in a subset of animal sequences and pull out relevant information about the genes and exomes
#Input Files: clinical_data.txt, motifs_list.txt, *.fasta
#Output Files: exomes (directory), exomename_topmotifs.fasta, exomename_precrispr.fasta, exomename_postcrispr.fasta, exomeReport.txt

#Program details

#copyExomes: reads clinical data file (clinical_data.txt) to id samples with diam 20-30mm and sequenced genomes
#copyExomes: then copies the identified exome fasta files (*.fasta) using sample code names to new directory called exomes

#createCrisprReady: identifues the 3 highest occuring motids in each exome inside the exomes folder
#createCrisprReady: outputs the headers and corresponding sequences to a new file called exomename_topmotifs.fasta
#createCrisprReady: Renames the headers of the exomename_topmotifs.fasta files to include the motif sequences and their count

#identifyCrisprSite: For each gene inside the exomename_topmotifs.fasta files, identifies a suitable CRISPR site
#identifyCrisprSite: Find sequences that contain “NGG”, where “N” can be any base, that has at least 20 basepairs upstream
#identifyCrisprSite: Outputs suitable candidates (headers and sequences) to a new file called exomename_precrispr.fasta

#editGenome.sh: Inserts the letter A right before the NGG site, and outputs to a new file called exomename_postcrispr.fasta

#exomeReport.py: Single report to summarize the findings. Text file (exomeReport.txt) lists: name of the discoverer of org., diameter, code name and environment it came from
#exomeReport.py: Also includes how many genes the organism has in common with all the other organisms and which genes are unique to that organism (in the same cohort)
#exomeReport.py: (summarizing motif-containing exomes with just the CRISPR-ready genes, using the exomenames_precrispr.fasta)

#To execute code:
#bash copyExomes.sh
#bash createCrisprReady.sh
#bash identifyCrisprSite.sh
#bash editGenome.sh
#python3 exomeReport.py ##note: please run as python3 for program continuity execution
