# The Irrlicht Engine SDK version 1.8.4 - Modified version

Welcome the Irrlicht Engine SDK.

Content of this file:

0. Additions over standard Irrlicht 1.8.4
1. Directory Structure Overview
2. How To Start
3. Requirements
4. Release Notes
5. License
6. Contact

## 0. Additions over standard Irrlicht 1.8.4

* CMake based toolchain.

## 1. Directory Structure Overview

  You will find some directories after uncompressing the archive of the
  SDK. These are:

| Dir      | Description |
| -------- | ----------- |
| examples | Examples and tutorials showing how to use the engine with C++. |
| include  | Header files to include when programming with the engine. |
| media    | Graphics and sound resources for the demo applications and examples. |
| source   | The source code of the Irrlicht Engine. This code is not needed to develop applications with the engine, but it is included to enable recompilation and debugging, if necessary. |
| tools    | Useful tools (with sourcecode) for the engine. |

## 2. How to start

To see the engine in action in Windows, just go to the \bin\Win32-VisualStudio
directory, and start some applications. There should also be an
application named Demo.exe which should show the most
interesting features of Irrlicht.

To start developing own applications and games with the engine take
a look at the 01.HelloWorld example in the \examples directory.
There is also a .html file with a tutorial which should be
easily comprehensible.

The Irrlicht Engine is a static lib under linux. A precompiled version can be
generated from the sources using the Makefile in source/Irrlicht. Run 'make' in 
that subfolder. After this you should be able to 'make' all
example applications in /examples by calling the buildAllExamples script. You 
can run the examples then from the bin folder.

It is also possible to use Irrlicht as shared object
(libIrrlicht.so.versionNumber). Use the proper makefile target for this by
running 'make sharedlib' in the source folder. See the Makefile for details.

For OSX you can find an XCode project file in source/Irrlicht/MacOSX. This will
build the libIrrlicht.a library necessary to create the apps.

## 3. Requirements

You can use one of the following compilers/IDEs to develop applications
with Irrlicht or recompile the engine. However, other compilers/IDEs may
work as well, we simply didn't test them.

* gcc 4.x
* Visual Studio 2010(10.0)-2013(12.0)
* Code::Blocks (& gcc or visual studio toolkit)
  
If you ever want to (re)compile the engine yourself (which means you don't
want to use the precompiled version) you need the following:

* Windows:
  * Needed: PlatformSDK (which usually comes with all IDEs, download it separately for MSVC Express 2005)
  * Optional: DirectX SDK, for D3D9 support
  * Optional: DirectX SDK prior to May 2006, for D3D8 support
* Linux:
  * Needed: XServer with include files
  * Optional: OpenGL headers and libraries (libGL.so) for OpenGL support
    * GLX +
    * XF86VidMode [package x11proto-xf86vidmode-dev] or XRandr (X11 support libraries, the latter two for fullscreen mode)
* OSX:
  * Needed: XCode and Cocoa framework
  * Needed: OpenGL headers and libraries

## 4. Release Notes

Informations about changes in this new version of the engine can be
found in changes.txt.

Please note that the textures, 3D models and levels are copyright
by their authors and not covered by the Irrlicht engine license.

## 5. License

The license of the Irrlicht Engine is based on the zlib/libpng license.
Even though this license does not require you to mention that you are
using the Irrlicht Engine in your product, an acknowledgement
would be highly appreciated.

Please note that the Irrlicht Engine is based in part on the work of
the Independent JPEG Group, the zlib, and libpng. This means that if you use
the Irrlicht Engine in your product, you must acknowledge somewhere
in your documentation that you've used the IJG code and libpng. It would
also be nice to mention that you use the Irrlicht Engine and the zlib.
See the README files in the jpeglib and the zlib for
further informations.


### The Irrlicht Engine License

Copyright (C) 2002-2015 Nikolaus Gebhardt

This software is provided 'as-is', without any express or implied
warranty.In no event will the authors be held liable for any damages
arising from the use of this software.

Permission is granted to anyone to use this software for any purpose,
including commercial applications, and to alter it and redistribute it
freely, subject to the following restrictions:

1. The origin of this software must not be misrepresented; you must not
 claim that you wrote the original software. If you use this software
 in a product, an acknowledgement in the product documentation would be
 appreciated but is not required.
2. Altered source versions must be clearly marked as such, and must not be
 misrepresented as being the original software.
3. This notice may not be removed or altered from any source distribution.

## 6. Contact

If you have problems, questions or suggestions, please visit the
official homepage of the Irrlicht Engine:

http://irrlicht.sourceforge.net

You will find forums, bugtrackers, patches, tutorials, and other stuff
which will help you out.

If want to contact the team of the engine, please send an email to
Nikolaus Gebhardt:

irrlicht@users.sourceforge.net

Please also not that parts of the engine have been written or contributed
by other people. Especially: (There are probably more people, sorry if I forgot one.
See http://irrlicht.sourceforge.net/author.html for more informations)

* Christian Stehno (hybrid) Contribution Coordinator/Developer
* Michael Zeilfelder (cutealien) Developer
* Patryk Nadrowski (Nadro)Developer
* Yoran Bosman (Yoran)Webserver administrator
* Gareth Davidson (bitplane)Developer/ Forum admin
* Thomas Alten (burningwater) Wrote the burningsvideo software rasterizer
* Luke P. Hoschke (luke)Wrote the b3d loader, the new animation system, VBOs and other things
* Colin MacDonald (rogerborg) All hands person
* Ahmed Hilali (blindside)The shader and advanced effects man
* Dean Wadsworth (varmint)OSX port maintainer and game developer
* Alvaro F. Celis (afecelis)Lots of work in the community, for example video tutorials about Irrlicht, forum admin
* John Goewert (Saigumi)Wrote some tutorials for the Irrlicht Engine and doing admin stuff
* Jam Takes care of moderating the forums and keeps them clean from those evil spammers.

Many others (this list hasn't been updated in a while, but they are often mentioned in changes.txt)
* Etienne Petitjean wrote the MacPort of the engine
* Mark JeacockeWrote lots of helpful comments and ideas in the forums and per email.
* Julio Gorgé Created the 'Unofficial DirectX 9.0 Driver for the Irrlicht Engine'
* Andy SpurgeonWrote the Dev-Cpp tutorial.
* André SimonWrote the Codewarrior tutorial.
* KnightToFlightCreated the unoffical terrain renderer addon for the Irrlicht Engine.
* Jon PryWrote the code to load compressed TGA files.
* Matthew CouchWrote the tokamak integration tutorial.
* Max WinkelWrote the splitscreen tutorial.
* Gorgon ZolaWrote the ODE integration tutorial.
* Dean P. MacriSent in code for curved surfaces and PCX Loading.
* SirshaneMade several bug fixes, sent in code for making the mouse cursor invisible in Linux.
* Matthias GallSent in code for a spline scene node animator and reported lots of bugs.
* Mario GruberSuggested triangle fan drawing and sent in code for this.
* AriaciSpotted out a bug in the ATI driver.
* Dr Andros C BragianosImproved texture mapping in cube scene node.
* Philipp DortmannSent in code for stencil buffer support for OpenGL.
* Jerome NicholsCreated the Irrlicht/Ruby interface located at irr.rubyforge.org
* Vash TheStampedeSent code for missing Draw2DLine() implementations
* MattyBoyXBOX support suggestions
* Oliver KlemscreateImageFromData() method suggestion/implementation
* Joxreally, really a lot of bug fixes, and the LMTS file loader
* ZolaQuaternion method additions
* Tomasz Nowakowskivarious bug fixes
* Nicholas Braystencil shadow bug fixes with OpenGL
* REAPERmouswheel events for scrollbar
* Calimerovarious bug fixes like vector2d operators
* Haddockbugfix in the linked list
* G.o.DXML parser fix
* Erik ZilliTranslated some of the tutorials from my stuttering english into real english. :)
* Martin PiskernigLinux bugfixing and testing
* SoconneWrote the original terrain renderer were Irrlichts terrain renderer of Irrlicht is based on it.
* SpintzGeoMipMap scene node, terrain renderer of Irrlicht is based on it.
* Murphy McCauleyOCT file loader, MIM tools
* Saurav MohapatraIrrCSM, and lots of addons, suggestions and bug reports
* Zhuck DimitryMy3D Tools
* Terry WelshAllowed me to use the textures of his 'Parallax Mapping with Offset Limiting' paper for the parallax demo of Irrlicht
* rtWrote the original .png loader for Irrlicht
* Salvatore RussoWrote the original .dmf loader for Irrlicht
* VoxVarious bug reports and fixes
* atomiceContributed code for a ms3d loader enhancement
* William FinlaysonOpenGL RTT, GLSL support and the reflection 2 layer material for OpenGL.
* DelightVarious code contributions for Irrlicht.NET (particle system, basic shader support and more)
* Michael ZoechImproved GLSL support
* Jean-loup Gailly, Mark AdlerCreated the zlib and libpng
* Guy Eric Schalnat, Andreas Dilger, Glenn Randers-Pehrson and othersCreated libpng
* The Independent JPEG GroupCreated JPEG lib
* Dr Brian Gladman AES Created aesGladman
