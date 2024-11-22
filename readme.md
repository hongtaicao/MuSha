# MuSha
* MuSha: Subgraph Matching by Multilevel Sharing

## Quick Start
* Binary files are for ``Little Endian x86_64 Ubuntu 20.04.5 LTS`` machines.
* Google Drive [https://drive.google.com/drive/folders/1elMOO1_BYWd_u4k2EMRwUXfWXtbWfnOI](https://drive.google.com/drive/folders/1elMOO1_BYWd_u4k2EMRwUXfWXtbWfnOI).
* Download and unzip the dataset ``dataset.zip`` (only in Google Drive).
* Download the binary ``release.exe``.
* Download the test script ``bin/MuSha.txt``.
* Organize files as the following
```
root-directory
    + bin/MuSha.txt
    + dataset/
    |   + unlabeled-query/
    |   + ...
    + release.exe
    ...
```
* command
```bash
bash bin/MuSha.txt
```

## Example
* command
```bash
./release.exe -algorithm TopDown -execute dynamic -graph-storage SortTrie -order-generator NonAutomorphism -symmetry-breaking SymBreak2007 -is-labeled 1 -data-file dataset/labeled-patent-subcategory-single-directed.txt -query-file dataset/labeled-patent-subcategory-single-directed-sample-query/6-22.txt
```
* output
```
DurationReadBinaryGraph(s)=2.723
DurationBuildOne(s)=0.002 DurationSymbreakOne(s)=0
AutomorphismCount=2 MatchVertex=0 3 2 1 5 4  SymbreakCount=2 SymbreakScore=6.39713e+11
DurationExecutionDynamic(s)=22.041 MatchCount=174467984
append result summary file=v0.1-log.csv
stop command line at 2024_11_12-23_13_16
```
* explanation
    - DurationBuildOne(s)=0.002 DurationSymbreakOne(s)=0
    - Therefore total optimization time cost = 0.002 + 0 = 0.002 seconds
    - Total execution time = 2.723 + 0.002 + 0 + 22.041 = 24.766 seconds
    - AutomorphismCount=2, MatchCount=174467984
    - MuSha explores symmetry breaking and therefore total count is 2*174467984


## Compile the Program
* require ``make`` and ``g++``
* download and unzip ``MuSha-master.zip``
* go to the directory of ``Makefile``
* compile ``make release``
* compile file is ``release.exe``


## Other Note
* Architecture ``lscpu``
* OS version ``cat /etc/os-release``
