# KiCAD FAQ

# Can I edit a single instance of a footprint in KICad?

Yes, you can edit a single instance of a footprint directly 
on the PCB without affecting other identical components, because 
once placed on a board, each footprint instance functions as an 
independent copy.

## How to Edit One Footprint Instance

- Open Properties: 

Hover your mouse over the specific footprint on your PCB and press E 
(or right-click the footprint and select Properties).

- Modify Local Settings: 

Change fields like text, reference designators, values, or graphical elements. 
These changes apply only to that specific instance on the board.

- Edit Pads/Graphics Locally: 

If you need deeper geometric changes (like moving a pad or changing a silkscreen line) 
just for that single part, select the footprint, press `Ctrl + E` to open it in the 
Footprint Editor, make your tweaks, and do not save it back to the global library. 
Instead, your edits remain isolated to that unique copy on the PCB canvas unless 
explicitly pushed or saved elsewhere.

> Note: 

Be careful if you run an "Update Footprint from Library" command later, as syncing 
with the master library can overwrite your local, one-off modifications if the 
reference matches a standard library item.