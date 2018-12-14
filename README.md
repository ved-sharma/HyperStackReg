# HyperStackReg ImageJ plugin

![alt text](https://github.com/ved-sharma/HyperStackReg/blob/master/Data/Example%20hyperstack%20-%20before%20vs%20after.gif "Example image")

**Movie:** A 16-bit multi-channel (blue, green and red) hyperstack before and after HyperStackReg registration. The intravital multiphoton movie shows green and red labeled cells moving in vivo in living mice. Extracellular matrix collagen fibers are shown in blue.

# Rationale
A single channel time-lapse, Z-stack (C=1, Z>=1, T>1) can be aligned using [StackReg](http://bigwww.epfl.ch/thevenaz/stackreg/) plugin. HyperStackReg plugin, on the other hand, aligns images in a multi-channel hyperstack (C>1, Z>=1, T>1). The main idea of the HyperStackReg plugin is to apply the same transformation matrix to each channel of a hyperstack, so that all the channels of a hyperstack are registered with respect to each other.

# Installation
Put <a href="https://github.com/ved-sharma/HyperStackReg/blob/master/HyperStackReg_.class" download>HyperStackReg_.class<a/> in the plugins folder and restart ImageJ. "HyperStackReg_" command should be visible under Plugins menu.

# Requires
Just like StackReg, HyperStackReg requires that another plugin called TurboReg should be installed. Please follow directions described on the [StackReg page](http://bigwww.epfl.ch/thevenaz/stackreg/).

# How the plugin works
**Step 1:** User opens a multi-channel hyperstack (C>1, Z>=1, T>1) and runs the HyperStackReg_ plugin. In a pop-up dialog window, user then selects the transformation type (Translation, Rigid body, Scaled rotation, Affine) and the channels to be used for transformation matrix computation. All the channels are selected, by default. Behind-the-scene processing details are printed in the Log window.

**Step 2:** The plugin duplicates the user-selected channels (and the corresponding Z and T frames) into a hyperstack and merges those channels into an RGB hyperstack (C=1, Z>=1, T>1). No RGB flattening is done, if user selects a single channel for transformation matrix computation (Step 1).

**Step 3:** The resulting hyperstack is then aligned for each Z and T; and transformation matrices are stored in a text file. The duplicated hyperstack is closed.

**Step 4:** Transformation matrices are read from the text file and applied to the first channel (C=1) of the original hyperstack. This process is repeated for all the channels (2nd, 3rd, 4th...so on) of the original hyperstack.

**Step 5:** All the registered channels are combined into a hyperstack.

# Batch processing
Plugin is macro recordable, so a folder full of files can be processed in batch mode. Check the [HyperStackReg_processFolder.ijm](https://github.com/ved-sharma/HyperStackReg/blob/master/HyperStackReg_processFolder.ijm) macro for example.

# Acknowledgements
This plugin builts on the functionalities of other plugins: [StackReg](http://bigwww.epfl.ch/thevenaz/stackreg/) and [MultiStackReg](http://bradbusse.net/downloads.html)

# Author
HyperStackReg plugin was created by [Ved Sharma](mailto:vedsharma@gmail.com) during 2015-16, while in the [John Condeelis laboratory](https://www.einstein.yu.edu/labs/john-condeelis/) at Albert Einstein College of Medicine.

# How to cite
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2252521.svg)](https://doi.org/10.5281/zenodo.2252521)

# License
See [license](https://github.com/ved-sharma/HyperStackReg/blob/master/LICENSE) file

