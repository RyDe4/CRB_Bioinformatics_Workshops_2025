## Set up your Workspace and Obtain a GTF File

1. Create a new directory called "CRB_workshops" using the `mkdir` command. You can use the man command followed by the program you want to use to open the manual that program/command. ex: `man mkdir`.
2. We can move up and down the manual page using the arrow keys, and exit by pressing q.
3. Change your working directory to the "CRB_workshops" directory with the `cd` command. Now, if you use the `pwd` command, you should see that your current working directory is the "CRB_workshops" directory.
4. Withing the "CRB_workshops" directory, create another directory called "annotation_files", and change into this directory.
5. Now, we will obtain a GTF file from ensembl. GTF files are typically used to store information about the attributes of genes and their components, as well as their positions within the genome. The GTF format is described here: http://useast.ensembl.org/info/website/upload/gff.html.
6. You can download the ensembl v113 human GTF file using `wget https://ftp.ensembl.org/pub/release-113/gtf/homo_sapiens/Homo_sapiens.GRCh38.113.chr.gtf.gz`.
7. Use the ls command to list files in your current working directory.
8. The ".gz" extension means the file is compressed in gzip format, so it can't be viewed without uncompressing the file. We can do this with the `gunzip` command.

## View the GTF file and Calculate Basic Statistics about the File

1. To view the file, there are a few different options. The `cat` command can be used to print the whole file to the terminal, but for large files such as this GTF this isn't as useful. To view the first lines of the file we can use the head, and the `tail` command can be used to view the last few lines. We can also use the less command to open a scrollable view of the file.
2. We can use the `wc` command to get information about the the number of words in the file, as well as the number of characters and the number of lines. Use `wc` with the `-l` option to count the number of lines in the GTF file.
3. We can search for words or patterns in the file using the `grep` command. Lets search for the word "snoRNA". We should see every line containing the word "snoRNA" printed to the terminal, with "snoRNA" highlighted in red.
4. We can pass the output from one command to another using the `|` operator. In this way we can count the number of lines containing the word "snoRNA", by using `grep snoRNA Homo_sapiens.GRCh38.113.chr.gtf | wc -l`. Here, the file input for the `wc -l` command is the output of the grep command. Note that the output of this command is not the total number of snoRNAs in the file, since the is a "transcript", "gene", and "exon" entry for each snoRNA in the file.
5. To redirect the output of a command to a file, we can use the `>` operator. If we were to run `grep snoRNA Homo_sapiens.GRCh38.113.chr.gtf | wc -l > Homo_sapiens_snoRNA.GRCh38.113.chr.gtf`, we would obtain a file called Homo_sapiens_snoRNA.GRCh38.113.chr.gtf containing all of the lines of the original GTF file which contain "snoRNA".
6. Note that the `>` operator will overwrite any pre-existing files with the same name. The `>>` operator will append to existing files.
7. If we want to get basic information about the file we just created as well as other files in our current directory, we can us the `ls -l` command.
8. If we want to get only the values of column 3 (the feature type column), we can use the `cut` command.

## Get the Number of Protein Coding Genes in the GTF File

1. Since the GTF file has multiple different types of entries for each gene/transcript, we first want to get only "gene" type entries. We can use the `awk` command to get the only lines which are "gene" type features. The command `awk '$3=="gene"' Homo_sapiens.GRCh38.113.chr.gtf`. Will get us only lines where the 3rd column is equal to "gene".
2. We will then pass the output of the awk command to grep to search for protein coding genes. Hint: you can grep for 'gene_biotype "protein_coding"'.
3. We can then use the `|` operator to pass the output of one command to another for a second time to count the number of lines which are for features of type "gene" and contain the phrase 'gene_biotype "protein_coding"'.
