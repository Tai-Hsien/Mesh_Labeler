Mesh Labeler3 – User Manual
==========================

[![lics](https://img.shields.io/badge/license-MIT-blue.svg)](https://en.wikipedia.org/wiki/MIT_License)

Author: [Tai-Hsien Wu](https://github.com/Tai-Hsien)

This project is powered by [SOVE Inc.](https://soveortho.com) and is mainly developed based on [Visualization Toolkit (VTK)](https://vtk.org/) and, especially, [vedo](https://github.com/marcomusy/vedo).

This program is originally developed to conveniently label/annotate dental mesh model. It can also work on any other type of mesh model.

------------
Current version: 3.1

* added landmarking function
* improved the stability of spline selection
* added adjustable landmark radius

------------

1.  Download installer from <https://app.box.com/s/5tpd2h3qzvz2oh9b5khecwr0u088xfgv> or portable version from <https://app.box.com/s/e0ygnmmznjlpeyf20silvyj4cudf9bn4> (click "Download" on top-right without sign-in).

2.  Extract ZIP file, and there will be a folder named
    **Mesh_Labeler3_portable**. Execute **Mesh_Labeler.exe** to open the program. It might take a few seconds to launch (sometimes longer). 
	
3. 	Once the program is launched, you will see the user interface, as shown below.

![Figure 1. The user interface of **Mesh Labeler**](./figure1.jpg)

4.  Use the bottom-right button **Load** to open a mesh file. Currently, the program supports VTP
    (with an attribute named **Label**, a cell scalar array) and STL, OBJ, and PLY files. There are four examples (Example_01.vtp, Example_02.stl, Example_03.obj, and Example_04.ply) that you can download via my github.
	Note: For those files that do not contain attribute **Label** (e.g., STL, OBJ, PLY), the program will initially generate a cell scalar array called **Label** 
    and assign 0 (i.e., all background) to the array for each cell
    (i.e., for each triangle) after loading them. The screenshot after loading a VTP with the cell array **Label** will look like below.

![Figure 2. After loading a suitable VTP file, you can see the model in the center of the window.](./figure2.jpg)

5.  From Version 2, users can define the number of labels, label color, and label description by themselves. To do it, please modify  the **colormap.csv** in the folder **Mesh_Labeler3_portable**, which is a CSV file containing five columns: Label, R, G, B, Descriptions.
	Please keep the headers as the default file. Each row corresponds to a label.

6.  The view on the scene can be changed by using various mouse actions, as
    follows:

-   Rotating the mouse wheel upwards will zoom in, and downwards will zoom out.

-   Holding the middle mouse button down and dragging will pan the scene or
    translate the object.

-   Holding the left mouse button down and dragging will rotate the camera/actor
    in the direction moved.

7.  There are two methods to annotate a mesh. Users can go for each method by selecting the corresponding tab. Different methods have different input(s) under their tabs.

-   Spline Method: Change label by selecting cells (triangles)

The simplest way to select cells is to right-click on a cell. The selected cells are highlighted by grey color. Right-click on a selected cell can cancel its selection.
An advanced way to select cells is to press "s" to enter "Spline model", where you can add points by left click on the mesh. Once you decide to use the selected points (number of points should be larger than 2) to generate a spline, press "Enter". All cells within this spline will be highlighted.
 Press "c" to clean the current selection. Before you execute the change, please make sure the *active label* is what you plan to apply. The default *active label* is 0. You can change it through the spinBox under the Spline tab.
When you satisfy the selection, press "e" to execute the change which will assign the value of *active label* on those selected cells. Please follow the colormap to assign/fix the label of each cell for the mesh.

-   One-Way Swap Method: Change all cells with a specific label one-shot

In this way, we can entirely change cells from one label to another label.
There are two spinBoxs (i.e., *Original label* and *New label*) under the One-Way Swap tab. Once they are all set, click **Change!** button; then, all cells with the original label will be changed to be the new label.

8.  Once everything is done, you can save the result by using the **Save** button. The default extension file is **VTP**, which will save the result in the VTP format with the cell array **Label**.
	If the extension file is **STL** or **OBJ**, Mesh Labeler will save each label to an individual **STL** or **OBJ** file. For example, a 15-class mesh model will output 15 STL files.
	
9. Version 3 adds a new function for identifying landmarks on mesh data. To do that, please select "landmarking" tab on the top of the program.

-   Landmarking Method: Annotate landmarks on the loaded mesh

Note that a mesh must be loaded before doing any actions in landmarking mode.
Users can load a list of landmarks from a fcsv-format file (fiducials file exported from [3D Slicer](https://www.slicer.org/)) by clicking **Load FCSV** or create a new list of landmarks by clicking **Add** (default position is the origin for a new landmark).
All landmarks are shown as red spheres in the view, and the name and position of landmarks can be found in the table under this tab. User can select a landmark by clicking the corresponding column of landmark in table.
The selected landmark will be represented by a blue sphere, as shown below.
A selected landmark can be renamed by pressing **Rename** button. A new window will pop up to ask the new name for the landmark.
A selected landmark can also be relocated by pressing **Relocate** button. After that, please left-click on the mesh for the new location of the landmark.
To unselect a landmark, please right-click mouse.
The list of landmarks can be exported as fcsv-format by clicking **Save FCSV**.
For the format of FCSV file, please refer to the example (Example_01_UR1.fcsv) in the repository or portable folder.


![Figure 3. The landmarking method in **Mesh Labeler**. The blue and red spheres represented the selected landmark and the rest landmarks in a given list of landmarks.](./figure3.jpg)

Reference
--------
If you think [Mesh Labeler](https://github.com/Tai-Hsien/Mesh_Labeler) is useful for your research project, please star this project!


Problems?
--------

If you have any questions about using Mesh Labeler, please feel free to open an issue or email me (tai-hsien.wu@soveortho.com).