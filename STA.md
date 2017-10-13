# Static Timing Analysis

#### 1. Environment setup

Put **iit018_stdcells.db** and **iit018_stdcells.lib** in the same directory.
Put optimized verilog netlist from design_vision in the same directory.

#### 2. Start Primetime on Hera

```
source /softwares/setup/synopsys/setup.primetime.bash
primetime
```

#### 3. Search and link path

```
set search_path "." \\ set search path as current directory
set link_path {* iit018_stdcells.db}
```

#### 4. Setup design

```
read_verilog verilog_netlist_file
current_design topmodule
link_design topmodule
read_parasitics design.spef // read the parasitic parameters

```
