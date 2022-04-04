Quickstart Tutorial
===================

Step 1 - Downloading
********************

First, make sure you've downloaded SGI from itch.io:

https://kyamix.itch.io/sgi

Accept no substitutes!

You'll want the engine targeted at the platform you're developing on, not the target you want to distribute your game on.

For example, let's say you want to develop on a Mac, but want to distribute on Mac, Windows, and Linux. You only need to download the DMG file.

You should also download the codesample. The codesample is platform-agnostic, so no matter if you're using Windows, Linux, or Mac, you'll download the same codesample file.

Step 2 - Create a workspace folder for your project
***************************************************

Create a directory for your project, and place the contents of your SGI engine download into it. Then, place the src folder from the codesample into it as well.

You should see three folders in the root directory of your project:

* compiler
* src
* target

*compiler* contains the compiling binary for your platform. (This came from the engine download)

*src* contains your project's source code. (This came from the codesample download)

*target* contains static binaries and libraries to make your game run. (This came from the engine download)

Step 3 - Duplicate the target folder
************************************

Generally, you want to keep the target folder clean so if things go awry with libraries or binaries, you can start again
without the need to download everything multiple times. Don't create a symlink, it'll become clear later on why that's a bad idea.

Open a command prompt, and get into the root directory of your project. Then:

.. tabs::

   .. tab:: Windows
   
      ``xcopy /E /I target dist``
     
   .. tab:: Linux

      ``cp -r target dist``

   .. tab:: MacOS

      ``cp -r target dist``
     
If things go badly with your build, you can simply delete the *dist* directory, then copy target back into it. (Hence, do not create a symlink!)

Step 4 - Attempt to compile the template
****************************************

The SGI download comes with a bare-bones logic file to start the engine successfully. It has no sound, no sprites, nothing other than
a simple start box and a command line to exit.

So, let's try it out now:

.. tabs::

   .. tab:: Windows
   
      ``compiler\compile.exe -k 1234567890123456 -i 1234567890123456 -s src -o dist``
     
   .. tab:: Linux

      ``./compiler/compile -k 1234567890123456 -i 1234567890123456 -s src -o dist``

   .. tab:: MacOS

      ``./compiler/compile -k 1234567890123456 -i 1234567890123456 -s src -o dist``

You can get an explanation of the parameters in the Appendix.

If all went well, you should see the compiler spit out some build information.



Step 5 - Running your first build
*********************************

If the compile was successful, you will now have target builds for all three platforms: Windows, GNU Linux, and MacOS.

.. note::

   Kyamix is not signed. This means that on Windows and MacOS, you may have to instruct your operating system that the binary is safe to run.

.. tabs::

   .. tab:: Windows
   
      ``dist\windows\kyamix.exe``
     
   .. tab:: Linux

      ``./dist/linux/kyamix &``

   .. tab:: MacOS

      ``open -a dist/macos/Kyamix``




