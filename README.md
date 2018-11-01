# HyperStackReg Imagej plugin
A single channel time-lapse, Z-stack (C=1, Z>=1, T>1) can be aligned using [StackReg](http://bigwww.epfl.ch/thevenaz/stackreg/) plugin. HyperStackReg plugin, on the other hand, aligns images in a multi-channel hyperstack (C>1, Z>=1, T>1). The main idea of the HyperStackReg plugin is to apply the same transformation matrix to each channel of a hyperstack, so that all the channels of a hyperstack are registered with respect to each other.

# Installation
Put HyperStackReg_v04.class in the plugins folder and restart ImageJ. "HyperStackReg_v04" command should be visible under Plugins menu.
