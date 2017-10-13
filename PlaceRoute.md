# Place and Route

#### 1. Start Cadence Encounter

```
source /softwares/setup/cadence/setup.edi142.bash
encounter -64
```

#### 2. Download library files

Put **iit018_stdcells.lef** **iit018_stdcells.tlf** **iit018_stdcells.lib** in the same directory.
Put **encounter.conf** in the same directory.

#### 3. Revise configuration

```
set my_toplevel topmodule_name
set rda_Input (ui_topcell) topmodule_name
set rda_Input (ui_netlist) netlist.v
```

#### 4. Floorplan

Set core margins as m.

#### 5. Add power rings

Add ```gnd vdd``` to nets.
Change Top and Bottom layer to metal3.
Set width as < m/2. 
Check center in channel.

#### 6. Add power stripes

Add ```gnd vdd``` to nets.
Change width to m/4. 

#### 7. Route

Route > Special route. 
Place > Standard cells.
Route > Nanoroute > Route // Choose timing driven.

#### 8. Save parasitic parameters.

Timing > Extract RC
Save SPEF, which will be used in STA. 
