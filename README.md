# AAIC Workload

This repository contains workloads of GPU queues of AIST Artificial
Intelligence Cloud (AAIC).  As AAIC is dedicatedly used for AI research,
many job records in the workload are jobs to run training tasks of deep
learning applications.

The current workload contains jobs submitted from July 14th, 2017 to
December 31st, 2018.


## System Overview

![AAIC Architecture](https://raw.githubusercontent.com/aistairc/aaic-workload/master/aaic-arch.jpg)

AAIC consists of 50 compute nodes equipped with GPUs (GPU nodes) and 68 CPU
only compute nodes.
Workloads published on this page are obtained from a batch job scheduling
system that manages GPU nodes.
Although there are 50 GPU nodes, the scheduling system manages 32 to 40 nodes
depending on utilization.
Remaining GPU nodes are used for other purposes.

The table shows the resource quantity of a GPU node.

|    Attribute |   Value |
|         ---: |    ---: |
|  # CPU cores |      20 |
|       # GPUs |       8 |
|       Memory | 256 GiB |
| SSD Capacity |  480 GB |

Here are the basic scheduling policy.

- There are 32 to 40 GPU nodes managed by the scheduling system.
- There are 4 queues and they share the same resource pool.
- The scheduling policy is based on FCFS and backfill.
- The maximum number of nodes in a job is 32.
- A Multi node jobs has to use all 8 GPUs in each node.
- A job can use any number of GPUs (1 to 8) in a node when the job uses
  only one node.
- Multiple jobs that use only one node and only a few GPUs in a node can
  run on the same node at the same time to improve GPU utilization.
  For example, two jobs that use two GPUs and a job that uses 4 GPUs run on
  the same node.


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

| Order | Attribute | Meanings |
|:--:|---------:|:---------|
|  1 | Job ID | A unique sequential number assigned to each job. The number is unique only in a workload file. |
|  2 | User | ID of a user who submit the job. User ID is unique only in a workload file. |
|  3 | Group | ID of a group where a user who submit the job belongs. Group ID is unique only in a workload file. |
|  4 | Queue | A queue where the job submitted. Queue name is an integer number. |
|  5 | Nodes | Number of used nodes by the job. |
|  6 | GPUs |Number of used GPUs within a node by the job. |
|  7 | Requested Walltime | Walltime requested by job submitter. |
|  8 | Termcode | Job termination code: success(0), fail(1), walltime exceeded(2), canceled by user(3) or canceled by system(4). |
|  9 | Submit Timestamp | Time when job is submitted in UNIX timestamp. |
| 10 | Start Timestamp | Time when job starts running in UNIX timestamp. |
| 11 | Finish Timestamp | Time when job ends running in UNIX timestamp. |
| 12 | Wait Time | Duration between time job submitted and time job starts in seconds. |
| 13 | Walltime | Actual walltime of the job in seconds. |


## Usage and Acknowledgment

AAIC workload is copyrighted by AIST, National Institute of Advanced Industrial
Science and Technology (国立研究開発法人 産業技術総合研究所 知財管理番号: H31PRO-2307).

If you use this workload in your work, please add the following or a similar
acknowledgement.

```
The AAIC workload log was graciously provided by AIRC, AIST.
```

If you cite this workload, please add the following or a similar reference.

```
Shinichiro Takizawa, Hirotaka Ogawa and Ryousei Takano, "AAIC Workload",
https://github.com/aistairc/aaic-workload, 2019.
```


## Publications

Papers and reports that use this workload.

- 滝澤 真一朗, 小川 宏高, 高野 了成, 大規模GPUクラスタにおける深層学習ワークロードの
  傾向把握, 第170回ハイパフォーマンスコンピューティング研究会, July, 2019.
- Shinichiro Takizawa, Ryousei Takano. Effect of an Incentive Implementation
  for Specifying Accurate Walltime in Job Scheduling. Proceedings of the
  International Conference on High Performance Computing in Asia-Pacific
  Region (HPCAsia2020), Jan. 2020.


## Links

- [About AAIC](https://www.airc.aist.go.jp/info_details/computer-resources.html)
- [AIRC, AIST](https://www.airc.aist.go.jp/en/)
- [AIST](https://www.aist.go.jp/index_en.html)
