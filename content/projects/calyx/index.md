+++
title = "Calyx"
description = "Calyx is a compiler infrastructure for languages that targets hardware accelerators."
weight = 1

[extra]
local_image = "projects/calyx/calyx-project.png"
+++

[Calyx](https://calyxir.org) aims to be a shared infrastructure in the development
of specialized hardware accelarators. Calyx simplifies the encoding of high-level semantics
and automatically optimizes programs when being lowered to synthesizable designs.

#### [View Calyx on GitHub](https://github.com/cucapra/calyx) {.centered-text}

## Contributions

- **AXI Wrapper** generator dynamically produces wrappers for arbitrary calyx programs
that allows these programs to be run on Xilinx FPGAs.
- **Cocotb testbench** that verifies the correctness of said AXI wrappers.
