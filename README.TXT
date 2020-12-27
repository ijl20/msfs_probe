*************************************
*       Sim_probe version 3.00      *
*************************************

Author: Ian Forster-Lewis

This is the FSX add-on that calculates ridge lift directly from the terrain and
prevailing wind, passing the value to CumulusX! for use within FSX.

New for version 3.00 is the automatic save of IGC flight log files in any
folder you specify.  These can be viewed in a variety of log analysis programs,
including:

* FSZweverView2 (download from www.virtualsoaring.org)

* IGCview ( http://carrier.csi.cam.ac.uk/forsterlewis/soaring/igcview/igcview.html )
    clunky, but web based and can display/race multiple logs

* Google Earth (trace converted by http://www.gpsvisualizer.com )

* http://www.everytrail.com
   e.g. http://www.everytrail.com/view_trip.php?trip_id=24425

* http://ywtw.de/igcsimen.html
     animated Google Earth tool that 'flies' your trace within Google Earth.

If you had a previous version of sim_probe, not that from version 3.00 the
module no longer displays a Command Prompt window by default. Instead the
module displays an 'add-on' menu with a submenu item to display the status
text (ridge lift value)

Note for the ridge lift capability, sim_probe still has CumulusX as a 
pre-requisite (although it is not needed if you want sim_probe purely for
the IGC file logging).

CumulusX! is available at http://www.luerkens.homepage.t-online.de/peter/

***************************************************************************

INSTALLATION

  (1) download CumulusX! from http://www.luerkens.homepage.t-online.de/peter/

  (2) follow the installation instructions for CumulusX!

  (3) INSTALL THE VISUAL C++ 2008 RUNTIME LIBRARY (vcredist_x86.exe)
      Download and install the file from Microsoft:

      http://www.microsoft.com/downloads/details.aspx?familyid=9B2DA534-3E03-4391-8A4D-074B9F2BC1BF&displaylang=en

      A copy of the file vcredist_x86.exe is included in this zip file if for some reason you have a problem
      with the above link.

  (4) INSTALL THE SIM_PROBE.EXE FILE:
      From the Windows 'start' menu, open "My Computer" and navigate through the folders to
      "C:\Program Files\Microsoft Games\Microsoft Flight Simulator X"

      Open the sim_probe zip file (i.e. the file containing this readme)
      with Windows Explorer

      drag the 'Modules' folder
      into your base FSX program folder, i.e. you should end up with
      "C:\Program Files\Microsoft Games\Microsoft Flight Simulator X\Modules\sim_probe\sim_probe.exe"

  (5) INSTALL THE SIMPROBE OBJECT:
      From the zip file window, 
  
      drag the "SimObjects" folder 
      into your base FSX program folder, i.e. you should end up with
      C:\Program Files\Microsoft Games\Microsoft Flight Simulator X\SimObjects\Misc\SimProbe"

  (6) ADD SIM_PROBE.EXE TO YOUR FSX AUTOSTART FILE "EXE.XML":

      If this is the *first* time you've ever added an add-on module to FSX, you may not
      have an "exe.xml" file at all, in which case you will have to create one using 
      Notepad.  Otherwise you can use Notepad to simply edit it. A sample "exe.xml" file
      is at the end of this readme.

         The "exe.xml" file is at the following locations:

            on XP:
   
      "<Drive>:\Documents and Settings\<username>\Application Data\Microsoft\FSX\exe.xml"


            on Vista:

      "<Drive>:\Users\<username>\AppData\Roaming\Microsoft\FSX\exe.xml"

      Note the "Application Data" or "AppData" folder can be 'hidden' by default in Windows and
      in Windows Explorer you might have to go into Tools->Folder Options for the
      "<Drive>:\Documents and Settings\<username>" folder and select "show hidden files and folders"
      If you don't find the file in that directory, you haven't set up CumulusX! to autostart and
      should go back and fix that.

      You need to add a "<Launch.Addon>" section for sim_probe.exe, which you can cut-and-paste
      from the sample below.  For completeness I've included the entire file including the entries
      for CumulusX! and sim_probe.  Yours may have *additional* entries if you have other addons
      *or* if you have FSX Deluxe/Professional you will have an entry for the Object Placement Tool.

      The sim_probe entry will look something like the following. Note the 'CommandLine' entry is 
      *new* for this version of sim_probe, and you can specify *any* folder for saving your IGC
      log files.  Note the use of quotes and double-backslashes, particularly the "\\" at the *end*
      of the log folder name. Note the use of quotes and double-backslashes, particularly the 
      "\\" at the *end* of the log folder name. There. I hope you're paying attention.

      <Launch.Addon>
        <Name>sim_probe</Name>
        <Disabled>False</Disabled>
        <ManualLoad>False</ManualLoad>
        <Path>Modules\sim_probe\sim_probe.exe</Path>
        <CommandLine>log="C:\\Documents and Settings\\Ian\\My Documents\\fs\\igc_files\\"</CommandLine>
      </Launch.Addon>


  (7) Start FSX, and you should see a new "Add-ons".."sim_probe" menu item.

  (8) Alt-tab to your CumulusX! window, and check the sim_probe status is checked and showing
      as 'green'. The FSX menu "Add-ons".."sim_probe".."show status text" will display the 
      ridge lift sim-probe is calculating in a green bar at the top of the page.  You can drag this
      bar lower down the page if you prefer.

  (9) The IGC files will be saved as <tail number>_<date>_<time>.igc in the folder of your choice.
      The file will actually be saved at any of the following:
      * when you complete a mission (succeed or fail)
      * when you land
      * when you exit a free flight
      * when you click the "add-ons".."sim_probe".."save IGC file" menu item
      It is worth going into the aircraft selection options and setting the tail number of the
      DG808S to your competition number.  I'm B21.

See the www.virtualsoaring.org forum for FSX/CumulusX! and you'll be able to get help from other users.

Good luck.

Ian Forster-Lewis


****************************************************************************************************
******************         SAMPLE EXE.XML FILE       ***********************************************
****************************************************************************************************

<?xml version="1.0" encoding="Windows-1252"?>

<SimBase.Document Type="Launch" version="1,0">
  <Descr>Launch</Descr>
  <Filename>exe.xml</Filename>
  <Launch.ManualLoad>False</Launch.ManualLoad>
  
  <Launch.Addon>
    <Name>CumulusX</Name>
    <Disabled>False</Disabled>
    <ManualLoad>False</ManualLoad>
    <Path>Modules\CumulusX!\CumulusX.exe</Path>
    <CommandLine></CommandLine>
  </Launch.Addon>

  <Launch.Addon>
    <Name>sim_probe</Name>
    <Disabled>False</Disabled>
    <ManualLoad>False</ManualLoad>
    <Path>Modules\sim_probe\sim_probe.exe</Path>
    <CommandLine>log="C:\\Documents and Settings\\Ian\\My Documents\\fs\\igc_files\\"</CommandLine>
  </Launch.Addon>


</SimBase.Document>


