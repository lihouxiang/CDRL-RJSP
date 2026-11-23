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
| `SPT.zip` | Raw experimental results of SPT. |
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

## Field Glossary (Chinese–English)

The raw result workbooks use Chinese field names. Their English equivalents (terminology as in the paper) are:

| Chinese | English |
|---|---|
| 加权总成本 | weighted total cost |
| 时间成本(货币量纲) | processing cost (monetary units) |
| 时间成本加权项 | weighted processing-cost term |
| 最大完工时间 | makespan |
| 模式切换成本 | configuration switching cost |
| 切换成本加权项 | weighted switching-cost term |
| 模式切换次数 | number of configuration switches |
| 功耗成本 | energy cost |
| 功耗成本加权项 | weighted energy-cost term |
| 时间成本系数 (machine_time_cost) | processing-cost coefficient |
| 权重-time / switch / power | weights $\omega_{m}$ / $\omega_{sw}$ / $\omega_{pow}$ |
| 工序总数 / 机器数量 / 工件数量 | number of operations / machines / jobs |
| 求解完成时间 / 求解用时 | solution timestamp / solution time |
| 工序ID / 工件ID / 工序序号 | operation ID / job ID / operation index |
| 机器ID / 模式ID | machine ID / processing configuration ID |
| 开始时间 / 结束时间 / 加工时长 | start time / end time / processing duration |
| 调度顺序 | dispatching order |
| 总加工时间 / 总时间成本 / 总功耗成本 | total processing time / total processing cost / total energy cost |
| 案例 / 最优组 / 最优成本 | instance / best algorithm / best cost |

## Reference

Brandimarte, P. Routing and scheduling in a flexible job shop by tabu search. *Ann. Oper. Res.* **1993**, *41*, 157–183. https://doi.org/10.1007/BF02023073
