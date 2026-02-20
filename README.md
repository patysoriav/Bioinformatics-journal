# Bioinformatics-journal
Diary about my work at the terminal and in data analysis (bioinformatics)

# Download RNAs Laccaria bicolor 02/19/2026
The objective is download all the Sequence Read Archive (SRA) from NCBI to Laccaria bicolor, then use R to separate only RNA-seq and run the scrip getSRA-geneeric.slurm 

**Note:** I can't download the SRA from NCBI because I was getting an error message. I download the RNA-seq using the termianal in my computer, but I need download 
the SRA from NCBI directly and compare the results because I'm not sure if what I did downloaded them all.

1. Download only the RNA-seq in the terminal directly
   
`esearch -db sra -query "\"Laccaria bicolor\" AND RNA-Seq[Strategy]" | \
efetch -db sra -format runinfo > Laccaria_bicolor_RNAseq.csv`

2. Verify that it downloaded correctly (seeing the first lines)

`head -n 5 Laccaria_bicolor_RNAseq.csv`

3. Move the file with RNA-seq to the pps/Lbicolor folder

`scp /Users/pattysoria/Laccaria_bicolor_RNAseq.csv pps5656@submit.hpc.psu.edu:/storage/home/pps5656/Users/pps/Lbicolor`

4. Edit and Run the script getSRA-generic.slurm

First, I edited the file with nano to change the user (ria5282 to pps5656) and the name of the file to read to Laccaria_bicolor_RNAseq.csv 

Edit `nano getSRA-generic.slurm`

Run scrip `sbatch getSRA-generic.slurm`

**Job ID:** 48632555



