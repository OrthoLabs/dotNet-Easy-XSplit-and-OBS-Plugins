# dotNet-Easy-XSplit-and-OBS-Plugins

I've provided many different examples of ways you could make plugins, including all the source. It should be able to be expanded with other engines. OpenTK is one of the most barebones because it's essentially just C# OpenGL bindings, which is a graphics library only. As long as you can create an array of 4 byte colors you should be able to adapt your own libraries for the plugin.

In theory, it should be possible to port everything here to other .NET languages, but I'm only familiar with using C#.

```
-External DLLS
  * CLRHost.Interop; Required for the OBS plugin support, source can be found at https://github.com/kc5nra/CLRHostPlugin
  * VHMediaCOM.dll; Included when you install XSplit.
```

```
-End User Standalone Setup:
  That defeats the purpose of this thing entirely.. but ok. 
  * Run a standalone version of the program 
  * Add the standalone program to the scenes you want. (Adding as a game means you can have other windows overlapping without it showing up on stream.)
  * Chroma/Color key out the background color, if needed. (For devs; Don't change this color while the program is running unless you're allowing the user to change the BG color to keep it that way.)
```

```
-End User XSplit Setup:
  * Drag the .XBS file into any scene you wish the plugin to run.
  * Run the .exe for it to send graphical data to XSplit. (The .exe needs to run for the plugin to work.) (For devs; I would advise giving the option to run the .exe in headless mode, since you don't actually need a window to render to, as long as you are rendering out to a texture behind the scenes.)
```

```
-End User OBS Setup:
  * Download and install CLRHostPlugin if you haven't already (make sure you install the 32 or 64 bit version in the correct spot, whichever version you're using). 
  * Extract the entirety of the bin folder into the CLRHostPlugin directory, including DLLS and any other content needed to run.
  * Launch OBS and add the plugin to the scene. OBS doesn't require you to run the .exe externally if the plugin itself can launch everything the application needs to render.
```
