# AAIC Workload

This repository contains workloads of GPU queues of AIST Artificial
Intelligence Cloud (AAIC).  As AAIC is dedicatedly used for AI research,
many job records in the workload are jobs to run training tasks of deep
learning applications.

The current workload contains jobs submitted from July 14th, 2017 to
December 31st, 2018.


## Workload Files

Workloads contained in this repository are formatted in CSV and distributed
by gzip compressed.

There are three kind of workload files in workloads directory.

- annual
  - Workloads that contain one year jobs are stored in this directory.
  - As recording workloads starts from July, the first month in the workload
    is July and the last month is June of next year.
- quarter
  - Workloads that contain jobs submitted in each quarter are stored in this
    directory.
- other
  - Other kinds of workloads, such as workloads used by us to publish their
    analysis results, are stored in this directory.
  - The workload named "aaicwl-hpc170.csv.gz" is used to present the analysis
    results in HPC170 workshop.


## Workload Format

All workload files are formatted in CSV and have the same format.
Each line in a workload file is a record of a job.
Each job record has the following 13 attributes.

| Attribute | Meanings |
|---------:|:---------|
| Job ID | A unique sequential number assigned to each job. The number is unique only in a workload file. |
| User | ID of a user who submit the job. User ID is unique only in a workload file. |
| Group | ID of a group where a user who submit the job belongs. Group ID is unique only in a workload file. |
| Queue | A queue where the job submitted. Queue name is an integer number. |
| Nodes | Number of used nodes by the job. |
| GPUs | Number of used GPUs within a node by the job. |
| Requested Walltime | Walltime requested by job submitter. |
| Termcode | Job termination code: success(0), fail(1), walltime exceeded(2), canceled by user(3) or canceled by system(4). |
| Submit Timestamp | Time when job is submitted in UNIX timestamp. |
| Start Timestamp | Time when job starts running in UNIX timestamp. |
| Finish Timestamp | Time when job ends running in UNIX timestamp. |
| Wait Time | Duration between time job submitted and time job starts in seconds. |
| Walltime | Actual walltime of the job in seconds. |


## Usage and Acknowledgment

If you use this workload in your work, please add the following or a similar
acknowledgement.

```
The AAIC workload log was graciously provided by AIRC, AIST.
```

If you cite this workload, please add the following or a similar reference.

```
Shinichiro Takizawa, Hirotaka Ogawa and Ryousei Takano, "AAIC Workload", https://github.com/aistairc/aaic-workload.
```


## Publications

Papers and reports that use this workload.

- 滝澤 真一朗, 小川 宏高, 高野 了成, 大規模GPUクラスタにおける深層学習ワークロードの
  傾向把握, 第170回ハイパフォーマンスコンピューティング研究会, July, 2019.


## Links

- [About AAIC](https://www.airc.aist.go.jp/info_details/computer-resources.html)
- [AIRC, AIST](https://www.airc.aist.go.jp/en/)
