# KiCAD FAQ

# Where is the "missing 3d models" button in KiCAD 10?

In KiCad 10, the button to add or configure 3D models is found by opening a footprint's properties (E key), 
going to the 3D Models tab, and clicking the folder/add icon or the configuration path settings.

## Finding and Fixing Missing 3D Models in KiCad 10

- Path Variable Issues: 

KiCad 10 changes how environment variables handle paths (such as transitions from older versions referencing KICAD8_3RD_PARTY). 
If your models are missing globally or from third-party libraries, go to `Preferences > Configure Paths` 
and ensure your environment variables are correctly mapped or manually add a matching path variable.

- Adding a Model to a Footprint:

Open your PCB or Footprint Editor and select the component.
Press E to open Footprint Properties.
Navigate to the 3D Models tab.Click the Add 3D Model (folder icon) button at the bottom/side 
of the model list to browse for your `.step` or `.wrl` file.

- Default Formats: 

KiCad 10 defaults primarily to `.step` files for official library 3D shapes, so ensure your 
paths point to valid directories containing the updated model formats.

---

# How do I place the KiCad icon on the silkscreen?

To place the KiCad icon or any custom logo on your PCB silkscreen, use the built-in 
Bitmap to Component Converter tool.

[Add graphics and logos to PCBs in KiCAD Penguin Tutor](https://www.youtube.com/watch?v=JVZk_96jJsI#:~:text=Use%20the%20bitmap%20to,printed%20and%20white%20areas)   

- Step 1: 
Prepare the ImageFind a clean, high-contrast black-and-white image or the official KiCad logo file (.bmp or .png).
Ensure the background is black and the logo/icon is white if you want it printed, or use the negative option inside 
the converter.

- Step 2: 
Convert the Image to a FootprintOpen the main KiCad project launcher.
Click on the Bitmap to Component Converter (Image Converter) tool.
Load your image file into the converter.
Set the output format to Footprint and choose the target layer as Front Silk Screen (F.SilkS).
Adjust the resolution (dots per inch) or scale to resize the icon.
Click Export to file to save it as a footprint into a custom or personal footprint library (ending with .pretty), 
or use the Clipboard / Export to Clipboard feature.Step 3: Place the Icon on the PCBOpen your PCB Editor in KiCad.
If you exported to a library, add that library via `Preferences > Manage Footprint Libraries` (if not already added).

Click the Add Footprints tool (shortcut F) and search for your newly created logo/icon footprint.Alternatively, 
if you exported it via the clipboard, right-click and select Paste directly into your PCB layout.

Click to drop the icon onto the board, then use the move (M) or rotate (R) tools to position it correctly on the silkscreen.

---

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