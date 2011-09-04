# folderify

<img alt="Octocat" src="https://github.com/lgarron/folderify/raw/master/examples/octocat/octocat.png" style="width: 256px; vertical-align: middle;"/>
<span style="font-size: 128px; vertical-align: middle;">&rarr;</span>
<img alt="Octocat Folder" src="https://github.com/lgarron/folderify/raw/master/examples/octocat/octocat_folder_256.png" style="width: 256px; vertical-align: middle;"/>
<img alt="Octocat Folder" src="https://github.com/lgarron/folderify/raw/master/examples/octocat/octocat_folder_128.png" style="width: 128px; vertical-align: middle;"/>
<img alt="Octocat Folder" src="https://github.com/lgarron/folderify/raw/master/examples/octocat/octocat_folder_32.png" style="width: 32px; vertical-align: middle;"/>
<img alt="Octocat Folder" src="https://github.com/lgarron/folderify/raw/master/examples/octocat/octocat_folder_16.png" style="width: 16px; vertical-align: middle;"/>


## Usage

Requires [ImageMagick](http://www.imagemagick.org/) to be installed (you should be able to run <code>convert</code> on the commandline).

    $ folderify examples/octocat/octocat.png
 
- The input file should be an image with a transparent background (i.e. the corners should be transparent).
- folderify will produce 5 folder icon images at different resolutions.
  - These can be combined into a .icns file using a tool like "Icon Composer" or png2icns.
  - The .icns file can be assigned as the icon of a file a tool like IconDroplet (another alternative is to assign the icon to an XCode OSX application project and build).
  - The icon can be copied to a folder using the "Get Info" pane in the Finder.
  
## TODO

folderify should become completely automated. Current issues:

- Tweak the settings to approximate the default OSX icons as closely as possible.
- Combining the .png files into .icns: [png2icns](http://icns.sourceforge.net/) seems to use an incorrecticns type for the larger resolution. [IconDroplet](http://zweisoft.blogspot.com/2011/06/icondroplet-15.html) runs into errors for mer.
- Applying the icon to an actual file: [assignIcon](http://hasseg.org/stuff/assignIconScript/assignIcon.py) or plain Rez/DeRez doesn't seem to work on my Lion installation.
- Efficiency: don't read-trim-resize the file so much. (Use -clone?)
- Maybe: Handle automatic positive/negative detection, so that the mask doesn't have to be generated by hand.
