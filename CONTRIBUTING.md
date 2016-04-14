# How to contribute a new part

1. Fork and clone the repository:

        git clone git@github.com:your-username/fritzing-parts.git

2. Create a branch for the part you want to contribute:

        git branch your-part
        git checkout your-part

3. Place the `.fzp` file in the core folder and the related `.svg` in the view-specific folders:

        description.fzp -> core/
        breadboard_view.svg -> svg/breadboard/ 
        schematic_view.svg -> svg/schematic/ 
        pcb_view.svg -> svg/pcb/ 

    See below for exporting your `.fzpz` file to the correct structure.

4. Then test and push!

    In order to make Fritzing recognize the new part, run Fritzing and select _Edit > Rebuild parts database_. The part will now be included in the database/index, and become available in the library window.

## How to export your part from within Fritzing (FZPZ)

If you created your part inside the Fritzing app, you will first need to export it and then extract it into the correct structure:

1. Export a `.fzpz` bundle of the part:

   Find the part in the parts library, right-click it and select _Export Part..._

2. Extract the `.fzpz`:

   First, make sure the filename is a good and concise description of your part. If not, rename it.

   Use the [fzpzclean.py python script](https://github.com/fritzing/fritzing-app/blob/master/tools/part-gen-scripts/misc_scripts/fzpzclean.py) to extract the bundle into the proper structure
   
       python fzpzclean.py -f <folder-with-fzpzs> -d <fritzing-parts-folder> -o core -r

3. Give it a unique **moduleId**

   Since you now have the same part twice, they will have conflicting IDs. In the first line of the `.fzp` file, find the property `moduleId` and change it to something unique. Usually, the full part name will do (without spaces).
   

# How to make your part visible in the part library window

This is optional, because even if your part is not directly visible in one of the bins, it is still accessible via the search and as alternative to similar parts (via a property change).

*to do*
  

# Advanced part makers: Manual part creation
*to do*

# Contributing a fix
fritzing has an obsolete mechanism. 
*to do*

