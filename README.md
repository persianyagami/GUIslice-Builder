# GUIslice Builder

Please refer to the wiki page for installation and usage details:

[GUIslice Builder - Documentation](https://github.com/ImpulseAdventure/GUIslice/wiki/GUIslice-Builder)

![image](https://user-images.githubusercontent.com/8510097/90728338-9a8be100-e279-11ea-969e-cbd8bb0ac6c6.png)

## Brief Overview
The GUIslice Builder is a standalone desktop application that is more than a layout tool for your UI. It's designed as 
No Code GUI Generator for User Interfaces that make use of GUIslice API. 

The cross-platform utility includes a WYSIWYG graphical editor that enables drag & drop placement of UI elements. Once a GUI has been laid out, the Builder can then generate a fully functional GUIslice Graphical UI complete with plug-in points for your custom application. 

The GUIslice API framework code can handle hardware like Arduino, ESP8266, ESP32 and more. It supports Graphic libraries like 
Adafruit's GFX, M5Stack, TFT_eSPI and LINUX with a wide variety of TFT Display Drivers and combinations of Touch support chips.

The generated output code (*.c, *.ino, *_GSLC.h) includes all of the necessary defines, UI storage elements and initialization 
in addition to the placement of the UI elements. This will greatly improve the ease in creating a new Graphical Application.

You can find Example project files inside GUIslice/examples/builder

## Disclaimer ##
The Software is not designed for use in devices or situations where there may be physical injury if the Software has errors.

## Builder Contents
Note that the Builder executables and User Guide are attached to the latest GUIslice Builder Repository [Release Notes](https://github.com/ImpulseAdventure/GUIslice-Builder/releases):

## Builder Source Code
The Builder source code is located in this repository [ImpulseAdventure/GUIslice-Builder](https://github.com/ImpulseAdventure/GUIslice-Builder)
- Build instructions can be found in `BUILD.txt`

## Release History

### Enhancements for 0.16.0

With this release the Builder becomes a true WYSIWYG editor for most platforms. The Builder now reads and parses 
your actual Platform Font header and c files and renders them inside the Builder. This native font support will now 
be able to give you accurate sizing and positioning information for supported fonts. Plus your text will be now 
displayed exactly as it will appear on your target TFT display. 

The Native Font support includes, Adafruit's Builtin GLCD fonts, and Adafruit's GFX compatable fonts, and 
Teensy ILI9341_t3 fonts. This Native Font support includes the ability to add your own fonts to the Builder 
simply by dropping them into the proper folders. You may also tell the Builder to simulate fonts it doesn't directly support. 

See the User Guide for more information about font handling and how to add your custom fonts.

GUIslice API 0.16.0 has upgraded the Keypad support. This is a breaking change for the API so the Builder 
will now require running with GUIslice API 0.16.0 and higher. For further information on keypads 
refer to the wiki page [Custom KeyPads](https://github.com/ImpulseAdventure/GUIslice/wiki/Custom-KeyPads)

The Builder has added support for ctrl-Z for Undo and ctrl-Y for Redo.

### HotFix 0.16.b003
 - Bug No. 200 New Keypad support causes input field button case-statement to be deleted and recreated
 - Bug No. 199 Sizing of rect for Text with margin doesn't include space on right-side

### HotFix 0.16.b002
GUISlice crashing after clicking generate code issue `#134`

Assigning storage to text field gives incorrect height API issue `#292`

### HotFix 0.16.b001
 - Bug No. 197 Crash opening project with screen larger that 320x240
 - Bug No. 196 Dup gslc_ElemSetTxtCol when text not set to the default color

### Bug Fixes 0.16.0
 - Bug No. 195 Enhancement - Add Top/Bot to Text Button text alignment fields `#127`
 - Bug No. 194 gslc_GetImageFromRAM creates const pointer issue `#126` 
 - Bug No. 193 codegen fails to work for GSLCX_CHECKBOX_STYLE_ BOX or ROUND issue `#128`
 - Bug No. 191 Crash if slider min=max
 - Bug No. 189 Add shortcut ctrl+z for UnDo
 - Bug No. 187 App window not controllable with Java built-in themes issue `#112`
 - Bug No.  98 Text element "Fill Enabled=false" doesn't render with transparency

### HotFix 0.15.b005

#### Bug Fixes 0.15.0
 - Bug No. 186 selecting UTF8 enable causes code gen to output `$<COM-019>` instead of pElemRef
 - Bug No. 185 Adding BMP Image with 32-bit depth causes later crashes
 - Bug No. 184 Invalid font for keupad causes font id=null in gslc_ElemXKeyPadCreate_Num()

### HotFix 0.15.b004
 - Bug No. 183 Changing frame color of text element changes color of text on display but code gen is correct issue `#106`

### Enhancements for 0.15.b003

You can now move selected widgets using alt-up arrow, alt-down arrow, alt-left arrow, and alt-right arrow keys.

Updated User Guide **2.3 Creating your UI** to document the fine movement of widgets using the arrow keys.

### HotFix 0.15.b003
 - Bug No. 180 Enhancement - Request for using keyboard arrow keys to move objects pixel by pixel issue `#104`
 - Bug No. 29  Enhancement - Keyboard cursor shortcuts can move groups of elements
 - Bug No. 28  Enhancement - Keyboard cursor shortcut for fine element positioning

### HotFix 0.15.b002
 - Bug No. 182 Code gen for Teensy E_TY_5X8PT7B is being loaded  even if not used and Keypad fonts ignored- issue `#103`
 - Bug No. 181 Teensy platform code gen outputs `#include "font_Arial.h"` once for each font reference- issue `#103`

### HotFix 0.15.b001
 - Bug No. 179 Code gen for Project Tab's Extra fonts doesn't include the extra font's enum issue `#100`
 - Bug No. 178 Enhancement - Add dosis book 13 point font to the builder

### Enhancements for 0.15.0
- Update UserGuide for ver: 0.15.0
- Added support for Teensy 
- Added Support for M5Stack
- Support for Flash-based Numeric/Alpha input Fields
- Support for Flash based Slider control.
- Support for Toggle Button.
- Support for Seekbar, a modern slider control.
- Added Style options to Checkbox and Radio Buttons.
- Base Page UI Elements will now show through other pages.

### Changes for 0.15.0
On Windows 10 the menubar is moved into the title pane.

The templates/arduinofonts.csv and linuxfonts.csv have been replaced with templates/builder_fonts.json which should make it easier to add new or custom fonts. 

The Builder normally only does code generation for fonts that are referenced by UI Elements in the project file. The Project Tab now allows users to specify additional fonts to be loaded into the system so that they can be used with manual drawing of text.

Added Apache log4j2 trace logging in GUIsliceBuilder/logs/builder.log to help hunt down bugs.  The log file is rolled over daily and the rollover files are compressed using zip.  A maximum of 5 log files are kept.

#### Bug Fixes 0.15.0
 - Bug No. 177 Add page to view caused crash
 - Bug No. 176 Drag to invalid drop point in treeview caused crash
 - Bug No. 175 Load Additional Fonts that can be used with gslc_DrvDrawTxtAlign and other functions `#98`
 - Bug No. 174 When property `Touch Enabled?=true` builder needs to add gslc_ElemSetClickEn call
 - Bug No. 173 The selected colors for frame, fill and glow are not adopted for Sliders issue `#96`
 - Bug No. 171 using ctrl-X in Property View can cause crashes
 - Bug No. 170 Project Tab, screen size not used when placing or aligning widgets on screen issue `#93`
 - Bug No. 169 Moto_mono22 font duplicated should be Moto_mono24 in arduinofonts.csv file issue `#92`
 - Bug No. 168 Project Option Tab is output as a Page during code gen
 - Bug No. 166 Support for extended font modes (eg. Teensy) - Builder issue `#89`

### Enhancements since 0.13.0

- Enhancement to split [project name].ino file into  [project name].ino and [project name]_GSLC.h header.
- Addition of a Project Options tab that allows you to set project options and save them inside the project.
- Enhancement to File Chooser to maintain a list of recently accessed project files.
- Support for FlatLaf Themes and Intellij Themes.  Users may now also add their own custom themes.
- Added new feature "Copy Properties" in the layout tab.
- Support selecting Jpeg images if you are using TFT_espi drivers and SPIFFS storage.
- Added support for Google's Dosis and Noto(tm) fonts with their permissive licensing.
- Builder will now save and restore window frame and panel resizing.
- Support for dragging multiple UI Elements.
- Major Enhancements to the code generation of Button callbacks. 
- Reduction of boiler plate code for Keypad input fields

#### HotFix 0.14.b004
 - Bug No. 167 Changing target platform to LINUX in Project Tab can cause font errors and crashes

#### HotFix 0.14.b003
 - Bug No. 164 Reordering pages in Tree View causes NullPointerException - issue `#85`

#### HotFix 0.14.b002
 - Bug No. 161 Code gen for XGraph doesn't add font unless used by another element

#### HotFix 0.14.b001
 - Bug No. 159 Code gen for fresh sketch causes crash

#### Changes for 0.14.b000

Update to User Guide for version 0.14.b000

This version of the Builder requires GUIslice 0.14.0 or higher to run.

Added new feature "Copy Properties" in the layout tab. You pick a UI Element to copy from and then fill out a checklist marking properties to copy, then select the target elements to modify.

The Property "Use Default Colors?" has been removed from all UI models in order to facilitate the implementation of Copy Properties.

GUIslice API has added a new call gslc_ElemCreateTxt_P_R_ext(). This now allows the Builder to support NumberInput and TextInput Fields created in Flash indicated by the `Use Flash API?=true` property.  This can greatly reduce RAM requirements if you have a large number of input fields.

The Builder's boiler plate code for Keypad input fields have also been greatly reduced with GUIslice API now supporting Builder specific calls that wrap many input support calls into one call.
For example, the Builder now uses in the CbBtnCommon callback something like:
```
gslc_ElemXKeyPadInputAsk(&m_gui, m_pElemKeyPad, E_POP_KEYPAD, m_pElemVal1);
```
instead of:
```
gslc_ElemXKeyPadTargetIdSet(&m_gui, m_pElemKeyPad, E_TXT_VAL1);
gslc_PopupShow(&m_gui, E_POP_KEYPAD, true);
// Preload current value
gslc_ElemXKeyPadValSet(&m_gui, m_pElemKeyPad, gslc_ElemGetTxtStr(&m_gui, m_pElemVal1));
```
While in the CbKeypad callback three calls like:
```
gslc_ElemSetTxtStr(pGui, m_pElemVal1, gslc_ElemXKeyPadDataValGet(pGui, pvData));
gslc_PopupHide(&m_gui);
```
Becomes:
```
gslc_ElemXKeyPadInputGet(pGui, m_pElemVal1, pvData);
```

##### Bug Fixes
 - Bug No. 157 Enhancement request for Flash-based Numeric/Alpha input Fields
 - Bug No. 94  Enhancement request for Multi-element property update

#### HOTFIX 0.13.b025.2
 - Bug No. 158 Preserve Button Callbacks?=true was ignored and callbacks were deleted and recreated

#### HOTFIX 0.13.b025.1
 - Bug No. 156 Generation for SetPageCur includes `$<TBNT-101>`

#### Changes for 0.13.b025

Update to User Guide for version 0.13.b025

A major new feature is the addition of a Project Options tab that allows you to set options specific to the project
such as target platform, screen size, background color or image and screen rotation.

UI Element Icons are now shown in the TreeView for each element.

##### Bug Fixes
 - Bug No. 155 Newly created projects not added to recent file list
 - Bug No. 151 Support saving configurations in the project

 #### Changes for 0.13.b024

Update to User Guide for version 0.13.b024

Support for new Themes based upon the FlatLaf project also supporting user loading of Intellij Themes.  The existing custom themes have been removed due to the lack of support. See Appendix D of the new User Guide.

Further enhancements to the code generation of Button callbacks.  See Appendix E of the User Guide for more details.

Button callbacks "Jump to Page? True/False" and "Show Popup Page? True/False" have been replaced with simply specifying the Target Page to go to.  See Section 4.18 Text Button of the User Guide for more detalls.

Code Generation templates are now exposed and editable for customization. See Appendix F of the User Guide.

##### Bug Fixes
 - Bug No. 154 Jump to Page?=true for button then not setting PAGE ENUM crashes code gen
 - Bug No. 153 Unable to generate UTF-8 character Literals
 - Bug No. 152 Windows 7 users can't resize Builder's TFT Simulation display
 
#### Changes for 0.13.b023
Enhancement that will now save and restore window frame and panel resizing.

Added support for Google's Dosis and Noto(tm) fonts with their permissive licensing.  This is in addition to GNU's FreeFonts and their restrictive GNU General Public License version 3.0 or later license.

To use these fonts with Adafruit GFX simply copy them from the Builder's installation folder GUIsliceBuilder/gfx_fonts to your Adafruit_GFX_Library/fonts folder.

As before you may continue to add your own fonts to the Builder by following the instructions in the User Guide Appendix B.

#### Changes for 0.13.b022
Replaces 0.13.b021 which crashed if you used FreeFonts or any other custom fonts due to fonts not installed correctly in the *_GSLC.h file.

Enhancement to split [project name].ino file into  [project name].ino and [project name]_GSLC.h header that contains GUIslice API storage, Fonts, Element Initialization and other items users generally don't need to modify.  While [project name].ino will remain where users must do their code injections.

Target Platform linux will continue to use a single [project name].c file. Also, existing projects will be upgraded automatically with the existing [project name].ino renamed to [project name].ino.orig in case of any problems with the upgrade.  

Enhancement to File Chooser to maintain a list of recently accessed project files and to open the last accessed folder.

#### Changes for 0.13.b020
Fix for SnapTo grid will only work for dragging single object. Multiple objects being dragged will still ignore SnapTo setting otherwise spacing between objects would get distorted.

##### Bug Fixes
 - Bug No. 148 Dragging an object doesn't snap to grid when preferences has SnapTo=true

 #### Changes for 0.13.b019
Enhancements and bug fixes made to paste allowing users to copy a group of UI Elements and keep the original positioning.  Checkboxes and Radio Buttons now will create a default Element Reference name when users turn on callbacks.

Support is back in for dragging multiple UI Elements. This had been removed due to problems handling Zoom magnification.

We now support selecting Jpeg images if you are using TFT_espi drivers. It is assumed in this case you will be using SPIFFS. This is in anticipation of support being added to GUIslice API.  

##### Bug Fixes
 - Bug No. 146 Request that input fields support Text property
 - Bug No. 147 Pasting an Element with ElementRef incorrectly copies it.

#### Changes for 0.13.b018

##### Bug Fixes
 - Bug No. 143 Arduino IDE Auto Format will move tags so Builder can't find them
 - Bug No. 144 Changing Keypad font to one not previously used will result in it not being found
 - Bug No. 145 Code gen output for gslc_ElemCreateTxt_P_R has spurious  ">".

#### Changes for 0.13.b017
Enhancement to Button Callbacks to better determine when case statements need to be regenerated. We now test for button model modifications against any existing source code like adding a jump to page, showpopup, change to page, change in the name of page enum, change of a pElementRef name for Input Fields.

##### Bug Fixes
 - Bug No. 141 Input + Text fields need default colors turned off to see frame box at runtime.
 - Bug No. 142 Improve button callback generation vs existing source code.

#### Changes for 0.13.b016
Added Grid, Zoom In and Zoom Out icons to the mini-toolbar to better support non-english keyboards.

##### Bug Fixes
trap java.lang.IllegalStateException: cannot open system clipboard

#### Changes for 0.13.b015

##### Bug Fixes
 - Bug No. 138 Copy & paste of Numeric Input causes duplicate m_pElemVal 
 - Bug No. 139 Copy & paste of Numeric Input rendering ignores field size
 - Bug No. 140 Numeric Input Field Size renders one less character

#### Changes for 0.13.b014

##### Bug Fixes
 - Bug No. 137 Tree view reorganization causes fatal error

#### Changes for 0.13.b013

##### Bug Fixes
 - Bug No. 132 Application hangs when trying to run it under Linux Debian Buster with xfce4 desktop
 - Bug No. 133 Fatal error when deleting/selecting popup in tree view
 - Bug No. 134 Provide error check in template to catch case user selects incorrect Target Platform (ie. TFT_eSPI)
 - Bug No. 135 In some themes, the app window is not controllable because of missing title bar
 - Bug No. 136 Number Input ERROR: GetXDataFromRef(Type 4116, Line 254) Elem type mismatch

#### Changes for 0.13.b012
Bug 132 turns out to be a major issue on Linux with the Optional LAFs that causes the UI to only appear as the user moves the mouse over hidden UI panels. The Ribbon support we use is based upon an open project called insubstantial. This project also supplies our optional Look and Feels. The project, however, is no longer supported and the bug fix for linux is way beyond our ability to repair. A new version of the project exists and is supported but requires Java 9 and above. 

The Ribbon and other features work fine so the solution is to remove the optional LAFs for linux. They will still be available in windows 10 since no issues have been reported. Now however, Users will startup in the default Java system LAF for their platform.  Users (except for Macs) can go to edit->options->Themes and change to any available LAF.

A future version will upgrade LAFs to a supported Open Source Project that has modern LAFs for swing. For example, The FlatLAF project.

##### Bug Fixes
- Bug No. 132 Application hangs when trying to run it under Linux Debian Buster with xfce4 desktop

#### Changes for 0.13.b011
The Listbox edit list items dialog (entered by pressing '...' in its property tab) now has Move Up and Down for reordering items. You could and still can simply select a row and drag then drop to a new location but the new move commands will make it clearer.

##### Bug Fixes
 - Bug No. 127 Incorrect visual display width for ListBox without scrollbar
 - Bug No. 128 Fatal error when ctrl-c copy then paste element selected in treeview
 - Bug No. 129 Fatal error when pasting after undo of copy element
 - Bug No. 130 Random duplicate key and enum collisions of UI elements
 - Bug No. 131 Enhancement - add move up and move down commands to Listbox edit items dialog

 #### Changes for 0.13.b010

##### Bug Fixes
 - Bug No. 122 VSCode/PlatformIO Type error with gen code (char*) for ListBox should be (uint8_t*)
 - Bug No. 123 code gen fails when any text/label contains '$'
 - Bug No. 124 case statements generated for deleted UI elements in callbacks
 - Bug No. 125 code gen for keypad input fails with IllegalArgumentException
 - Bug No. 126 E_FONT_TXT5 not declared for keypad if no other text fields present

#### Changes for 0.13.b009 

##### Bug Fixes
 - Bug No. 120 gen code defines an empty string for ring gauge text while builder shows percent
 - Bug No. 121 Builder doesn't return the keypad result back to the linked text element in callback

#### Changes for 0.13.b008 

##### Bug Fixes
 - Bug No. 118 Platform  Arduino TFT_eSPI, should not have include Fonts/...
 - Bug No. 119 Delete extra page causes main page removal

#### Changes for 0.13.b007 

##### Bug Fixes
 - Bug No. 117 Code Gen for Target Platform -Arduino TFT_eSPI Missing template: <FONT_TFT_ESPI>

#### Changes for 0.13.b006 

##### Bug Fixes
 - Bug No. 116 Listbox gslc_ElemXListboxItemsSetGap missing colGap

#### Changes for 0.13.b005 

##### Bug Fixes
 - Bug No.  76 (re-open)Image file selection always opens to arduino_res should remember last directory accessed
 - Bug No. 113 Flash _P() macros with custom color parameters needs to be wrapped with parentheses
 - Bug No. 114 Builder should validate image formats to be sure they are supported
 - Bug No. 115 Builder should validate Page ENUM is used for jump page on Text+Image Button Callbacks

#### Changes for 0.13.0.4 Hot Fix for Use Flash API calls

##### Bug Fixes
 - Bug No. 107 RingGauge: undo button doesn't update Flat Color / Gradient color property visibility
 - Bug No. 112 Code gen fails for "Use Flash API" mode

 #### Changes for 0.13.0.3 Hot Fix for Adafruit GFX font usage

##### Bug Fixes
 - Bug No. 104 RingGauge: default Flat Color property should be GSLC_COLOR_BLUE_LT4
 - Bug No. 105 RingGauge: RingGauge: default Inactive Color property should be (gslc_tsColor) {0,0,48}
 - Bug No. 106 RingGauge: TFT Simulation incorrectly shows Flat Color property
 - Bug No. 108 RingGauge: codegen invalid API call to ElemXRingGaugeSetColorActiveFlat()
 - Bug No. 109 Can't Install GUIsliceBuilder as a NON-Admin user
 - Bug No. 110 (Issue 28) Compilation error in Adafruit-GFX.h fonts include typo 
 - Bug No. 111 (Issue 26) Compilation error: gslc_ElemXRingGaugeSetAngleRange(&m_gui,pElemRef, 270, 360, RING-102);

#### Changes for 0.13.0.2 Hot Fix for projects created with early beta versions of the builder

##### Bug Fixes
 - Bug No. 102 crash running code generation due to missing tags in .ino or .c files for older projects
 - Bug No. 103 Upgrading older project files causes duplicate storage to be assigned

#### Changes for 0.13.0.1 Hot Fix for linux and mac/os

##### Bug Fixes
 - Bug No. 100 Linux target platform gives missing FONT_INCLUDE template 
 - Bug No. 101 Builder fails to load in mac/os can't find starting class

#### Changes for 0.13.0

### Known Issues for Release 0.13.0

 - Bug No. 48 Crash on generate code in macOS when space in file name. 
 - Bug No. 86 Need to double click mouse twice sometimes to get a selection.
 - Bug No. 91 Fails to trap "invalid" filenames that are not permitted by the Arduino IDE

##### New UI Elements Supported

 - Line
 - Listbox
 - Number Input
 - Radial Gauge
 - Ramp Gauge
 - Ring Gauge
 - Spinner
 - Text Input
 - Base Page
 - PopUp Dialog Page

#### Removed Features
 - Import Button for importing non-builder created projects. Round trip edits of builder created files are still supported. Maintence costs for the Import feature were too high to continue support.

##### Bug Fixes
 - Bug No. 7  Support transparency in BMP 
 - Bug No. 12 All widgets should allow renaming ElementRef field
 - Bug No. 27 Ability to duplicate an elements 
 - Bug No. 65 Creating saved ElemRef should follow ElemCreate instead of using PageFindElemById
 - Bug No. 66 XTextBox bad values sent to the gslc_ElemXSliderCreate() 
 - Bug No. 68 Regenerating code increments m_sX* array indices in ElemX*Create()
 - Bug No. 69 Box UI for tick func generates gslc_ElemSetTxtAlign() instead of gslc_ElemSetTickFunc()
 - Bug No. 70 Code gen puts out gslc_ElemCreateBox instead of gslc_ElemCreateBox_P version for arduino flash
 - Bug No. 71 Code gen for XGraph crashes 
 - Bug No. 72 remove Auto gen id in arduino flash _P routines 
 - Bug No. 73 remove save folder restrictions
 - Bug No. 75 Widget select+move sometimes unresponsive
 - Bug No. 76 Image file selection always opens to arduino_res Remember last directory in which an image was selected
 - Bug No. 77 Changed global option Target Image Directory isn't retained without pressing Enter first before OK 
 - Bug No. 79 Added status bar to avoid confirmation dialogs 
 - Bug No. 80 Deleting a Button Image does not remove the corresponding case in the CbBtnCommon callback function.
 - Bug No. 81 Extended widgets headers no longer use GUIslice_ex.h 
 - Bug No. 82 keyboard shortcutsfor the frequently used System related functions (Save Export Delete etc.). 
 - Bug No. 83 request to resize panes 
 - Bug No. 85 grouping radio buttons always assigns GROUP0 
 - Bug No. 87 Crtrl-D is supported for deletions but not Command Delete key
 - Bug No. 88 Default target image path needs leading slash “/“ on SD filenames
 - Bug No. 89 Element drag when in zoomed mode doesn't track mouse 
 - Bug No. 90 checkboxes and radio buttons should have either width or height. 
 - Bug No. 92 Change the default background color to black 
 - Bug No. 96 Fatal error can cause crash log loop 
 - Bug No. 97 Install not change project directory
 - Bug No. 99 Progress Bar Frame not showing up on TFT simulation screen