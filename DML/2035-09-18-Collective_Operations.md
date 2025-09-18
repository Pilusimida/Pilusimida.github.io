---
title: "Collective Operations
date:
categories:
---
# All-Reduce
Definition:
- Stores reduced results across all the nodes
For distributed learning:
- Mirror all the model parameters across all workers(no Parameter Server).
- Workers exchange parameter updates directly via an all-reduce operation.

## Network Topology
- Fully-connected Topology
- Tree-based Topology
- Ring-based Topology
  - Most communication efficient