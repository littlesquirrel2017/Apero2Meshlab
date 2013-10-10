Apero2Meshlab
=============

Apero2Meshlab is a micmac patch that adds the possibility to export the Apero orientations of cameras to a meshlab mlp file that can be loaded by Meshlab.

Code file CPP_Apero2Meshlab.cpp should be placed in the src/uti_files/ dir of micmac. 
Also Apero2Meshlab.c should be copied in the right place.
And then also other changes to the micmac code are needed in order to work!

I provide a bash script for applying the patch and copying the files so to simplify this part.

Run it as:
```bash
./intall_patch.sh path/to/micmac_source [-r]
```

where:	

	-r undo the changes


If you need support please contact me

When patched and compiled you will have a mm3d Apero2Meshlab tool that provides two methods for exporting to meshlab:
1. undistort images with drunk and write out a mlp file with the cameras in it
2. keep the images as they are and write the mlp file using the first two distortions coefficients of the camera only.

Both of them does _NOT_ provide exact exports. Both are approximated in some way.

Extended Install Info
---------------------

First of all. Are you compilig micmac/culture3d by yourself? 
If not do that and come back later. This is a source patch that need to be compiled together with the rest of micmac. 
You can't use it on pre-compiled binaries.

So for installing you can do this way, open a bash console and:
```bash
cd /home/tizio/code #or where your use to place you code stuff
git clone https://github.com/luca-penasa/Apero2Meshlab.git Apero2Meshlab #this will download the whole source in the /home/tizio/code/Apero2Meshlab folder
```

Then simply execute the commands as above:
```bash
./intall_patch.sh path/to/micmac_source /home/tizio/code/culture3d # where culture3d is the path to the mimac sources
```

This should install the patch.

If you want to do it by hand you can install the two cpp files in the right folder, then look at:
https://github.com/luca-penasa/Apero2Meshlab/blob/master/patchset.patch
and perform the required changes.

Let me know if the process is not working (recent changes to micmac source could have invalidated the patch)
