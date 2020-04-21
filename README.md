################## Pfcsp_diversity_scripts ##################

######################## amino_haplotype_count_aadiff #################
This script was used to determine the frequency of amino acid haplotypes in each parasite population.
Usage: ./amino_haplotype_count --help

Options:
  -h, --help   show this help message and exit
  -i INP       Input file (default is stdin)
  -o OUT       Results output file name (default is stdout)
  -s START     Position[inclusive] to start reading amino acids (default in 1)
  -e END       Position[inclusive] to stop reading amino acids (default is
               till the end)
  -w WINDOW    Window size for each haplotype (default is sequence lenght)
  --step=STEP  Step size to move for the beginning for each haplotype (default
               is window size)


######## gt_modelling script #######
This was used to model biallelic genotypes in the Cape Coast parasite population dataset. 
This was based on the approach by the MalariaGEN Pf3k Project, 2016 where genotypes were modeled using the read
depth and allelic depth (Amato et al., 2016) . Briefly, for read depth of two alleles at a SNP position in
a sample, at positions with read depth &lt;5, the genotype was undetermined. At all other positions, with
read depth &gt;= 5, the sample was determined to be heterozygous if the allelic depth of both alleles were
greater or equal to 2. All other samples were homozygous for the allele seen in the majority of reads.
They were either genotyped as the homozygote reference allele or homozygote alternative allele.


########## vcf_to_amino_acids ###########
This script was used to translate DNA sequences to amino acid sequences
Usage: ./vcf_to_amino_acids --help

Options:
  -h, --help  show this help message and exit
  -v VCF      Vcf[.gz] Input file (default is stdin)
  -o OUT      Output file name (default is stdout)
  -r REF      Reference sequence file name in fasta format (required)
  -s START    Gene start position (required)
  -e END      Gene end position (required)
  --rev=REV   Whether the genotypes are reverse[yes] or forward[no] (default
              is no)
  --alt=ALT   Include amino acids translated from altenate genotypes
              [yes|no](default is no)



################ vcf_to_fasta ##################
This script was used to re-construct fasta squences from retained variants from vcf 
Usage: ./vcf_to_fasta --help

Options:
  -h, --help  show this help message and exit
  -v VCF      Vcf[.gz] Input file (default is stdin)
  -o OUT      Output file name (default is stdout)
  -r REF      Reference sequence file name in fasta format (required)
  -s START    Start locus in reference file (default is 1)
  -e END      End locus in reference file (default is END)
  --rev=REV   Whether the genotypes are reverse[yes] or forward[no] (default
              is no)
  --alt=ALT   Include altenate genotypes [yes|no](default is no)


