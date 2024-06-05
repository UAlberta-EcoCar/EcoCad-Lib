# EcoCar/KiCad Electrical Parts Library
This repository is dedicated to making a parts library for electrical components used in EcoCar. By standardizing all the parts we use in the club, we can make ordering processes easier. It will be up for debate whether or not we standardize chip resistors and multi-layer ceramic capacitors (MLCC). 

The primary purpose is to cover significant components like inductors, operational amplifiers, power regulators, and others not native to the KiCad standard library. We should, however, save any parts used from the KiCad standard library if it is not something simple like a chip resistor or MLCC. Diodes should be included in the EcoCar standard parts library.

The digi-key library of parts was added to the repository on 2024-06-04 as a submodule. Whenever this submodule is updated, please update the date.

## How to install the libraries - as of KiCad 8
Installation of the EcoCad library involves three steps: schematic symbol link, footprint symbol link, and the 3D model link. You have to tell KiCad that these libraries exist by showing KiCad where to look for them.

1. Open KiCad using their blue icon, do not open a schematic or pcb file directly
2. Click on preferences, three options are of interest: Configure paths, Manage symbol libraries, and Manage footprint libraries
3. Click first on manage symbol libraries, and click the '+' under the global tab
4. Give it the nickname 'ecocad_lib_symbols'
5. Browse for the location of where you stored the EcoCad library by clicking on the folder icon. The library path should be the full path to ecocad_lib_symbols.kicad_sym then hit OK. Do NOT use any path substitutions
6. Go to manage footprint libraries and do the same thing except this time make sure you add the full path to the ecocad_lib_footprints *folder*. Give it a similar nickname 'ecocad_lib_footprints' then hit OK. Again *no* path substitutions
7. Finally, go to Configure paths and add a new environment variable. It ***MUST*** be called 'ECOCAD_3DMODELS' otherwise the footprints library will not be able to find the 3D models associated with the footprint. The path, like the schematic and footprint lib, needs to be the path to 'ecocad_lib_3dmodels' *folder*. Once this is done, hit ok
8. To check and see if this worked, open the schematic editor and search up 'ecocad_lib_symbols' in the parts picker (hotkey a). Choose the LM25122 and press ok
9. After placing the part, highlight it and press 'e'. Click on the footprint field and then click the book like icon on the right. This should bring up the footprint selector box and there should already be one highlighted likely titled 'PWP20_TEX'. You can switch between views of the footprint and the 3D model. Both should be there.

If this didn't work for you, repeat these steps and double check that you have inputed the correct paths for each step. The nickname for each step is CASE SENSITIVE and must be IDENTICAL. If this still hasn't worked, please reach out for help.

## How to install Digi-key library
1. In your terminal (i.e git bash) run the command 'git submodule init', then 'git submodule update'. This will clone the digi-key submodule library onto your local copy
2. As in the previous steps, add whichever symbol library desired from the legacy folder of symbols (choose Legacy format in global tab) and add the foot prints folder as before
