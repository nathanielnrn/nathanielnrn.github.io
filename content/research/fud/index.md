+++
title = "Push Button FPGA Toolchains"
#date = 2023-11-30
#updated = 2023-11-30
weight = 2
description = "I've worked on integrating custom scripts into toolchains to allow for the easy testing and execution of programs on FPGAs."


[extra]
+++

In trying to get Verilog AXI interfaces to [interface with XRT](../axi-interface)
it made sense to have a system that allowed for rapid testing of iterations of my
AXI interface.
Ideally, we would have a simple system to either simulate programs or actually execute them on our
[Xilinx Alveo U50](https://www.xilinx.com/products/boards-and-kits/alveo/u50.html).

Unfortunately, going from a program to doing either of the above was enough of a
chore that it required an [entire page of dedicated documentation](https://docs.calyxir.org/fud/xilinx.html)
detailing environment variables that needed to be set and flags that needed
to be passed in in order to have any hope of getting programs to execute properly.

To this end, I worked on creating [fud](https://docs.calyxir.org/fud/index.html) stages
that would simplify the process of running programs on our FPGA.

`fud` is a command line tool that pipelines together the various tools and stages
needed to convert Calyx programs into desired output programs. In our case,
we wanted to go from Calyx to [xclbins](https://xilinx.github.io/XRT/master/html/formats.html)
to actually simulating/executing.

The fud stage I [created](https://github.com/cucapra/calyx/blob/master/fud/fud/xclrun.py)
parsed json files into inputs to programs,
and utilized [PYNQ](https://www.pynq.io/) to run these programs on hardware.

The work involved creating custom bash and python scripts, integrating said
scripts into existing tools, diving into the documentation of PYNQ and integrating
that as well, and expanding configuration options to correctly set environment
variables and pass in flags as appropriate.

The final product allows us to run programs in two steps.

1. Create an `xclbin` (equivalent to compiling an executable via something like gcc):
```
fud exec source-program.futil -o output-file.xclbin --to xclbin
```
2. Execute said `xclbin` on an FPGA (equivalent to running an exectuable)
```
fud exec some-output.xclbin --from xclbin --to fpga -s fpga.data program-input.data
```





[//]: # (Getting programs to to run on FPGAs is _hard_. If you've ever fought your way)


[//]: # (through [Vitis documentation](https://docs.xilinx.com/r/en-US/ug1393-vitis-application-acceleration/Kernel-Interface-Requirements)

[//]: # (or -- lord forbid-- getting a program to execute on an FPGA via the commandline,)

[//]: # (you may have an inkling of what I'm talking about.)

[//]: # ()

[//]: # (In trying to get [Calyx] programs to run on)









[calyx]: https://calyxir.org/
