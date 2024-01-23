# Reports CodeSlicing 


| Tool         | VST3 | ST3 | MT3 | T4  | Klone      | Report                                               | Precision_Report |
| ------------ | ---- | --- | --- | --- | ---------- | ---------------------------------------------------- | ---------------- |
| V1_EU_75     | 99%  | 89% | 73% | 31% | 56.691.834 | [V1_EU_75_report](./reports/V1_EU_75_report)         | [V1_EU_75_precision_report](./reports_precision/V1_EU_75_precision_report.txt)  |
| V1_LSH_BC_75 | 99%  | 95% | 70% | 45% | 82.870.134 | [V1_LSH_BC_75_report](./reports/V1_LSH_BC_75_report) | [V1_LSH_BC_75_precision_report](./reports_precision/V1_LSH_BC_75_precision_report.txt) |
| V1_HAM_75    | 99%  | 97% | 83% | 34% | 51.336.536 | [V1_HAM_75_report](./reports/V1_HAM_75_report)       | [V1_HAM_75_precision_report](./reports_precision/V1_HAM_75_precision_report.txt)  |
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


### Version 1 

*  **Def** = Die Liste der Zeilen, in denen eine Variable definiert oder neu definiert wird.
*  **Use** = Die Liste der Zeilen, in denen eine Variable genutzt wird, beispielsweise für eine Berechnung, ohne dass sie dabei verändert wird.
*  **Dvars** = Die Liste der Variablen, welche Abhängigkeiten von der Variable aufweisen.  
*  **Cfuncs** = Die Liste der Funktionen/Methoden, in welcher die Variable als Parameter übergeben wird.


### Version 2

* **SC (Slice Count)** = Die Gesamtzahl aller Slices. Für eine Variable ist dies die Summe aller Slice-Profile, um den endgültigen Slice zu bilden. Im Falle eines Pfads oder einer Methode repräsentiert dies die Anzahl der Slices für alle in der Methode enthaltenen Variablen. 
* **SCvg (Slice Coverage)** = Die Größe des Slices im Verhältnis zur Modulgröße, welche in "Lines of Code" gemessen wird. Dabei wird die Anzahl aller Statements einer Variable ins Verhältnis zu den Lines of Code gesetzt. Daraus ergibt sich die Formel *SCvg = SZ/w*, wobei *SZ* für die Anzahl alles Statements und *w* für die Anzahl der Codezeilen steht.
* **SI (Slice Identifier)** = Die Anzahl der eindeutigen Bezeichner innerhalb eines Slices wird durch die Bildung der Vereinigung der DVars und CFuncs ermittelt.
* **SS (Slice Spatial)** = Der räumliche Abstand in LoC zwischen der ersten Definition und der letzten Verwendung der Slicing-Variablen. Dies wird durch *SS = (S_l - S_f)/w* berechnet, wobei *S_f* für die Zeile der ersten Definition, *S_l* für die Zeile der letzten Verwendung und *w* für die Anzahl der Codezeilen steht. 


