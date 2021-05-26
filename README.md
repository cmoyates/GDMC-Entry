# Minecraft Settlement Generator

## Description
This is an MCEdit filter (and several schematic files) that can be used to generate custom designed "settlements" in Minecraft. 

This generator uses Poisson Disc Distribution to get a bunch of pseudo-random points in the selected area (that are a specified distance apart), then places a bunch of premade schematics at those points. While it's doing that it keeps track of all the positions of the entrances of all of the structures, and after they're all placed it connects them with an A* path. There are some building-specific randomizations to keep everything from looking completely identical, and some additional details such as streetlights and the path block changing when over water.

This generator also simulates a specified number of families over a specified number of generations and generates certain details in the settlement accordingly (such as a cemetery that includes tombstones for all members of previous generations, family crests in the form of banners on each tombstone, and flags on each of the houses showing the family of the current inhabitants).

## Usage
1. Download / install Minecraft: Java Edition 
2. Create a new world, explore the area where you would like the settlement to be generated and then exit the game
3. Download MCEdit from [this link](https://github.com/Podshot/MCEdit-Unified-Preview/releases/tag/MCEdit-Unified-1.6.0.53-testing) and extract it into a folder
4. In the MCEdit folder, navigate to the "stock-filters" subfolder
5. Download the contents of this repository as a .zip file and extract its contents into the "stock-filters" folder
6. Open MCEdit and open the Minecraft world that you created earlier
7. Select the area in the world where you want the settlement to be
    - The settlement generation was tested on sizes of 256x256x256 and 1024x256x1024, these will work assuming you explored the entirety of the selection area in game, while other sizes may not work.
    - ***Always make the size of the selection on the Y-axis 256 blocks***, otherwise some weird stuff might happen with the heightmaps and I don't know how that will affect the settlement
8. Click the "Filter" button in the bottom toolbar, select "GDMCSubmission" in the dropdown menu at the top of the box that appears on the left, and then click the button in that box labelled "Filter"
    - ***Although there are three options that can be changed in the MCEdit GUI, I strongly recommend keeping them at their default values***
9. Wait for the process to complete (this will take a few minutes), then press CTRL+S to save the world
10. Once the saving is complete, open the world in Minecraft to see the newly generated settlement

## Credits
With the exception of the things stated below everything in this project was done by me:

- There are some snippets of code from the built-in MCEdit filter "Topsoil" that I used to get a heightmap efficiently. I have clearly indicated when this is done in the code, but for the sake of clarity, it's mainly from lines 466 to 487 and from lines 738 to 751. Doing a bit of digging it looks like the "Topsoil" filter was developed by codewarrior0 whose GitHub you can check out [here](https://github.com/codewarrior0).

- I had a ton of help designing the actual structures found in the schematics from my classmate James Hudson whose GitHub you can check out [here](https://github.com/jhudson1998).

- The implementation of Poisson Disc Distribution I used was based off of [this paper](https://www.cs.ubc.ca/~rbridson/docs/bridson-siggraph07-poissondisk.pdf) by Robert Bridson.
