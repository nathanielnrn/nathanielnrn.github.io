+++
title = "Calyx"
description = "Calyx is a compiler infrastructure for languages that targets hardware accelerators."
weight = 1

[extra]
local_image = "projects/calyx/calyx-project.png"
+++

[Calyx](https://calyxir.org) is a shared compiler infrastructure in the development
of specialized hardware accelarators. Calyx simplifies the encoding of high-level semantics
and automatically optimizes programs when being lowered to synthesizable designs.

#### [View Calyx on GitHub](https://github.com/cucapra/calyx) {.centered-text}

## Contributions

- **AXI Wrapper** generator dynamically produces wrappers for arbitrary calyx programs
that allows these programs to be run on Xilinx FPGAs.
- **Cocotb testbench** verifies the correctness of said AXI wrappers and is
incorporated in Calyx's CI suite. The custom testbench simulates AXI transactions
with dynamically generated AXI wrappers and outputs are compared with expected
baseline results.
- **fud** is a Calyx toolchain driver that pipelines various executions and steps.
Fud includes a number of pipelines that assist with executing programs on FPGAs
utilizing tools such as[Vitis](https://www.xilinx.com/products/design-tools/vitis.html) and
[XRT](https://www.xilinx.com/products/design-tools/vitis/xrt.html).
