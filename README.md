# VirtualDirector
 A tool for rehearsing live theatre remotely

Hardware requirements:
For optimal use we recommend using a PC with an AMD 5000 series processor and an Nvidia RTX graphics card.

The platform was built and tested on a windows desktop computer with an AMD Ryzen 7 5800X CPU and Nivdia RTX Quadro 4000 graphics card. The platform depends on video feeds being captured and processed through 3rd party software over the network which can be computationally expensive when multiple participants are engaged. We have not tested other configurations so cannot make recommendations beyond the above. We suggest running the platform and experimenting with settings to find a workflow that works with your available hardware.

Dependencies:
Touchdesigner: https://derivative.ca/download

Optional:
NDI Tools: https://www.ndi.tv/tools/
VB-Audio: https://vb-audio.com/
Obs Ninja: https://docs.obs.ninja/

VirtualDirector is a live broadcast and realtime editing tool for remote collaborators. The platform captures video feeds either through a screen capture of a video conferencing call or directly through webRTC, a secure peer-to-peer streaming technology facillitated by OBS Ninja developed by the amazing and generous Steve Seguin (https://github.com/steveseguin). VirtualDirector allows a user to mix video feeds from remote users inside a shared virtual environment that can be dynamically changed and saved as scenes to facilliate the rehearsal and performance of theatre. The platform has tools for removing chromakey backrounds, working with 2D video and image assets as background and foreground elements as well compositing remote participants inside 3D geometry.

VirtualDirector runs inside of Touchdesigner, a visual programming sandbox. Basic familiarity with Touchdesigner is recommended for succesfull deployment of VirtualDirector. The platform is modular and can be adapted to meet the specific needs of your performance troupe. The platform is released under an MIT Open Source License that requires attribution to the orignal developers (Boyd Branch & Piotr Mirowski) for any public use of the software. Commercial use of the software requires purchase of a professional Touchdesigner license (https://derivative.ca/UserGuide/TouchDesigner_Commercial). VirtualDirector was developed as part of a research project carried out at the University of Kent and is made publically available here for other researchers and performers to use free of charge (and also free of technical support :-) We only ask for notification of how it is being used and attribution if used for public performance. We are enthusiastic collaborators, so also welcome any interest in further developing the project.

You can learn more about how the platform was used to study the affects of tele-immersion on improvisational theatre here: https://www.youtube.com/watch?v=N9PXSp1Xa3M

To operate the software download the latest version of Touchdesginer and clone this repository to your fastest drive.  Open the VirtualDirector_XXXXX.toe file by double clicking the icon. 

VirtualDirector can work with video captured thought the use of NDI Tools or directly through OBS Ninja urls.

For capturing video from video conferencing software (Zoom, MS Teams, Skype etc) we recommend using NDI Tools screen capture: https://www.ndi.tv/nvidia/ to capture the video grid of particpants to feed into VirtualDirector. After downloading NDI tools, launch the NDI Screen Capture tool as well as the NDI Virtual Input. Select your Zoom window as the capture source for your NDI Capture Tool, and then select that source as your NDI Virtual Input.

Once you have your Zoom or other Web conferencing tool set up with NDI, you can bring that source in directly to Virtual Director via the 'Source Name' drop down menu. If you have multiple NDI feeds available, they will automatically populate this drop down. Select the relevant NDI Feed.

Virtual Director depends on users having a chromakey background. If your participants do not have green or blue screens at home, they can utilise the built in background removal tools in Zoom to upload a 'virtual green screen.' Just have the participants upload a green jpeg as their background.

Select Video Feeds:
Find the top center panel labled 'Library' to select from the available media frameworks available on your computer (usually DirectShow).
Next find your webcam device in the device link.

Next assign this NDI feed as your 'grid source.' Virtual Director allows a user to select from many different sources for thier grid including a provided grid of the 'Brady Bunch' to use for testing purposes. Click on the drop down menu next to 'Grid Source' and select 'NDI 1' to select your NDI source.

Next specify the amount of rows and columns in your grid.

If you have an uneven grid of players select the 'Odd' option next to your grid column selection. If your rows are even, select 'Even'

Press 'Update' to extract the players and load them into the GUI. (You may need to press update a few times to fully populate the grid)

Next select your background images by pressing the small folder icon at the end of the row labeled 'BGs.' We recommend beginning with the 2nd image set of backgrounds found in the 'Asset Folder' of this repo. Technically images can be of any size, but larger images will require more processing power. We also recommend a 16X9 apsect ratio for your images. We generally work with 1920 X 1080 px images.

Next find the 'FGs' label and select the folder icon at the end of the row to load a folder of .png images to use as 'foreground' elements. We suggest starting with the FG folder provided in the Asset folder with this repo.

Now you are ready to arrange your players. Find the middle console with the label 'Select Cast.' Here you can select individual cast member video feeds to refine their background segmentation. Select the number of the cast member from the dropdown. The following row labled 'P' and 'U' are for use with ObsNinja and can be ignored for now. Make sure the button to the right is in the 'off position' in order to work with your Zoom NDI capture. Press 'Smart Key' to perform an automatic background removal. If the chromakey is not well executed you can manually adjust the hue, saturation, and values to fine tune your key. Perform this operation for all players.

The rows to the left are your players. You can select any one of your cast as players 1-8 by clicking on the appropriate thumbnail. 

Make sure the '3D BG' button is turned off in the row between 'output' and 'preview'

*Note player 1 has an option for displaying the video feed of the operator with the small box labeled 'On' or 'off' at the bottom left. When set to 'On' the user video will be displayed instead of the cast member.

To see the immediate affect of player controls the 'Preview' window to the right displays all the realtime adjusments being made. The current settings for any scene can be saved by pressing one of the numbers in the 'Save' column.

The 'Prev' column will load the previously saved settings for a given cue number.

The saved scene numbers correspond to the 'Output' numbered tabs at the top. The output window feeds into an NDI output that can set to your virtual webcam or loaded directly in your broadcasting tool that supports NDI.

To compose a scene, select a background and fade the relevant players video up. 

Use the XY 2D sliders to position your players within the scene.

You can use the 'scale' sliders to scale the pixels up or down.

Use the 'Z pos' sliders to move the players closer or further from the virtual camera.

X,Y,Z rotation will rotate player videos on the corresponding axis.

Activate the foreground element by turning on the FG button located next to the 'BG Z Pos' of the of the middle console toward the bottom.

Select a foreground element by clicking on the icon of the relevant image.

The FG element can be positioned in the same way as the players using the sliders.

At the bottom of the 'preview' window are a set of tools for displaying text.

Type the text you want to display in the corresponding window. Select 'Text off' or 'Text on' to preview the text. Select 'Disp On or Disp off' to display the text in the output.

*Note you must save the scene with the text in oder to see it display in the output

Besides switching between saved scenes, you can also display the preview scene directly to the output by selecting the 'Go Live' button.

While outputing a scene, you can use the camera control buttons located beneath the scene numbers of the output window. 'CU1 - CU8' will dolly the virtual camera into a close up of the player. The other buttons are for use with a 3D scene which will be covered later.

You can record the video of your output by selecting a folder location and hitting the 'record' button. *Note recording is computationally expensive and requires a fast CPU to run 

There are several other advanced features which will be described later.

* Note background and foreground elements can be video or images. For video we suggest encoding your footage in the .hap codec for smooth playback. 





