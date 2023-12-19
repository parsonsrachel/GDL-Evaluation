# GDL-Evaluation

# Scripts for running methods

- Astral-Pro
  ```
  java -jar -D'java.library.path=lib' astral.1.1.6.jar -i <input file> &> <output file>
  ```
- Astral-Pro 2
  
  ```
  ./bin/astral-pro -o <output file> <input file> &> <log file>
  ```
- DISCO-Astral
  
  ```
  python3 disco.py -i <input file> -o <output file>
  java -jar astral.5.7.8.jar -i <input file> &> <output file>
  ```
- DISCO-ASTRID
  
  ```
  python3 disco.py -i <input file> -o <output file>
  ./ASTRID -i <input file> -o <output 1> -u
  ./ASTRID -i <output 1> -o <output 2>
  ```
- DupLoss
  
  ```
  ./Losses.linux -i <input file> &> <output file>
  ```
- DupLoss v2
  
  ```
  ./DupLoss_v2.linux -i <input file> &> <output file>
  ```
- FastMulRFS
  
  ```
  python3 python-tools/preprocess_multrees_v3.py -i <input file> -o <family file> --verbose
  ./external/FastRFS/build/FastRFS -i <family file> -o <output file> &> <log file>
  ```
- MulRF
  
  ```
  ./MulRFSupertreeLin -i <input tree> &> <output tree>
  ```
- SpeciesRax
  
  ```
  python3 scripts/build_families_file.py NONE <input tree> <mapping> NONE <family file>
  ./build/bin/generax \
  --families <family file> \
  --strategy SKIP \
  --si-strategy HYBRID \
  --species-tree MiniNJ \
  --rec-model UndatedDTL \
  --per-family-rates \
  --prune-species-tree \
  --si-estimate-bl \
  --si-quartet-support \
  --prefix <output file>
  ```

  # s100 runs
  Varried three lengths of the sequences to simulate different error rates
  Created the gene trees using RaxML command:
  ```
  ```
  These tree have the wrong names (there are no duplicate labels), so we have to go through the trees, fix the names and add them all to one file.
  ```
  directory_1000_seqlen = '/home/rap16104/Dependencies/standard-RAxML/ILS+Error/'
  directory_500_seqlen = '/home/rap16104/Dependencies/standard-RAxML/ILS+Error/500seqlen/'
  directory_2500_seqlen = '/home/rap16104/DL+ILS/estimated-gene-trees-psize-'
  #/home/rap16104/DL+ILS/estimated-gene-trees-psize-10000000/ntaxa-100.dlrate-0.0.psize-10000000/01/g_trees-raxml-sqlen-250.trees

  
  psize=['psize-10000000/', 'psize-50000000/']
  drate=['dlrate-0.0000000001-psize-50000000/', 'dlrate-0.0000000005-psize-50000000/', 'dlrate-0.0000000002-psize-50000000/', 'dlrate-0.0-psize-50000000/']
  num = ['01/','02/','03/','04/','05/','06/','07/','08/','09/','10/']
  for p in psize:
    for d in drate:
        for n in num:
            
            fr = open("DL+ILS/estimated-gene-trees-"+p+d+p+n+fname, "r")
            fw = open("DL+ILS/estimated-gene-trees-"+p+d+p+n+"multi100-500genetrees.newick", "a")
            lines = fr.readlines()
            for line in lines:
                new = re.sub("_([0-9]+)_([0-9]+):",":",line)
                fw.write(new)

