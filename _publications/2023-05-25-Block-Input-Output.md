---
title: "IOCost: Block Input-Output Control for Containers in Datacenter"
collection: publications
permalink: /publication/2023-05-25-Block-Input-Output.html
excerpt: 'IEEE Micro Top Pick from all of the computer architecture conference papers of 2022'
date: 2023-05-25
venue: 'IEEE Micro (Volume: 43, Issue: 4, July-Aug. 2023)'
paperurl: 'https://doi.org/10.1109/MM.2023.3277783'
citation: 'T. Heo et al., "IOCost: Block Input–Output Control for Containers in Datacenters," in IEEE Micro, vol. 43, no. 4, pp. 80-87, July-Aug. 2023, doi: 10.1109/MM.2023.3277783.'
---
Resource isolation is a requirement in datacenter environments. However, our production experience in Meta’s large-scale datacenters shows that existing input–output (IO) control mechanisms for block storage are inadequate in containerized environments. This article presents IOCost, an IO control solution designed for containerized environments that provides scalable, work-conserving, and low-overhead IO control for heterogeneous storage devices and diverse workloads in datacenters. IOCost performs offline profiling to build a device model and uses it to estimate device occupancy of each IO request. To minimize runtime overhead, it separates IO control into a fast per-IO issue path and a slower periodic planning path. A novel work-conserving budget donation algorithm enables containers to dynamically share unused budget. We have deployed IOCost across Meta’s datacenters comprising millions of machines, upstreamed IOCost to the Linux kernel, and open sourced our device-profiling tools.