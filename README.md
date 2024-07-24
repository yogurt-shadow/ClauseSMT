# Data and Binary files for "Improving NLSAT for Nonlinear Real Arithmetic Theory with Clause-Level Information"

Benchmark: QF_NRA of SMT-LIB (https://zenodo.org/records/11061097)

## Comparison with Existing SMT Solvers
| Solver | Path | Data | Usage | Sat | Unsat | Solved |
| --- | --- | --- | --- | --- | --- | --- |
| NLSAT | [NLSAT](solvers/NLSAT) | [NLSAT_result](data/NLSAT.csv) | ./NLSAT <*.smt2> | 5541 | 5191 | 10732|
| Z3 | [z3](solvers/z3) | [z3_result](data/z3.csv) | ./z3 <*.smt2> | 5569 | 5379 | 10948|
| CVC5 | [cvc5](solvers/cvc5) | [cvc5_result](data/cvc5.csv) | ./cvc5 <*.smt2> | 5475 | 5809 | 11284|
| Yices2 | [yices2](solvers/yices2) | [yices2_result](data/yices2.csv) | ./yices2 <*.smt2> | 5372 | 5612 | 10984|
| dReal (delta=0.001) | [dReal](solvers/dReal) | [dReal_result](data/dReal.csv) | ./dReal --precision 0.001 <*.smt2> | 4811 | 4294 | 9105|
| MathSAT | [mathsat](solvers/mathsat) | [mathsat_result](data/mathsat.csv) | ./mathsat <*.smt2> | 2772 | 4583 | 7355|
| clauseSMT (Ours) | [clauseSMT](solvers/clauseSMT) | [clauseSMT_result](data/clauseSMT.csv) | ./clauseSMT <*.smt2> | 5608 | 5397 | 11005 |

## Effect of Proposed Techniques
### Effect of Look-Ahead Mechanism
| Solver | Description | Path | Data | Usage | Sat | Unsat | Solved |
| --- | --- | --- | --- | --- | --- | --- | --- |
| NLSAT | Decide Lowest Degree Literal | [NLSAT](solvers/NLSAT) | [NLSAT_result](data/NLSAT.csv) | ./NLSAT <*.smt2> -st | 5541 | 5191 | 10732|
| random_decide | Decide Random Literal | [random_decide](solvers/random_decide) | [random_decide_result](data/random_decide.csv) | ./random_decide <*.smt2> -st | 5505 | 5147 | 10652|
| static-look-ahead | Feasible-set based Look-Ahead | [static-look-ahead](solvers/static-look-ahead) | [static-look-ahead_result](data/static-look-ahead.csv) | ./static-look-ahead <*.smt2> -st | 5555 | 5223 | 10778|

### Effect of Clause-Level Propagation based Branching Heuristic
| Solver | Description | Path | Data | Usage | Sat | Unsat | Solved |
| --- | --- | --- | --- | --- | --- | --- | --- |
| static-look-ahead | Static order based on degree | [static-look-ahead](solvers/static-look-ahead) | [static-look-ahead_result](data/static-look-ahead.csv) | ./static-look-ahead <*.smt2> -st | 5555 | 5223 | 10778|
| vsids-look-ahead | Dynamic order based on VSIDS | [vsids-look-ahead](solvers/vsids-look-ahead) | [vsids-look-ahead_result](data/vsids-look-ahead.csv) | ./vsids-look-ahead <*.smt2> -st | 5599 | 5321 | 10920|
| clauseSMT (Ours) | Dynamic order based on clause-level propagation | [clauseSMT](solvers/clauseSMT) | [clauseSMT_result](data/clauseSMT.csv) | ./clauseSMT <*.smt2> -st | 5608 | 5397 | 11005|