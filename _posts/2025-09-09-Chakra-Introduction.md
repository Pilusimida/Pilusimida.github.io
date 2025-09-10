---
layout: post
title: "Chakra Introduction"
date: 2025-09-09
---
<!-- # Chakra Introduction -->

## OPEN-SOURCE TOOLS
### Execution Trace Converter
**Desp**: convert execution trace in various schemas to the Chakra scheme.
**Example**: 
- PyTorch execution traces are in the JSON format and CONVERTER uses the JSON parser to read the execution traces.
- Computation nodes in PyTorch have the *duration* field.
- Communication nodes in PyTorch are identified by the name of nodes. The communication types and size are determined by its child node, whose name starts with "nccl".
### Execution Trace Visualizer
**Desp**: visualize the dependencies between nodes in a trace.

### Timeline Visualizer
**Desp**: visualize the execution of nodes when a trace in simulated in a simulator.

### Test Case Generator
**Desp**: generate arbitrary execution traces by offering libraries to describe traces.

### Execution Trace Feeder
**Desp**: parse traces and feed them into simulators and emulators