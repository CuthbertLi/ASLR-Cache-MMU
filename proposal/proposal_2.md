# Proposal 2: Cache Replacement Policy and Bélády's anomaly

## Introduction 

Bélády's anomaly is the phenomenon in which increasing the number of page frames results in an increase in the number of page faults for certain memory access patterns. This paradoxical phenomenon is first described by László Bélády in 1969. 

[Fornai et al., 2010] has shown Bélády's anomaly is unbounded. That means there is some reference strings to any arbitrary page fault ratio. 

## Interesting problems 

It is known that Bélády's anomaly is highly related to page replace policy. Some replacement policies like FIFO is possible to experience it, but other policies like LRU cannot experience this anomaly. Therefore, the questions are: 

What is the necessary and sufficient condition for a replacement policy to experience Bélády's anomaly? 

What is the necessary and sufficient condition for a reference string and page size under a certain replacement policy to experience Bélády's anomaly? 

Besides, since Bélády's anomaly is unbounded, is it always the case? In other word, is it the case that Bélády's anomaly is unbounded whenever Bélády's anomaly occurs for a replacement algorithm, or under a certain condition? 

## How is it related to Operating Systems? 

Some may argue caching is not an operating systems topic. We cannot disagree more. Caches are central to the design of a huge number of hardware and software systems, including operating systems, Internet naming, web clients, and web servers. Therefore, cache is an especially important topic in operating systems. 

Cache replacement policy, in particular, is widely studied in operating systems. Examples include but are not limited to tranlation lookaside buffer (TLB) and buffer cache on disks. 

It is the job of kernel to map virtual address to physical address, thus implementing virtualization of memory. However, virtualization is not free. It is slower. Therefore, a good cache replacement policy is critical in this design. Bélády's anomaly is also really concerning. 