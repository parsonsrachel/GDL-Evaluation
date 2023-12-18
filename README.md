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
