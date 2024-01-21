# Reports CodeSlicing 


| Tool         | VST3 | ST3 | MT3 | T4  | Klone      | Report                                               | Precision_Report |
| ------------ | ---- | --- | --- | --- | ---------- | ---------------------------------------------------- | ---------------- |
| V1_EU_75     | 99%  | 89% | 73% | 31% | 56.691.834 | [V1_EU_75_report](./reports/V1_EU_75_report)         | [V1_EU_75_precision_report](./reports_precision/V1_EU_75_precision_report.txt)  |
| V1_LSH_BC_75 | 99%  | 95% | 70% | 45% | 82.870.134 | [V1_LSH_BC_75_report](./reports/V1_LSH_BC_75_report) | [V1_LSH_BC_75_precision_report](./reports_precision/V1_LSH_BC_75_precision_report.txt) |
| V2_EU_75     | 99%  | 97% | 82% | 42% | 84.294.814 | [V1_EU_75_report](./reports/V1_EU_75_report)         | [V2_EU_75_precision_report](./reports_precision/V2_EU_75_precision_report.txt) |
| V2_LSH_BC_75 | 99%  | 89% | 63% | 35% | 77.201.336 | [V2_LSH_BC_75_report](./reports/V2_LSH_BC_75_report) | [V2_LSH_BC_75_precision_report](./reports_precision/V2_LSH_BC_75_precision_report.txt) |


## Infos 

| Tool         | Version | Vergleichsfunktion | Threshold | mit BucketCleanup? |
| ------------ | ------- | ------------------ | --------- | ------------------ |
| V1_EU_75     | 1       | Euklid             | 75        | -                  |
| V1_LSH_BC_75 | 1       | LSH + Hamming      | 75        | JA                 |
| V1_HAM_75    | 1       | Hamming            | 75        | -                  |
| V2_EU_75     | 2       | Euklid             | 75        | -                  |
| V2_LSH_BC_75 | 2       | LSH + Hamming      | 75        | JA                 |
| V2_HAM_75    | 2       | Hamming            | 75        | -                  |


| Version | Aufbau Vektor               | Beispiel         |
| ------- | --------------------------- | ---------------- |
| 1       | < Def, Use, Dvars, cFuncs > | <1, 3, 1, 0>     |
| 2       | < SC, SCvg, SI, SS >        | <2, 0.7, 2, 0.9> |


