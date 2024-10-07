# Watch PCB Dials
Welcome, watch modding community!

Hopefully this guide can help someone with zero PCB design experience take advantage of this production method to create their own NH3X (or any other) watch dials.
Minimum order quantities from PCB factories like PCBWay or JLCPCB can be as low as 5 units, at a cost of around $100 USD - perfect for hobby projects.

## Prerequisites

- [KiCad](https://www.kicad.org/download/) - an open source EDA (electronic design automation) tool. We will be using its PCB layout capabilities to generate production files for our dials.

## Getting Started

1. Download and extract the project files.

   ![Screenshot 2024-10-07 210912](https://github.com/user-attachments/assets/44199ef6-4d10-46a9-b90e-5d6b282eca08)

2. Double click Example.kicad_pro (located in the Example folder) to open the project.

> [!NOTE]
> You may encounter messages from KiCad about missing libraries, or asking tp speficy locations for footprints, ignore these or follow on-screen instructions to dismiss them - don't worry, they won't affect what we're doing.

3. Once in KiCad, click the "PCB Editor" button to start editing the PCB layout.

   ![Screenshot 2024-10-07 212200](https://github.com/user-attachments/assets/155968a0-21e3-4179-a7c1-339a96a0d8d8)

## Design

4. Familiarize yourself with the editor, and features of the design. The example provided illustrates the various layers of a PCB design.
   ![Screenshot 2024-10-07 230228](https://github.com/user-attachments/assets/833fe51b-b67b-4293-9543-653c874e20af)

6. Import SVG files with your own designs, or use the built-in drawing tools.
   - Experiment by adding elements into the various layers. Visualize changes with the 3D viewer to see how they affect the final product.
   ![Screenshot 2024-10-07 230703](https://github.com/user-attachments/assets/5d52d6a5-e8bd-4bbc-9d64-65f536b7d322)

> [!TIP]
> When importing SVG files, make sure to first save paths in the file with no outline, or set the "DXF default line width" in KiCad's import window to 0.

## Production

6. Generate and export production files (gerbers, drill, and sometimes map files)
   - [Guide for PCBWay](https://www.pcbway.com/helpcenter/generate_gerber/Generate_Gerber_file_from_Kicad.html)
   - [Guide for JLCPCB](https://jlcpcb.com/help/article/how-to-generate-gerber-and-drill-files-in-kicad-8)

7. Place your order
   - Most services (including PCBWay and JLCPCB) will ask for the files generated in the previous step to be uploaded as a zip file.
   - Each service will have its own ordering form for specifying production parameters. The ones we need to pay attention to are:
     1. Layers: 1 or 2 (see tip below).
     2. Material: FR4 (best and most cost effective for the 0.4mm thickness we require.
     3. Thickness: 0.4mm (as per the [NH series spec](https://www.timemodule.com/uploads/attachments/download/Spec%20Sheet/NH35_SS.pdf)).
     4. Soldermask colour: the base colour of the PCB/dial.
     5. Silkscreen colour: the colour of anything on the F.Silkscreen layer (usually constrained by soldermask colour).
     6. Surface finish: ENIG (immersion gold) recommended. Avoid HASL - this surface finish is basically blobs of solder.
     7. Order number: you will either need to specify a location for the order number in the design (following the factory's instructions), or pay $1-$2 to remove the order number altogether. The last thing you want is an order number of the face of your dial.
     8. Other settings e.g. minimum drill sizes, vias, copper thickness can be left at defaults for the most optimal cost.

> [!TIP]
> 1 and 2 layer PCBs often cost the same. You can rotate a second design by 180 degrees and place it on the reverse side of a 2 layer PCB (use the B.* layers: B.Cu, B.Mask, B.Silkscreen, etc.). This way you get two designs produced for the price of one!
> Note, this should work for NH38 dials too, but the rotation is not exactly 180 degrees thanks to the slightly offset position of the open heart. On paper this offset is +/- 4.687 degrees, but I have never tried it.

### Happy Modding!


See a problem with this guide or project file? [Submit an issue here](https://github.com/dmohanja/Watch-PCB-Dials/issues).


>Oh, would you look at that! There's still enough space here for a [sneaky self-promo](https://runbybirds.etsy.com)
     
