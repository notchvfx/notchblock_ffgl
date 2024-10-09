# Notch Block FFGL Plugin

An experimental FFGL plugin that allows the use of [Notch Blocks](https://www.notch.one) in applications that support FFGL plugins; e.g. Resolume. (Windows OS only).
To use:
* Install the plugin in your host's FFGL effects directory.
* Instanciate the plugin in your host and load a Notch Block from the plugin's properties. 
* As with all Block playback integrations, a valid Notch Playback license (or Builder Pro license - which includes Playback) and Codemeter runtimes are required to load Notch Blocks. 
* Notch is 64 bit only - so the FFGL plugin is also 64 bit only, and will only work in 64 bit host applications that support 64 bit FFGL plugins.

## IMPORTANT

This plugin is provided 'AS IS' and on an 'AS AVAILABLE' basis, WITHOUT WARRANTY and WITHOUT SUPPORT.

Please read the [LICENSE.txt](LICENSE.txt) for full details.

## Download

Download using the 'Releases' section on the right side of the [Github site](https://github.com/notchvfx/notchblock_ffgl).

## Limitations

FFGL has some limitations as a plugin format which in turn limit the capabilities of this plugin beyond our control.

* Loading a Block will pause output until loading completes. Blocks are shared between instances of the plugin, so if one instance uses a Block it gets cached for all instances using that Block.
* When a project is opened containing instances of the plugin, the instances are only initialised - and therefore the Notch Block loaded - only when it gets displayed for the first time. You'll need to go through every instance of the plugin and display it when you first load the project to ensure you don't get pauses during playout. This is due to the lifecycle of an FFGL plugin in the host, so we can't change it. 
* Notch Block rendering and update rate is controlled by the host application, and performance is ultimately determined and limited by the host application. Some hosts are more efficient than others. 

The FFGL SDK does not allow dynamically changing properties (even on load). Therefore, there are some limitations on how Notch's exposed parameters can be handled.

* Hard limit of 32x exposed properties per type. (i.e. 32x floats, 32x ints, 32x strings)
* All float values are shown as 0-1 and then scaled to the range specified when exposing your parameter in Notch Builder.
* Exposed property groups are not supported.
* Multiple video input parameters are supported, but only if the host application supports this via FFGL. Most only support a single input.

## Requirements

The normal requirements of a Notch Block apply:

* An active [Notch Playback license](https://www.notch.one/pricing/), applied to a Codemeter Dongle.
* [Codemeter Runtimes](https://www.wibu.com/support/user/user-software.html) installed
* Windows 10 >= 1607
* DirectX 11.3 supported GPU
* Blocks from Notch 1.0 and 0.9.23 and earlier versions are all supported.
* Live network editing from Notch Builder is supported if the Block enables it.
