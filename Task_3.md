## Searching and Loading Modules on OSC

OSC has many popular bioinformatics tools pre-installed which are accessible through their module system.
-To see all available software use the command `module avail`.  
-To search for specific software packages, you can use the `module spider <software name>`. The `module spider` command can also be used to find out more specific steps that may be needed to load certain software tools.  
-To load a software tool, you can use the `module load <software name/version>` to load a specific version of a software tool.

## The fastq File Format

Fastq files are used to store sequencing reads produced by next generation sequencing technologies. They contain 4 lines for each read:  
-The read name, and possibly other information describing the read.  
-The sequence of the read itself. This line contains characters representing the DNA nucleotides of the read, or N if the sequencer could not confidently identify a base.  
-A line with a + to separate the read from its quality string.  
-The quality string for the read. This string encodes the confidence that the sequencer has that it has accurately identified the base at each position in a read. Bases below a certain quality threshold are assigned an N.

## Running fastqc

fastqc is a popular tool for performing quality control of sequencing reads. It can decode the quality strings for reads into more human readable form and summarize them across many reads so that we can get a better idea of the accuracy of the base calls in our sequencing run. It can also identify contaminating sequences found in the fastq file, as well generate other more situational QC plots.  

To run fastqc:  
-Load fastqc using the command `module load fastqc/0.12.1`, or a different version depending on what cluster you are on. It is important to take note of the version of software you are using since journals require you to put this information in the methods section when you publish.  
-Create a directory in /fs/ess/PAS2980/ with the same name as your username. This is where you will perform your analyses for this workshop. Within your directory, create a sub-directory called something like "raw_fastqc".  
-Run fastqc on the file `/fs/ess/PAS2980/GSE231460_data/raw_fastq/patient_P1_day0_R1.fastq`, and send the output to the directory you created for your fastqc output. You can do this with a command similar to `fastqc /fs/ess/PAS2980/GSE231460_data/raw_fastq/patient_P1_day0_R1.fastq -o /fs/ess/PAS2980/<your username>/raw_fastq`. The -o option specifies the directory where the output from fastqc will go.  
-Download the html file that should now be found in `/fs/ess/PAS2980/<your username>/raw_fastq` using the Files GUI in OnDemand, and open it in your browser.  

## Interpreting fastqc results  

For RNA-seq, the most important plots are usually the "Per base sequence quality", "Overrepresented sequences", and "Adapter Content" plots. You don't need to worry about which plots have a checkmark or X, since fastqc was originally designed for whole genome sequencing data and pass/fail thresholds were chosen based on this type of analysis.  

Sequence quality and phred scores:  
-
