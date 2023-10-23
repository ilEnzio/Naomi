# Naomi
Automated Prompt evaluation experiment.

Originally inspired by the 2023 Def Con talk:
[LLMs at the Forefront: Pioneering the Future of Fuzz Testing in a Rapidly Changing World](https://forum.defcon.org/node/245769) 
by "X"
Assoicated Blog Post: https://infiniteforest.org/LLMs+to+Write+Fuzzers


The idea is to use something akin to the generic Algorithm I from The Art, Science, and Engineering of Fuzzing: 
A Survey(2019)* to create a LLM Prompt Evaluation tool.  

**Preprocess** 
- Model-less fuzz:
  - Takes: 
    - user provided fuzz configuration
  - Return:
    - set of configuration
- Model-based fuzz:
  - Takes:
    - Prompt Under Evaluation(PUE)
  - Return: 
      - act as Policy/Evaluation Oracle - return expected response given the input seed
      - an input seed based on the PUE
      - a set of configuration
  
    
**Schedule**
- takes the current set of fuzz configs and selects the config for the current fuzz iteration

**InputGen**
- Takes:
  - fuzz configuration
  - seed input

- Return:
  - minset of test cases

**InputEval**
- Takes:
  - config, test case, policy/eval oracle/expected result
- scores the output of PUE
- Return:
  - Output report
    - config
    - test case
    - eval oracle
    - output scores
    - 
