https://www.scaler.com/academy/mentee-dashboard/class/211430

Learnt CAP, PACELC theorems. Basically:
- CAP: if a system has partitions then it can either be consistent or available, but not both. *This means if a system is likely to develop partitions we should decide what is more important - availability or consistency*.
- PACELC: this is a more complete theorem. The first PAC is exactly the CAP theorem. The ELC means, that if partitions are not present in a system: then a system can be low-latency (fast) or consistent, but not both. *So if P, choose A or C. else choose L or C*.

Implementation wise, the choices are baked into the code (say in backend app controllers).