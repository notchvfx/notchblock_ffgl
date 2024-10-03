# Notch Block FFGL Plugin

A plugin that allows the use of [Notch Blocks](https://www.notch.one) in applications that support FFGL plugins; e.g. Resolume. (Windows OS only)

## IMPORTANT

This plugin is provided 'AS IS' and on an 'AS AVAILABLE' basis, WITHOUT WARRANTY and WITHOUT SUPPORT.

Please read the [LICENSE.txt](LICENSE.txt) for full details.

## Download

Download using the 'Releases' section on the right side of the [Github site](https://github.com/notchvfx/notchblock_ffgl).

## Limitations

FFGL has some limitations as a plugin format which in turn unavoidably limit the capabilities of this plugin.

* Loading a Block will pause output until loading completes. Blocks are shared between instances of the plugin, so if one instance uses a Block it gets cached for all instances using that Block.
* When a project is opened containing instances of the plugin, the instances are only initialised - and therefore the Notch Block loaded - only when it gets displayed for the first time. You'll need to go through every instance of the plugin and display it when you first load the project to ensure you don't get pauses during playout.
* Notch Block rendering and update rate is controlled by the host application, and performance is ultimately determined and limited by the host application. Some hosts are more efficient than others. 

The FFGL SDK does not allow dynamically changing properties (even on load). Therefore, there are some limitations on how Notch's exposed parameters can be handled.

* Hard limit of 32x exposed properties per type. (i.e. 32x floats, 32x ints, 32x strings)
* All float values are shown as 0-1 and then scaled to the range specified when exposing your parameter in Notch Builder.
* Exposed property groups are not supported.

## Requirements

The normal requirements of a Notch Block apply:

* An active [Notch Playback license](https://www.notch.one/pricing/), applied to a Codemeter Dongle.
* [Codemeter Runtimes](https://www.wibu.com/support/user/user-software.html) installed
* Windows 10 >= 1607
* DirectX 11.3 supported GPU
