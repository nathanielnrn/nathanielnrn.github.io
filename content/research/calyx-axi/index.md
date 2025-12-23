+++
title = "Calyx implementation of AXI Interfaces"
#date = 2023-11-30
#updated = 2025-12-23
weight = 1
description = """After working on a Verilog AXI implementation
I pivoted to working on an AXI implementation written in Calyx itself."""


[extra]
+++


After successfully [generating AXI-wrappers](../axi-interface) in Verilog,
There was interest in showing that [Calyx](https://calyxir.org/) can help
accelerate the development of interfaces and protocols generally.
To that end, work was done on creating [dynamically generated AXI-wrappers][tracker]
implemented in **Calyx**, as opposed to Verilog.

Creating this generator touched on a wide range of topics in the Calyx ecosystem.
While the work performed can eventually be pieced together by me by going through the repos
issues and PRs, a whirlwind tour of worked done to enable these generators follows:

* Create `yxi`, a [memory interface schema](https://github.com/calyxir/calyx/pull/1729)
to describe the shape of Calyx memories.
* Create a [Cocotb testbench](https://github.com/calyxir/calyx/tree/51d92b1a33f6136658ed660f6cc5abd76562d2cc/yxi/axi-calyx/cocotb)
to verify correctness of AXI controllers.
* Create a [handwritten AXI controller](https://github.com/calyxir/calyx/pull/1842)
implemented in Calyx, hooked up to above testbench.
* Add [fixes](https://github.com/calyxir/calyx/pull/1859) and
[features](https://github.com/calyxir/calyx/pull/1927) to our python builder.
* [Create][axi-generator-1] [a][axi-generator-2] [dynamic][axi-generator-3]
[AXI][axi-generator-4] [controller][axi-generator-5] generator implemented in Calyx.
* Update [Cargo build configurations](https://github.com/calyxir/calyx/pull/1974).
* Introduce [passes](https://github.com/calyxir/calyx/pull/1952) to the compiler.
* Introduce compiler driver build [paths](https://github.com/calyxir/calyx/pull/1994).
* (My favorite) introduce [subtyping](https://github.com/calyxir/calyx/pull/2085) of components based on ports into Calyx.
* Introduce [dynamic memory](https://github.com/calyxir/calyx/pull/2111) Calyx primitives with variable latencies to be used as
stand ins to real, offchip memory.
* Introduce an [AXI controller generator](https://github.com/calyxir/calyx/pull/2132) that removes latency assumptions
regarding memories, working with dynamic memories introduced.
*  Get our AXI controllers to integrate with [XRT](https://github.com/calyxir/calyx/pull/2516)
(Xilinx) via generated AXI-lite subordinate controllers
* My most recent contribution was to add a one-stop command to [generate, execute,
and verify](https://github.com/calyxir/calyx/pull/2540) the results of AXI-wrapped Calyx programs.


If you are interested in learning more about the AXI generator work I've contributed
please visit this [issue][tracker] or [reach out](https://calyx.zulipchat.com/) on the Calyx Zulip.

[tracker]: https://github.com/cucapra/calyx/issues/1733
[axi-generator-1]: https://github.com/calyxir/calyx/pull/1855
[axi-generator-2]: https://github.com/calyxir/calyx/pull/1856
[axi-generator-3]: https://github.com/calyxir/calyx/pull/1861
[axi-generator-4]: https://github.com/calyxir/calyx/pull/1862
[axi-generator-5]: https://github.com/calyxir/calyx/pull/1934
[axi-generator-6]: https://github.com/calyxir/calyx/pull/2132
