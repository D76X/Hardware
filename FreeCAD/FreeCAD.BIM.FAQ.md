# Can I change the size of the Grid in FreeCAD BIM?

Yes, you can change the size of the grid in FreeCAD BIM, though 
the method depends on whether you mean the Draft/BIM grid or an 
Arch/BIM Axis Grid. 

[1] (https://forum.freecad.org/viewtopic.php?t=8446), 
[2] (https://forum.freecad.org/viewtopic.php?t=40996), 
[3] (https://www.youtube.com/watch?v=T_EvMReliNw&vl=en)

1. Changing the Draft / BIM Workspace Grid

To change the spacing and size of the background grid used in the Draft and BIM workbenches: 

[1] (https://wiki.freecad.org/Manual:BIM_modeling/en), 
[2] (https://forum.freecad.org/viewtopic.php?t=8446)

1. Open FreeCAD and go to the top menu: `Edit > Preferences`. 
[1] (https://forum.freecad.org/viewtopic.php?t=8446)

2. Click on Draft in the left-hand panel, then select the Grid and snapping tab. 
[1] (https://forum.freecad.org/viewtopic.php?t=8446)

3. Under the Grid section, modify:
	• Grid spacing: The distance between grid lines (e.g., 1000mm for a 1-meter grid).
	• Grid size: The total number of grid lines.
	• Main lines every: How often a major grid line appears. 
    [1] (https://forum.freecad.org/viewtopic.php?t=8446), 
    [2] (https://wiki.freecad.org/Manual:BIM_modeling/en)

4. Click OK. [1] (https://forum.freecad.org/viewtopic.php?t=8446)

5. Toggle the grid off and on using the Toggle grid button on your toolbar to refresh the view. 
[1] (https://forum.freecad.org/viewtopic.php?t=8446), 
[2] (https://wiki.freecad.org/Manual:BIM_modeling/en)

(Note: In some versions, the "BIM Setup" dialog box also has a grid field, 
though users have noted it may not always sync properly with the Draft 
preferences—so changing it directly under `Edit > Preferences > Draft > Grid and snapping` 
is the most reliable path). 
[1] (https://forum.freecad.org/viewtopic.php?style=3&t=87680)

2. Changing an Architectural Axis Grid (Arch Grid)

If you are working with an actual architectural column/axis grid object in your BIM model: 
[1] (https://www.youtube.com/watch?v=T_EvMReliNw&vl=en), 
[2] (https://wiki.freecad.org/Arch_Grid)

- By properties: 
Select the Grid object in the tree view and edit its Width, Height, Rows, 
or Columns properties directly in the Data tab.

- By task panel: 
Double-click the architectural grid object in the model tree to open the editing task panel, 
where you can adjust line distances, spacing, and add or remove axes. 
[1] (https://wiki.freecad.org/Arch_Grid), 
[2] (https://www.youtube.com/watch?v=T_EvMReliNw&vl=en)
