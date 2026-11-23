# CDRL-RJSP

Benchmark instances and raw experimental data for "Graph-based collaborative multi-agent deep reinforcement learning for reconfigurable job shop scheduling".

## Contents

| File | Description |
|---|---|
| `instance.zip` | Benchmark instances (JSON): 10 instances transformed from the Brandimarte benchmark (mk1–mk10) and 25 randomly generated instances (case_*), of which 20 form the test set used in the paper. |
| `CDRL.zip` | Raw experimental results of CDRL (proposed method). |
| `SAHG.zip` | Raw experimental results of SAHG. |
| `CADHG.zip` | Raw experimental results of CADHG. |
| `AHG.zip` | Raw experimental results of AHG. |
| `PPO.zip` | Raw experimental results of PPO. |
| `LPT.zip` | Raw experimental results of LPT. |
| `MOR.zip` | Raw experimental results of MOR. |
| `RPD.xlsx` | Relative percentage deviation (RPD) summary, corresponding to Table 4 and Figure 5 of the paper. |

Each `*_result.xlsx` records one algorithm's raw results on one instance: the objective values (weighted total cost and its components — time cost, configuration switching cost, power cost; makespan; number of configuration switches) and the operation-level schedule (machine assignment, processing configuration, start/end times).

## Instance Format

Each instance JSON contains:

- `jobs`: for each job, a list of operations; each operation is a list of `[machine_id, base_processing_time]` alternatives;
- `num_machines`: number of machines;
- `machine_modes`: for each machine, the available processing configurations with `cost`, `efficiency`, and `power_cost`.

## Naming Convention

- `case_S_6J_8M_0001` — randomly generated instance, small scale, 6 jobs × 8 machines, ID 0001 (S/M/L = small/medium/large). In the paper these appear as `caseS0001`, `caseM0043`, `caseL0113`, etc.
- `mk1`–`mk10` — instances transformed from the Brandimarte benchmark instances mk01–mk10 (Brandimarte, 1993).

## Correspondence to the Paper

- Table 3 — weighted total cost of the eight algorithms on the 30 test instances (from the `*_result.xlsx` files);
- Table 4 and Figure 5 — RPD statistics (`RPD.xlsx`);
- Table 5 and Figures 6–8 — case study on `caseL0113` (`case_L_20J_8M_0113`).

## Reference

Brandimarte, P. Routing and scheduling in a flexible job shop by tabu search. *Ann. Oper. Res.* **1993**, *41*, 157–183. https://doi.org/10.1007/BF02023073
