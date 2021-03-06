# Logic Synthesis
#### 1. Download library files

Here we are going to use TSMC 0.18 micro meter process technology.
iit018_stdcells.db
iit018_stdcells.lib

#### 2. Start design_vision
```
source /softwares/setup/synopsys/setup.ecen454.bash
design_vision
```
#### 3. Setup library

Open *"File>Setup"*, fill **iit018_stdcells.db** in *"Link Library"* and *"Target Library"*, **generic.sdb** in *"Symbol Library"*, **dw_foundation.sldb** in *"Synthetic Library"*.

#### 4. Load design

Analyze => Elaborate => Read => Save attribute settings. 
  
#### 5. Select top design

Create symbol view.

#### 6. Set parameters

```
set_drive 0.0335 [all_inputs] // set drive strength 
set_load 3 [all_outputs] // set load
```
#### 7. Operating conditions

Make sure library is iit018_stdcells.

#### 8. Timing constraints

Specify clock signal and delay constraints.

#### 9. Check design 

Then ```uniquify```

#### 10. Compile design

#### 11. Report area and save optimized netlist

#### 12. Set the implementation method

```
set_implementation cla add*
set_implementation cla sub*
set_implementation cla submodule/add*
set_implementation wall mult*
set_implementation wall submodule/mult*
```

Check the implementation set.

```
report_resource -h
```


#### 13. Recompile the design
