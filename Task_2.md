## Set up your Workspace and Obtain a GTF File

1. Create a new directory called "CRB_workshops" using the mkdir command. You can use the man command followed by the program you want to use to open the manual that program/command. ex: man mkdir.
2. We can move up and down the manual page using the arrow keys, and exit by pressing q.
3. Change your working directory to the "CRB_workshops" directory with the cd command. Now, if you use the pwd command, you should see that your current working directory is the "CRB_workshops" directory.
4. Withing the "CRB_workshops" directory, create another directory called "annotation_files", and change into this directory.
5. Now, we will obtain a GTF file from ensembl. GTF files are typically used to store information about the attributes of genes and their components, as well as their positions within the genome. The GTF format is described here: http://useast.ensembl.org/info/website/upload/gff.html.
6. You can download the ensembl v113 human GTF file using wget https://ftp.ensembl.org/pub/release-113/gtf/homo_sapiens/Homo_sapiens.GRCh38.113.chr.gtf.gz.
7. Use the ls command to list files in your current working directory.
8. The ".gz" extension means the file is compressed in gzip format, so it can't be viewed without uncompressing the file. We can do this with the gunzip command.
