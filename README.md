Mesh Labeler – User Manual
==========================

Created by [Tai-Hsien Wu](https://github.com/Tai-Hsien) at the Ohio State University.

This project is mainly based on [Visualization Toolkit (VTK)](https://vtk.org/) and, especially, [vedo](https://github.com/marcomusy/vedo).

------------

1.  Download installer version from
	<https://drive.google.com/file/d/1CoG3lq2MbpTl00IV0T6R4icbxWD-2i-f/view?usp=sharing>
	or portable version from
    <https://drive.google.com/file/d/1Cp4Tl0noN039VGEDD8uJQ06R18wD-ypz/view?usp=sharing>

2.  Install the program or extract ZIP file.

-   For the installer version, execute **Mesh_Labeler_Setup.exe** to install this program. After that, you can find a shortcut in the Windows Start menu.

-   For the portable version, extract the ZIP file, and there will be a folder named
    **Mesh_Labeler_win_v1.1**. Execute **Mesh_Labeler.exe** to open the program. It might take a few seconds to launch (sometimes longer). 
	
-   Note: Sometimes the portable version need a very long time to open or cannot open due to the antivirus block. Please use the installer version if possible.
	
3. 	Once the program is launched, you will see the user interface, as shown below.

![Figure 1. The user interface of **Mesh Labeler**](./figure1.jpg)

4.  Use the top-right button to open a mesh file. Currently, the program supports VTP
    (with an attribute named **Label** , a cell scalar array) and STL, OBJ, and PLY files. There are four examples (Example_01.vtp, Example_02.stl, Example_03.obj, and Example_04.ply) that you can download via my github. Note: Since STL, OBJ, PLY files do not have the attribute **Label**.
    The program will initially generate the cell scalar array (i.e., **Label**)
    and assign value of 0 (i.e., all background) to the array for each cell
    (i.e., for each triangle) when loading these types of files. The
    screenshot after loading an appropriate VTP will look like below.

![Figure 2. After loading a suitable VTP file, you can see the model in the center of the window.](./figure2.jpg)

5.  The view on the scene can be changed by using various mouse actions, as
    follows:

-   Rotating the mouse wheel upwards will zoom in, and downwards will zoom out.

-   Holding the middle mouse button down and dragging will pan the scene or
    translate the object.

-   Holding the left mouse button down and dragging will rotate the camera/actor
    in the direction moved.

6.  There are two ways to annotate a mesh, described as follows.

-   1st way: Change label by selecting cells (triangles)

The simplest way to select cells is to right-click a cell. The selected cells are highlighted by grey color. An advanced way to select cells is to press "s" to enter "Spline model",
 where you can add points by left click on the mesh. Once you decide to use the selected points (number of points should be larger than 2) to generate a spline, press "Enter". All cells within this spline will be highlighted.
 Press "c" to clean the current selection. Before you execute the change, please make sure the *active label* is what you plan to apply. The default *active label* is 0. You can change it in the textbox on the top right.
When you satisfy the selection, press "e" to execute the change which assigns the value of *active label* on those selected cells. Please follow the colormap in the bottom window
to assign/fix the label of each cell for a dental tooth model.

-   2nd way: Change all cells with a specific label number one shot

In this way, we can entirely change cells those labels are a specific value to be
another value. There are two textboxes on the middle-right side. Once they read valid label numbers, click "Change!"
button. Then, all cells with the old label will be changed to be a new label.

7.  Once everything is done, you can save the result by using the **Save VTP
    file** button. The program will save the result in the VTP format with the
    **Label** cell scalar attribute.

Problems?
--------

If you have any questions about using this software, please feel free to open an issue or email me.